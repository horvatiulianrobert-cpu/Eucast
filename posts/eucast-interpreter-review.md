---
title: "Review: EUCAST Batch Interpreter prototype"
date: 2026-11-08
---

# Review: EUCAST Batch Interpreter prototype

The supplied HTML is a self-contained Romanian-language prototype for entering antibiotic susceptibility test results and generating a printable report. It has a clear workflow and responsive layout, but it should **not be used for clinical interpretation or patient care in its current form**.

## Findings

### Critical: EUCAST interpretations and version claim are not validated

The page labels itself “v14.0 Compliant” and presents hard-coded S/I/R breakpoints and clinical comments as EUCAST criteria. The supplied code does not identify authoritative EUCAST tables, organism/indication-specific assumptions, disk content, dosage/exposure assumptions, or a validation process. Several interpretations are also simplified to numeric thresholds. A disclaimer alone would not make these results safe for clinical use.

**Before any clinical use:** verify every breakpoint and expert rule against the applicable official EUCAST tables and guidance; record the table/version and assumptions; and obtain review and validation by qualified clinical microbiology professionals. Otherwise, present the output only as a clearly labeled non-clinical demonstration and do not call it EUCAST-compliant.

### High: Custom values are inserted into HTML without escaping

`openAddCustomAntibioticModal()` accepts a name and comment from the user. `renderBatchForm()` and `generateFinalReport()` interpolate those values into `innerHTML`. Markup entered as a custom name or comment can therefore be interpreted as HTML/script in the page.

**Fix:** build elements with DOM APIs and assign user-provided strings with `textContent` (or use a well-maintained HTML escaping/sanitizing approach where markup is genuinely needed). Apply the same rule to every interpolated value.

### Medium: Custom breakpoints cannot reliably be set to zero

The `parseFloat(...) || default` expressions in `openAddCustomAntibioticModal()` replace a valid value of `0` with the fallback. This makes zero breakpoints impossible to enter and can silently produce different criteria than intended.

**Fix:** distinguish an invalid/empty input from numeric zero, for example by checking `Number.isFinite(value)` after parsing.

### Medium: Switching organisms discards entered results

`loadOrganismAntibiotics()` rebuilds the list with blank values. Changing the organism selection loses all values entered for the previous organism without warning.

**Fix:** either preserve values per organism or ask for confirmation before discarding them.

## Other improvements

- Validate input units and allowed precision; disk diameters and MIC values should not be treated as interchangeable arbitrary numbers.
- Avoid using `parseFloat` alone for validation, since it accepts partially numeric strings.
- Recompute the report date/time when generating a report, rather than only when the page first loads.
- Add automated tests for breakpoint boundary behavior, invalid methods, custom inputs, and report rendering.
- Consider storing patient identifiers only when necessary; the page currently handles them in the browser, but printed reports may contain sensitive information.

## Recommendation

Treat this as a UI prototype, not a validated antibiogram interpretation system. Do not use its classifications to guide treatment. Resolve the clinical validation and unsafe HTML rendering findings before considering any deployment.
