<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EUCAST Batch Interpreter & Generare Raport</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }

        @media print {
            .no-print { display: none !important; }
            .print-only { display: block !important; }
            body { background: white !important; color: black !important; }
            .print-shadow-none { shadow: none !important; border: 1px solid #e2e8f0 !important; }
        }
    </style>
</head>
<body class="bg-slate-100 text-slate-800 min-h-screen flex flex-col selection:bg-blue-500 selection:text-white">

    <!-- Header (No Print) -->
    <header class="bg-gradient-to-r from-blue-900 via-indigo-900 to-slate-900 text-white shadow-lg no-print">
        <div class="max-w-7xl mx-auto px-4 py-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row justify-between items-center gap-3">
            <div class="flex items-center space-x-3">
                <div class="p-2.5 bg-blue-500/20 rounded-xl backdrop-blur-md border border-blue-400/30">
                    <i data-lucide="activity" class="w-7 h-7 text-blue-300"></i>
                </div>
                <div>
                    <h1 class="text-xl font-bold tracking-tight flex items-center gap-2">
                        EUCAST Smart Interpreter 
                        <span class="text-[10px] bg-blue-500/30 text-blue-200 px-2 py-0.5 rounded-full border border-blue-400/30">v14.0/v16.1 Compliant</span>
                    </h1>
                    <p class="text-xs text-blue-200">Sistem automatizat de evaluare antibiograme & generare rapoarte clinice</p>
                </div>
            </div>
            <div class="flex items-center space-x-3">
                <button onclick="window.print()" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white text-xs font-semibold rounded-xl shadow-md transition-all flex items-center gap-2">
                    <i data-lucide="printer" class="w-4 h-4"></i>
                    Printează Raport (PDF)
                </button>
            </div>
        </div>
    </header>

    <!-- Content Container -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 py-6 sm:px-6 lg:px-8 space-y-6">

        <!-- STEP 1: Patient Data & Organism Selection Panel (No Print) -->
        <section class="bg-white rounded-2xl shadow-sm border border-slate-200 p-5 sm:p-6 no-print">
            <div class="flex items-center justify-between border-b border-slate-100 pb-3 mb-4">
                <div class="flex items-center space-x-2">
                    <div class="w-7 h-7 rounded-lg bg-blue-50 text-blue-600 font-bold flex items-center justify-center text-xs">1</div>
                    <h2 class="text-base font-bold text-slate-900">Date Pacient & Selecție Organism Target</h2>
                </div>
                <span class="text-xs text-slate-400 italic">Selectarea organismului încarcă automat panoul de antibiogramă</span>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-12 gap-4">
                <!-- Patient Name -->
                <div class="md:col-span-3">
                    <label class="block text-xs font-semibold text-slate-600 mb-1 uppercase tracking-wider">Nume Pacient / CNP</label>
                    <input type="text" id="patientName" placeholder="ex: Popescu Ion / 1850..." class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2 text-sm focus:ring-2 focus:ring-blue-500 focus:bg-white transition-all">
                </div>

                <!-- Sample Type -->
                <div class="md:col-span-3">
                    <label class="block text-xs font-semibold text-slate-600 mb-1 uppercase tracking-wider">Tip Probă Biologică</label>
                    <select id="sampleType" class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2 text-sm focus:ring-2 focus:ring-blue-500 focus:bg-white transition-all">
                        <option value="Urocultură">Urocultură</option>
                        <option value="Hemocultură">Hemocultură</option>
                        <option value="Exudat / Secretie">Exudat / Secreție Faringiană/Purulentă</option>
                        <option value="Aspirat Bronșic / Spută">Aspirat Bronșic / Spută</option>
                        <option value="Lichid Cefalorahidian (LCR)">Lichid Cefalorahidian (LCR)</option>
                        <option value="Plagă / Secretie Purulentă">Plagă / Secreție Purulentă</option>
                        <option value="Altele">Altele</option>
                    </select>
                </div>

                <!-- Sample Code/Date -->
                <div class="md:col-span-2">
                    <label class="block text-xs font-semibold text-slate-600 mb-1 uppercase tracking-wider">ID Probă / Data</label>
                    <input type="text" id="sampleId" placeholder="ex: #9842 / 12.11" class="w-full bg-slate-50 border border-slate-300 rounded-xl px-3 py-2 text-sm focus:ring-2 focus:ring-blue-500 focus:bg-white transition-all">
                </div>

                <!-- ORGANISM SELECT -->
                <div class="md:col-span-4">
                    <label class="block text-xs font-bold text-blue-700 mb-1 uppercase tracking-wider flex items-center gap-1">
                        <i data-lucide="bug" class="w-3.5 h-3.5"></i> Microorganism Izolat *
                    </label>
                    <select id="organismSelect" onchange="loadOrganismAntibiotics()" class="w-full bg-blue-50/60 border-2 border-blue-400 text-blue-950 font-bold italic rounded-xl px-3 py-2 text-sm focus:ring-2 focus:ring-blue-600 transition-all cursor-pointer">
                        <!-- Populated dynamically -->
                    </select>
                </div>
            </div>
        </section>

        <!-- STEP 2: Batch Entry Form (No Print) -->
        <section class="bg-white rounded-2xl shadow-sm border border-slate-200 p-5 sm:p-6 no-print space-y-4">
            <div class="flex flex-col sm:flex-row justify-between sm:items-center border-b border-slate-100 pb-3 gap-2">
                <div class="flex items-center space-x-2">
                    <div class="w-7 h-7 rounded-lg bg-blue-50 text-blue-600 font-bold flex items-center justify-center text-xs">2</div>
                    <div>
                        <h2 class="text-base font-bold text-slate-900">Introducere Valori Antibiogramă (Batch Entry)</h2>
                        <p class="text-xs text-slate-500">Completați diametrul în mm sau CMI în mg/L pentru antibioticele dorite</p>
                    </div>
                </div>

                <!-- Global Mode Switcher -->
                <div class="flex items-center space-x-2 bg-slate-100 p-1 rounded-xl border border-slate-200 text-xs">
                    <span class="text-slate-500 font-medium px-2">Mod implicit:</span>
                    <button type="button" id="globalModeZone" onclick="setGlobalMode('zone')" class="px-3 py-1 rounded-lg font-bold bg-white text-blue-700 shadow-sm transition-all">
                        Diametru (mm)
                    </button>
                    <button type="button" id="globalModeMic" onclick="setGlobalMode('mic')" class="px-3 py-1 rounded-lg font-bold text-slate-600 hover:text-slate-900 transition-all">
                        CMI (mg/L)
                    </button>
                </div>
            </div>

            <!-- Dynamic Antibiotics Grid / List -->
            <div id="antibioticBatchContainer" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-3">
                <!-- Dynamic cards populated via JS -->
            </div>

            <!-- Add Custom Antibiotic Button & Generate Report CTA -->
            <div class="pt-4 border-t border-slate-100 flex flex-col sm:flex-row justify-between items-center gap-3">
                <button type="button" onclick="openAddCustomAntibioticModal()" class="text-xs font-semibold text-blue-600 hover:text-blue-800 bg-blue-50 hover:bg-blue-100 px-3.5 py-2 rounded-xl border border-blue-200 transition-all flex items-center gap-1.5">
                    <i data-lucide="plus" class="w-4 h-4"></i> Adaugă un antibiotic suplimentar în listă
                </button>

                <button type="button" onclick="generateFinalReport()" class="w-full sm:w-auto bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-700 hover:to-teal-700 text-white font-bold px-6 py-2.5 rounded-xl shadow-lg shadow-emerald-600/20 transition-all flex items-center justify-center gap-2">
                    <i data-lucide="file-check" class="w-5 h-5"></i>
                    Generează / Actualizează Raport Final
                </button>
            </div>
        </section>

        <!-- STEP 3: FINAL EVALUATION REPORT (Printable) -->
        <section id="finalReportSection" class="bg-white rounded-2xl shadow-sm border border-slate-200 p-6 space-y-6 print-shadow-none">
            
            <!-- Report Header -->
            <div class="border-b border-slate-200 pb-5">
                <div class="flex justify-between items-start">
                    <div class="flex items-center space-x-3">
                        <div class="p-3 bg-blue-600 text-white rounded-xl font-bold">
                            <i data-lucide="clipboard-list" class="w-8 h-8"></i>
                        </div>
                        <div>
                            <h2 class="text-xl font-bold text-slate-900">BULETIN DE INTERPRETARE ANTIBIOGRAMĂ</h2>
                            <p class="text-xs font-medium text-slate-500">Conform Criteriilor și Breakpoint-urilor EUCAST</p>
                        </div>
                    </div>
                    <div class="text-right text-xs text-slate-500">
                        <p class="font-bold text-slate-800" id="reportDate">Data: --</p>
                        <p id="reportTime">Ora: --</p>
                    </div>
                </div>

                <!-- Patient Metadata Banner -->
                <div class="mt-4 grid grid-cols-2 sm:grid-cols-4 gap-3 bg-slate-50 p-3.5 rounded-xl border border-slate-200/80 text-xs">
                    <div>
                        <span class="text-slate-400 block font-medium">Pacient:</span>
                        <strong id="repPatientName" class="text-slate-800">Necompletat</strong>
                    </div>
                    <div>
                        <span class="text-slate-400 block font-medium">Tip Proba:</span>
                        <strong id="repSampleType" class="text-slate-800">Urocultură</strong>
                    </div>
                    <div>
                        <span class="text-slate-400 block font-medium">ID Probă:</span>
                        <strong id="repSampleId" class="text-slate-800">--</strong>
                    </div>
                    <div>
                        <span class="text-slate-400 block font-medium">Patogen Identificat:</span>
                        <strong id="repOrganism" class="text-blue-700 italic font-bold">--</strong>
                    </div>
                </div>
            </div>

            <!-- Table of Results -->
            <div class="overflow-x-auto">
                <table class="w-full text-left border-collapse">
                    <thead>
                        <tr class="border-b border-slate-300 bg-slate-100/70 text-[11px] font-bold uppercase tracking-wider text-slate-600">
                            <th class="py-3 px-3">Antibiotic</th>
                            <th class="py-3 px-3 text-center">Valoare Testată</th>
                            <th class="py-3 px-3 text-center">Categorie Clinică</th>
                            <th class="py-3 px-3 text-center">Breakpoints EUCAST</th>
                            <th class="py-3 px-3">Comentariu Clinic / Reguli de Expert</th>
                        </tr>
                    </thead>
                    <tbody id="reportTableBody" class="divide-y divide-slate-200 text-xs">
                        <tr>
                            <td colspan="5" class="py-10 text-center text-slate-400 italic">
                                Nu au fost introduse date. Completați valorile în formularul de mai sus și apăsați "Generează Raport Final".
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- Footer / Expert Notes -->
            <div class="pt-4 border-t border-slate-200 text-[11px] text-slate-500 space-y-2">
                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-2 bg-slate-50 p-3 rounded-xl border border-slate-200">
                    <div class="space-x-3">
                        <span class="inline-flex items-center gap-1 font-bold text-emerald-800"><span class="w-2.5 h-2.5 rounded-full bg-emerald-500"></span> S: Sensibil (Doză Standard)</span>
                        <span class="inline-flex items-center gap-1 font-bold text-amber-800"><span class="w-2.5 h-2.5 rounded-full bg-amber-500"></span> I: Sensibil (Expunere Crescută)</span>
                        <span class="inline-flex items-center gap-1 font-bold text-rose-800"><span class="w-2.5 h-2.5 rounded-full bg-rose-500"></span> R: Rezistent</span>
                    </div>
                    <span class="text-[10px] text-slate-400 italic">Sistem dezvoltat conform EUCAST Breakpoint Tables</span>
                </div>
                <p class="text-[10px] text-slate-400 leading-normal">
                    * Notă: Categoria **I** semnifică sensibilitate clinică atunci când expunerea la agentul antibacterian este crescută prin ajustarea regimului de dozare (doză mai mare, frecvență crescută) sau prin acumularea naturală la locul infecției (ex: tract urinar).
                </p>
            </div>
        </section>
    </main>

    <!-- DATABASE & LOGIC -->
    <script>
        // EXTENDED EUCAST DATABASE WITH ACCURATE BREAKPOINTS & COMMENTS
        const eucastDatabase = {
            "Escherichia coli": [
                { name: "Ampicilină", zone: { S: 14, R: 14 }, mic: { S: 8, R: 8 }, comment: "Inactivă pe tulpini producătoare de β-lactamaze. Raportați R dacă este ESBL." },
                { name: "Amoxicilină-ac. clavulanic (UTI)", zone: { S: 19, R: 19 }, mic: { S: 32, R: 32 }, comment: "Criterii valabile exclusiv pentru infecții urinare joase necomplicate." },
                { name: "Amoxicilină-ac. clavulanic (Sistemic)", zone: { S: 19, R: 19 }, mic: { S: 8, R: 8 }, comment: "Pentru infecții sistemice/parenchimatoase." },
                { name: "Piperacilină-tazobactam", zone: { S: 20, R: 20 }, mic: { S: 8, R: 16 }, comment: "Inactiv pe producători de carbapenemaze." },
                { name: "Cefotaxim", zone: { S: 22, R: 19 }, mic: { S: 1, R: 2 }, comment: "Zonă < 25 mm indică necesitatea screeningului ESBL." },
                { name: "Ceftriaxon", zone: { S: 25, R: 22 }, mic: { S: 1, R: 2 }, comment: "Marker principal de screening ESBL." },
                { name: "Ceftazidim", zone: { S: 22, R: 19 }, mic: { S: 1, R: 4 }, comment: "Evaluare rezistență cefalosporine gen. 3." },
                { name: "Cefepim", zone: { S: 27, R: 24 }, mic: { S: 1, R: 4 }, comment: "Cefalosporină gen. 4." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Diametru 16-21 mm necesită test confirmatoriu pentru Carbapenemaze." },
                { name: "Ertapenem", zone: { S: 25, R: 22 }, mic: { S: 0.5, R: 1 }, comment: "Cea mai sensibilă carbapenemă pentru screening de carbapenemaze." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Atenție la mutațiile de nivel scăzut gyrA/parC." },
                { name: "Levofloxacin", zone: { S: 22, R: 19 }, mic: { S: 0.5, R: 1 }, comment: "Fluoroquinolonă." },
                { name: "Gentamicină", zone: { S: 17, R: 17 }, mic: { S: 2, R: 2 }, comment: "Aminoglicozid." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid." },
                { name: "Tobramicină", zone: { S: 17, R: 17 }, mic: { S: 2, R: 2 }, comment: "Aminoglicozid." },
                { name: "Fosfomicină (doar UTI)", zone: { S: 24, R: 24 }, mic: { S: 8, R: 8 }, comment: "Aprobat exclusiv pentru cistite acute necomplicate." },
                { name: "Nitrofurantoină (doar UTI)", zone: { S: 11, R: 11 }, mic: { S: 64, R: 64 }, comment: "Limitat la infecții urinare necomplicate. Inactiv în pielonefrite." },
                { name: "Cotrimoxazol (SXT)", zone: { S: 16, R: 13 }, mic: { S: 2, R: 4 }, comment: "Trimetoprim-Sulfametoxazol." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "CRITICAL: Difuzia pe disc NU este validă pentru Colistină! Determinați doar CMI." }
            ],
            "Klebsiella pneumoniae": [
                { name: "Amoxicilină-ac. clavulanic", zone: { S: 18, R: 18 }, mic: { S: 8, R: 8 }, comment: "Inerent REZISTENTĂ la Ampicilină simplă (gene SHV chromozomiale)." },
                { name: "Piperacilină-tazobactam", zone: { S: 20, R: 20 }, mic: { S: 8, R: 16 }, comment: "Evaluare infecții severe." },
                { name: "Ceftazidim", zone: { S: 22, R: 19 }, mic: { S: 1, R: 4 }, comment: "Evaluare ESBL / AmpC." },
                { name: "Ceftriaxon", zone: { S: 25, R: 22 }, mic: { S: 1, R: 2 }, comment: "Cefalosporină gen. 3." },
                { name: "Cefepim", zone: { S: 27, R: 24 }, mic: { S: 1, R: 4 }, comment: "Cefalosporină gen. 4." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Verificați producătorii de KPC, NDM sau OXA-48 dacă zona < 22 mm." },
                { name: "Ertapenem", zone: { S: 25, R: 22 }, mic: { S: 0.5, R: 1 }, comment: "Screening carbapenemaze." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Fluoroquinolonă." },
                { name: "Gentamicină", zone: { S: 17, R: 17 }, mic: { S: 2, R: 2 }, comment: "Aminoglicozid." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid de elecție pentru izolate multirezistente." },
                { name: "Cotrimoxazol (SXT)", zone: { S: 16, R: 13 }, mic: { S: 2, R: 4 }, comment: "Trimetoprim-Sulfametoxazol." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "CRITICAL: Difuzia pe disc NU este validă pentru Colistină! Determinați doar CMI." }
            ],
            "Klebsiella oxytoca": [
                { name: "Amoxicilină-ac. clavulanic", zone: { S: 18, R: 18 }, mic: { S: 8, R: 8 }, comment: "Inerent rezistentă la ampicilină (producție de K1 β-lactamază)." },
                { name: "Cefotaxim", zone: { S: 22, R: 19 }, mic: { S: 1, R: 2 }, comment: "Supraexprimarea K1 poate da rezistență la Cefuroxim/Aztreonam." },
                { name: "Ceftriaxon", zone: { S: 25, R: 22 }, mic: { S: 1, R: 2 }, comment: "Cefalosporină gen. 3." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Fluoroquinolonă." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid." }
            ],
            "Proteus mirabilis": [
                { name: "Ampicilină", zone: { S: 14, R: 14 }, mic: { S: 8, R: 8 }, comment: "Sensibilă natural la ampicilină (spre deosebire de Proteus vulgaris)." },
                { name: "Amoxicilină-ac. clavulanic", zone: { S: 19, R: 19 }, mic: { S: 8, R: 8 }, comment: "Inhibitor de beta-lactamază." },
                { name: "Ceftriaxon", zone: { S: 25, R: 22 }, mic: { S: 1, R: 2 }, comment: "Cefalosporină gen. 3." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Fluoroquinolonă." },
                { name: "Nitrofurantoină", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL: Proteus spp. sunt inerent rezistente la Nitrofurantoină." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL: Proteus spp. sunt inerent rezistente la Colistină." }
            ],
            "Enterobacter cloacae complex": [
                { name: "Ampicilină / Augmentin", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL datorită β-lactamazei AmpC cromozomiale inductibile." },
                { name: "Cefotaxim / Ceftriaxon", zone: { S: 22, R: 19 }, mic: { S: 1, R: 2 }, comment: "Risc de selectare a mutanților dereprimați AmpC în timpul terapiei." },
                { name: "Cefepim", zone: { S: 27, R: 24 }, mic: { S: 1, R: 4 }, comment: "Opțiune preferată dintre cefalosporine (stabilă la AmpC)." },
                { name: "Piperacilină-tazobactam", zone: { S: 20, R: 20 }, mic: { S: 8, R: 16 }, comment: "Utilizați cu precauție în infecții cu încărcătură bacteriană mare." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenemă de elecție." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Fluoroquinolonă." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid." }
            ],
            "Citrobacter freundii": [
                { name: "Ampicilină / Augmentin", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL (AmpC cromozomial)." },
                { name: "Cefepim", zone: { S: 27, R: 24 }, mic: { S: 1, R: 4 }, comment: "Stabil la AmpC." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Ciprofloxacin", zone: { S: 25, R: 22 }, mic: { S: 0.25, R: 0.5 }, comment: "Fluoroquinolonă." }
            ],
            "Morganella morganii": [
                { name: "Ampicilină / Augmentin", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL (AmpC cromozomial)." },
                { name: "Ceftriaxon", zone: { S: 25, R: 22 }, mic: { S: 1, R: 2 }, comment: "Cefalosporină gen. 3." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Colistină / Nitrofurantoină", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL la Colistină și Nitrofurantoină." }
            ],
            "Serratia marcescens": [
                { name: "Ampicilină / Augmentin", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL (AmpC cromozomial)." },
                { name: "Cefepim", zone: { S: 27, R: 24 }, mic: { S: 1, R: 4 }, comment: "Stabil la AmpC." },
                { name: "Meropenem", zone: { S: 22, R: 16 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL la Colistină." }
            ],
            "Pseudomonas aeruginosa": [
                { name: "Piperacilină-tazobactam", zone: { S: 18, R: 18 }, mic: { S: 16, R: 16 }, comment: "Doza standard este ridicată (4g x 4/zi)." },
                { name: "Ceftazidim", zone: { S: 17, R: 17 }, mic: { S: 8, R: 8 }, comment: "Agent anti-pseudomonas principal." },
                { name: "Cefepim", zone: { S: 18, R: 18 }, mic: { S: 8, R: 8 }, comment: "Necesită doze crescute (2g x 3/zi)." },
                { name: "Meropenem", zone: { S: 24, R: 18 }, mic: { S: 2, R: 8 }, comment: "Risc de selectare a rezistenței prin porina OprD în timpul terapiei." },
                { name: "Ciprofloxacin", zone: { S: 26, R: 26 }, mic: { S: 0.5, R: 0.5 }, comment: "Singurul antipseudomonas cu administrare orală." },
                { name: "Tobramicină", zone: { S: 17, R: 17 }, mic: { S: 2, R: 2 }, comment: "Mai activă decât gentamicina pe P. aeruginosa." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "CRITICAL: Difuzia pe disc NU este validă pentru Colistină! Determinați doar CMI." }
            ],
            "Acinetobacter baumannii complex": [
                { name: "Meropenem", zone: { S: 21, R: 15 }, mic: { S: 2, R: 8 }, comment: "Carbapenemă de elecție." },
                { name: "Imipenem", zone: { S: 23, R: 17 }, mic: { S: 2, R: 8 }, comment: "Carbapenem." },
                { name: "Amikacină", zone: { S: 18, R: 15 }, mic: { S: 8, R: 16 }, comment: "Aminoglicozid." },
                { name: "Gentamicină", zone: { S: 17, R: 14 }, mic: { S: 4, R: 8 }, comment: "Aminoglicozid." },
                { name: "Ciprofloxacin", zone: { S: 21, R: 18 }, mic: { S: 1, R: 2 }, comment: "Fluoroquinolonă." },
                { name: "Cotrimoxazol (SXT)", zone: { S: 19, R: 16 }, mic: { S: 2, R: 4 }, comment: "Trimetoprim-Sulfametoxazol." },
                { name: "Colistină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "CRITICAL: Doar determinarea CMI este validă conform EUCAST." }
            ],
            "Stenotrophomonas maltophilia": [
                { name: "Cotrimoxazol (SXT)", zone: { S: 16, R: 16 }, mic: { S: 4, R: 4 }, comment: "Tratament de elecție de primă linie." },
                { name: "Levofloxacin", zone: { S: 19, R: 19 }, mic: { S: 2, R: 2 }, comment: "Opțiune alternativă conform CLSI." },
                { name: "Carbapeneme / Beta-lactame", zone: { S: 0, R: 0 }, mic: { S: 0, R: 0 }, comment: "REZISTENT NATURAL la Carbapeneme (producție de metallo-beta-lactamază L1)." }
            ],
            "Staphylococcus aureus": [
                { name: "Cefoxitin (Screening MRSA)", zone: { S: 22, R: 22 }, mic: { S: 4, R: 4 }, comment: "SURROGAT MRSA: Zona ≥22mm indica MSSA (Sensibil la Oxacilină, Augmentin, Carbapeneme)." },
                { name: "Penicilină G", zone: { S: 26, R: 26 }, mic: { S: 0.12, R: 0.12 }, comment: "Verificați dacă marginea zonei este netedă/abruptă (cliff zone = penicillinase +)." },
                { name: "Eritromicină", zone: { S: 23, R: 18 }, mic: { S: 1, R: 2 }, comment: "Dacă este Rezistent, efectuați D-Test pentru rezistență inductibilă la Clindamicină." },
                { name: "Clindamicină", zone: { S: 22, R: 19 }, mic: { S: 0.25, R: 0.5 }, comment: "Urmăriți fenomenul de aplatizare a zonei (D-Test pozitiv)." },
                { name: "Ciprofloxacin", zone: { S: 20, R: 20 }, mic: { S: 1, R: 1 }, comment: "Nu se folosește ca monoterapie în infecții severe." },
                { name: "Gentamicină", zone: { S: 18, R: 18 }, mic: { S: 1, R: 1 }, comment: "Aminoglicozid." },
                { name: "Vancomicină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "CRITICAL: Difuzia pe disc ESTE INVALIDĂ pentru Vancomicină la Stafilococ. Determinați doar CMI!" },
                { name: "Teicoplanină", zone: { S: 0, R: 0 }, mic: { S: 2, R: 2 }, comment: "Determinați CMI conform ghidului EUCAST." },
                { name: "Linezolid", zone: { S: 21, R: 21 }, mic: { S: 4, R: 4 }, comment: "Activ pe tulpini MRSA." },
                { name: "Rifampicină", zone: { S: 26, R: 22 }, mic: { S: 0.06, R: 0.5 }, comment: "Utilizat exclusiv în combinații (ex: infecții de proteză)." },
                { name: "Cotrimoxazol (SXT)", zone: { S: 17, R: 14 }, mic: { S: 2, R: 4 }, comment: "Opțiune orală excelentă pentru MRSA." }
            ],
            "Staphylococcus epidermidis / Lugdunensis": [
                { name: "Cefoxitin (Screening MRSE)", zone: { S: 25, R: 25 }, mic: { S: 4, R: 4 }, comment: "Breakpoints de screening specifice Stafilococilor Coagulazo-Negativi (CoNS)." },
                { name: "Eritromicină", zone: { S: 23, R: 18 }, mic: { S: 1, R: 2 }, comment: "Macrolid." },
                { name: "Clindamicină", zone: { S: 22, R: 19 }, mic: { S: 0.25, R: 0.5 }, comment: "Lincosamidă." },
                { name: "Vancomicină", zone: { S: 0, R: 0 }, mic: { S: 4, R: 4 }, comment: "Difuzia pe disc invalidă; determinați doar CMI." },
                { name: "Linezolid", zone: { S: 21, R: 21 }, mic: { S: 4, R: 4 }, comment: "Oxazolidinonă." }
            ],
            "Enterococcus faecalis": [
                { name: "Ampicilină", zone: { S: 10, R: 10 }, mic: { S: 4, R: 8 }, comment: "Inerent REZISTENT la Cefalosporine, Clindamicină, Cotrimoxazol!" },
                { name: "Vancomicină", zone: { S: 12, R: 12 }, mic: { S: 4, R: 4 }, comment: "Zona < 12mm indică suspiciune de VRE (fenotip vanA/vanB)." },
                { name: "Teicoplanină", zone: { S: 16, R: 16 }, mic: { S: 2, R: 2 }, comment: "Diferențiere fenotip vanA (R la teicoplanină) vs vanB." },
                { name: "Gentamicină (High-Level HLAR)", zone: { S: 8, R: 8 }, mic: { S: 128, R: 128 }, comment: "Test de sinergie cu bactericide pe perete celular." },
                { name: "Linezolid", zone: { S: 20, R: 20 }, mic: { S: 4, R: 4 }, comment: "Activ pe tulpini VRE." },
                { name: "Nitrofurantoină (doar UTI)", zone: { S: 15, R: 15 }, mic: { S: 64, R: 64 }, comment: "Aprobat pentru cistite necomplicate." }
            ],
            "Enterococcus faecium": [
                { name: "Ampicilină", zone: { S: 8, R: 8 }, mic: { S: 4, R: 4 }, comment: "Majoritatea tulpinilor de E. faecium sunt rezistente la Ampicilină." },
                { name: "Vancomicină", zone: { S: 12, R: 12 }, mic: { S: 4, R: 4 }, comment: "Evaluare VRE." },
                { name: "Teicoplanină", zone: { S: 16, R: 16 }, mic: { S: 2, R: 2 }, comment: "Glicopeptid." },
                { name: "Linezolid", zone: { S: 20, R: 20 }, mic: { S: 4, R: 4 }, comment: "Agent de rezervă pentru VRE." }
            ],
            "Streptococcus pneumoniae": [
                { name: "Oxacilină 1µg (Screening Penicilină)", zone: { S: 20, R: 20 }, mic: { S: 0.06, R: 0.06 }, comment: "Zone ≥20mm confirmă sensibilitatea la Penicilină și Amoxicilină." },
                { name: "Penicilină G (Meningită)", zone: { S: 0, R: 0 }, mic: { S: 0.06, R: 0.06 }, comment: "În meningită, CMI > 0.06 mg/L se raportează Rezistent." },
                { name: "Penicilină G (Non-Meningită)", zone: { S: 0, R: 0 }, mic: { S: 0.5, R: 2 }, comment: "În infecții respiratorii, CMI ≤ 0.5 mg/L este Sensibil." },
                { name: "Ceftriaxon", zone: { S: 26, R: 23 }, mic: { S: 0.5, R: 2 }, comment: "Cefalosporină gen. 3." },
                { name: "Eritromicină", zone: { S: 22, R: 19 }, mic: { S: 0.25, R: 0.5 }, comment: "Predice rezistența la Azitromicină și Claritromicină." },
                { name: "Levofloxacin", zone: { S: 19, R: 16 }, mic: { S: 2, R: 2 }, comment: "Fluoroquinolonă respiratorie." },
                { name: "Vancomicină", zone: { S: 12, R: 12 }, mic: { S: 2, R: 2 }, comment: "Glicopeptid." }
            ],
            "Streptococcus pyogenes (Grup A)": [
                { name: "Penicilină V / G", zone: { S: 18, R: 18 }, mic: { S: 0.25, R: 0.25 }, comment: "Sensibil universal! Nu s-a documentat rezistență clinică la Penicilină." },
                { name: "Eritromicină", zone: { S: 21, R: 18 }, mic: { S: 0.25, R: 0.5 }, comment: "Macrolid." },
                { name: "Clindamicină", zone: { S: 19, R: 19 }, mic: { S: 0.5, R: 0.5 }, comment: "Lincosamidă (inclusiv efect anti-toxinic în fasciită necrozantă)." }
            ],
            "Streptococcus agalactiae (Grup B)": [
                { name: "Penicilină G", zone: { S: 18, R: 18 }, mic: { S: 0.25, R: 0.25 }, comment: "Sensibil universal la peniciline." },
                { name: "Eritromicină", zone: { S: 21, R: 18 }, mic: { S: 0.25, R: 0.5 }, comment: "Testare recomandată la paciente alergice la penicilină." },
                { name: "Clindamicină", zone: { S: 19, R: 19 }, mic: { S: 0.5, R: 0.5 }, comment: "Testare D-test dacă eritromicina este rezistentă." },
                { name: "Vancomicină", zone: { S: 12, R: 12 }, mic: { S: 2, R: 2 }, comment: "Alternativă în caz de anafilaxie la beta-lactame." }
            ]
        };

        // State Global
        let globalMode = 'zone'; // 'zone' sau 'mic'
        let currentAntibioticsList = [];

        // DOM Loaded Init
        window.addEventListener('DOMContentLoaded', () => {
            initOrganismSelect();
            setCurrentDate();
            lucide.createIcons();
        });

        function setCurrentDate() {
            const now = new Date();
            document.getElementById('reportDate').textContent = `Data: ${now.toLocaleDateString('ro-RO')}`;
            document.getElementById('reportTime').textContent = `Ora: ${now.toLocaleTimeString('ro-RO', {hour: '2-digit', minute:'2-digit'})}`;
        }

        function initOrganismSelect() {
            const select = document.getElementById('organismSelect');
            select.innerHTML = '';
            Object.keys(eucastDatabase).forEach(org => {
                const opt = document.createElement('option');
                opt.value = org;
                opt.textContent = org;
                select.appendChild(opt);
            });
            loadOrganismAntibiotics();
        }

        function setGlobalMode(mode) {
            globalMode = mode;
            document.getElementById('globalModeZone').className = mode === 'zone' 
                ? "px-3 py-1 rounded-lg font-bold bg-white text-blue-700 shadow-sm transition-all"
                : "px-3 py-1 rounded-lg font-bold text-slate-600 hover:text-slate-900 transition-all";
            
            document.getElementById('globalModeMic').className = mode === 'mic' 
                ? "px-3 py-1 rounded-lg font-bold bg-white text-blue-700 shadow-sm transition-all"
                : "px-3 py-1 rounded-lg font-bold text-slate-600 hover:text-slate-900 transition-all";

            currentAntibioticsList.forEach(item => item.mode = mode);
            renderBatchForm();
        }

        function loadOrganismAntibiotics() {
            const org = document.getElementById('organismSelect').value;
            const atbs = eucastDatabase[org] || [];
            
            currentAntibioticsList = atbs.map((atb, idx) => ({
                id: idx,
                ...atb,
                mode: globalMode,
                value: ''
            }));

            renderBatchForm();
        }

        function renderBatchForm() {
            const container = document.getElementById('antibioticBatchContainer');
            container.innerHTML = '';

            currentAntibioticsList.forEach((atb, index) => {
                const evalRes = evaluateAntibiotic(atb);

                const card = document.createElement('div');
                card.className = "p-3.5 rounded-xl border border-slate-200 bg-slate-50/50 hover:bg-white hover:border-blue-200 transition-all space-y-2";
                
                let badgeClass = "bg-slate-200 text-slate-600";
                if (evalRes.code === 'S') badgeClass = "bg-emerald-500 text-white font-bold";
                else if (evalRes.code === 'I') badgeClass = "bg-amber-500 text-white font-bold";
                else if (evalRes.code === 'R') badgeClass = "bg-rose-600 text-white font-bold";
                else if (evalRes.code === 'INVALID') badgeClass = "bg-purple-600 text-white font-bold";

                card.innerHTML = `
                    <div class="flex justify-between items-start">
                        <span class="font-bold text-xs text-slate-800">${atb.name}</span>
                        <span id="badge-${index}" class="px-2 py-0.5 rounded text-[10px] uppercase tracking-wider ${badgeClass}">
                            ${evalRes.code || 'NO VAL'}
                        </span>
                    </div>

                    <div class="flex items-center space-x-2">
                        <div class="relative flex-grow">
                            <input type="number" step="any" min="0" 
                                value="${atb.value}" 
                                placeholder="${atb.mode === 'zone' ? 'mm' : 'mg/L'}"
                                oninput="onAntibioticInput(${index}, this.value)"
                                class="w-full bg-white border border-slate-300 rounded-lg px-2.5 py-1.5 text-xs font-mono font-bold text-slate-800 focus:ring-2 focus:ring-blue-500 focus:outline-none">
                            <span class="absolute right-2 top-1.5 text-[10px] text-slate-400 font-sans font-bold">${atb.mode === 'zone' ? 'mm' : 'mg/L'}</span>
                        </div>

                        <button type="button" onclick="toggleLocalMode(${index})" class="px-2 py-1 text-[10px] bg-slate-200 hover:bg-slate-300 text-slate-700 font-semibold rounded-md transition-all">
                            ${atb.mode === 'zone' ? 'Switch CMI' : 'Switch Disc'}
                        </button>
                    </div>

                    <div class="text-[10px] text-slate-400 flex justify-between">
                        <span>Disc: ${atb.zone.S === 0 ? 'N/A' : `S≥${atb.zone.S} R<${atb.zone.R}`}</span>
                        <span>CMI: ${atb.mic.S === 0 ? 'N/A' : `S≤${atb.mic.S} R>${atb.mic.R}`}</span>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function toggleLocalMode(index) {
            currentAntibioticsList[index].mode = currentAntibioticsList[index].mode === 'zone' ? 'mic' : 'zone';
            renderBatchForm();
        }

        function onAntibioticInput(index, val) {
            currentAntibioticsList[index].value = val;
            const evalRes = evaluateAntibiotic(currentAntibioticsList[index]);
            
            const badge = document.getElementById(`badge-${index}`);
            if (badge) {
                badge.textContent = evalRes.code || 'NO VAL';
                badge.className = "px-2 py-0.5 rounded text-[10px] uppercase tracking-wider ";
                if (evalRes.code === 'S') badge.className += "bg-emerald-500 text-white font-bold";
                else if (evalRes.code === 'I') badge.className += "bg-amber-500 text-white font-bold";
                else if (evalRes.code === 'R') badge.className += "bg-rose-600 text-white font-bold";
                else if (evalRes.code === 'INVALID') badge.className += "bg-purple-600 text-white font-bold";
                else badge.className += "bg-slate-200 text-slate-600";
            }
        }

        function evaluateAntibiotic(atb) {
            const val = parseFloat(atb.value);
            if (isNaN(val) || val < 0 || atb.value === '') {
                return { code: '', category: 'Necompletat', comment: atb.comment };
            }

            if (atb.mode === 'zone') {
                if (atb.zone.S === 0 && atb.zone.R === 0) {
                    return {
                        code: 'INVALID',
                        category: 'Metodă Invalida / Inerent R',
                        comment: atb.comment || 'EUCAST: Difuzia pe disc NU este validă. Determinați CMI sau microorganismul este inerent rezistent.'
                    };
                }
                if (val >= atb.zone.S) return { code: 'S', category: 'Sensibil', comment: atb.comment };
                if (val < atb.zone.R) return { code: 'R', category: 'Rezistent', comment: atb.comment };
                return { code: 'I', category: 'Sensibil expunere crescută', comment: atb.comment };
            } else { // CMI Mode
                if (atb.mic.S === 0 && atb.mic.R === 0) {
                    return {
                        code: 'R',
                        category: 'Rezistent Natural',
                        comment: atb.comment
                    };
                }
                if (val <= atb.mic.S) return { code: 'S', category: 'Sensibil', comment: atb.comment };
                if (val > atb.mic.R) return { code: 'R', category: 'Rezistent', comment: atb.comment };
                return { code: 'I', category: 'Sensibil expunere crescută', comment: atb.comment };
            }
        }

        function openAddCustomAntibioticModal() {
            const name = prompt("Introduceți numele noului antibiotic de adăugat:");
            if (!name) return;
            
            const sZone = parseFloat(prompt("Break-point Sensibil ZONĂ (mm) [ex: 20] (Introduceți 0 dacă nu e aplicabil):", "20")) || 0;
            const rZone = parseFloat(prompt("Break-point Rezistent ZONĂ (mm) [ex: 17] (Introduceți 0 dacă nu e aplicabil):", "17")) || 0;
            const sMic = parseFloat(prompt("Break-point Sensibil CMI (mg/L) [ex: 1]:", "1")) || 1;
            const rMic = parseFloat(prompt("Break-point Rezistent CMI (mg/L) [ex: 4]:", "4")) || 4;
            const comment = prompt("Comentariu clinic sau regulă de expert (opțional):", "Adăugat manual") || "";

            currentAntibioticsList.push({
                id: Date.now(),
                name: name,
                zone: { S: sZone, R: rZone },
                mic: { S: sMic, R: rMic },
                comment: comment,
                mode: globalMode,
                value: ''
            });

            renderBatchForm();
        }

        function generateFinalReport() {
            document.getElementById('repPatientName').textContent = document.getElementById('patientName').value.trim() || 'Necompletat';
            document.getElementById('repSampleType').textContent = document.getElementById('sampleType').value;
            document.getElementById('repSampleId').textContent = document.getElementById('sampleId').value.trim() || '--';
            document.getElementById('repOrganism').textContent = document.getElementById('organismSelect').value;

            const tbody = document.getElementById('reportTableBody');
            tbody.innerHTML = '';

            const populated = currentAntibioticsList.filter(a => a.value !== '' && !isNaN(parseFloat(a.value)));

            if (populated.length === 0) {
                tbody.innerHTML = `
                    <tr>
                        <td colspan="5" class="py-10 text-center text-slate-400 italic">
                            Nu s-a completat nicio valoare. Introduceți cel puțin o valoare în formularul de mai sus.
                        </td>
                    </tr>
                `;
                return;
            }

            populated.forEach(item => {
                const res = evaluateAntibiotic(item);
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition-colors";

                let badgeColor = "";
                if (res.code === 'S') badgeColor = "bg-emerald-100 text-emerald-800 border-emerald-300";
                else if (res.code === 'I') badgeColor = "bg-amber-100 text-amber-800 border-amber-300";
                else if (res.code === 'R') badgeColor = "bg-rose-100 text-rose-800 border-rose-300";
                else badgeColor = "bg-purple-100 text-purple-800 border-purple-300";

                const bpString = item.mode === 'zone' 
                    ? (item.zone.S === 0 ? "Disc invalid (Doar CMI)" : `S ≥ ${item.zone.S} mm | R < ${item.zone.R} mm`)
                    : (item.mic.S === 0 ? "Inerent Rezistent" : `S ≤ ${item.mic.S} mg/L | R > ${item.mic.R} mg/L`);

                tr.innerHTML = `
                    <td class="py-3 px-3 font-bold text-slate-800">${item.name}</td>
                    <td class="py-3 px-3 text-center font-mono font-bold text-slate-900">
                        ${item.value} <span class="text-[10px] font-sans text-slate-500 font-normal">${item.mode === 'zone' ? 'mm' : 'mg/L'}</span>
                    </td>
                    <td class="py-3 px-3 text-center">
                        <span class="inline-block px-3 py-1 font-bold rounded-lg border text-xs ${badgeColor}">
                            ${res.code} - ${res.category}
                        </span>
                    </td>
                    <td class="py-3 px-3 text-center text-[11px] text-slate-500 font-mono">${bpString}</td>
                    <td class="py-3 px-3 text-[11px] text-slate-600 leading-relaxed max-w-xs">${res.comment}</td>
                `;
                tbody.appendChild(tr);
            });

            document.getElementById('finalReportSection').scrollIntoView({ behavior: 'smooth' });
        }
    </script>
</body>
</html>
