# PHYSIS

**Pediatric Height Yielded through Skeletal Interpretation System**

Pediatric endocrine clinical decision support — bone age scoring, adult height prediction, growth charting, and additional calculators for inpatient and outpatient practice. PHYSIS is a **standalone application built from scratch** for pediatric endocrinology workflows. 

**Inspiration**

PHYSIS draws on published methods and clinical references with its main focus of making important clinical tools available and easily accessible. While entirely developed by myself, PHYSIS takes inspiration from [Bone Age](https://play.google.com/store/apps/details?id=uk.co.eatyourpeas.tannerwhitehouse) and [endocrinologist](https://github.com/eatyourpeas/endocrinologist), both developed by [eatyourpeas](https://github.com/eatyourpeas). Inspiration for additional clinical tools from [Child Metrics](https://www.ceddcozum.com/), developed and maintained by the Turkish Society for Pediatric Endocrinology and Diabetes (TSPED).

**Disclaimer**

Please be sure to read the [Disclaimer](https://calc.dom.doctor/disclaimer) and [Terms of Use](ToU.md) before using PHYSIS.

**P.H.Y.S.I.S. Production:** [https://calc.dom.doctor](https://calc.dom.doctor)

**Current release:** **v0.8.2** (28 Aug 2026) — Disclaimer and Terms of Use pages sync from repo markdown.

## Primary workflow: growth & height prediction

The main workflow (`/growth`) guides TW3-RUS bone age scoring through adult height prediction and CDC growth chart visualization.


| Step                 | Feature                                                                                                                                                                                                                        |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **TW3 bone age**     | Hand-navigator scoring for all 13 RUS landmarks with per-stage drawings and criteria text (individual atlas PNGs + markdown descriptions), discrete stage slider, and SMS → bone age lookup (sex-specific Tables A1/A3, A5/A6) |
| **Parental stature** | Father/mother heights (cm, in, or ft+in) or direct MPH entry; distinguishes **MPH** (Tanner, TW3) from **MPS** (parental average, adjusted RWT & Khamis-Roche)                                                                 |
| **APH methods**      | Bone-age mode: **TW3**, **adjusted RWT**, **original RWT**. No-bone-age mode: **Khamis-Roche** only. Missing-input checklists on result cards before calculation.                                                              |
| **CDC growth chart** | Plots stature and weight vs chronological age and bone-age–shifted age; overlays MPH/MPS and selected predicted adult height                                                                                                   |
| **Show work / QC**   | Audit trail of inputs, coefficient lookup, landmark scoring, and discrepancy flags (`ShowWorkSection`)                                                                                                                         |
| **Clinical copy**    | Configurable charting summary with method references and TW3 atlas citations                                                                                                                                                   |




## Other calculators -- C.A.L.C.S.

**C**omprehensive **A**ction-**L**everaging **C**alculator **S**uite

### Adrenals/ Sex Steroids (`/calculators/adrenal`)

| Tool | Route |
| --- | --- |
| BSA (Haycock or Costeff weight-only) & steroid potency wean/converter | `/bsa-steroid` |
| 17OHP Intrepretation in Prematurity (Olgemöller 2003 and Pode-Shakked 2018) | `/cah-screening` |
| XY DSD Steroid Panel — post-hCG T/DHT, T/Δ4A, ASI; Esoterix T/DHT/Δ4A conversion | `/xy-dsd-steroid-panel` |

### Bone Health (`/calculators/bone-health`)

| Tool | Route |
| --- | --- |
| Renal electrolyte indices (TRP, CCR, spot UCa/UCr, TTKG) | `/renal-electrolytes` |
| Calcium dosing (enteral / parenteral) | `/calcium-dosing` |
| Figueras-Aloy MBDP risk-score | `/figueras-aloy-mbdp` |
| DXA BMD Interpretation | `/dxa-bmd-interpretation` |
| Bone Turnover labs | Coming soon |

Legacy routes `/trp` and `/ccr` redirect to `/renal-electrolytes`.

### Diabetes (`/calculators/diabetes`)

| Tool | Route |
| --- | --- |
| A1c ↔ GMI ↔ fructosamine ↔ eAG (Cohen et al. preferred; Young et al. alternate) | `/a1c-converter` |
| Insulin MDI → sliding scale (ISS) | `/insulin-mdi-iss` |
| Diluted ISS generation | `/insulin-diluted-iss` |
| TDD estimator and MDI calculator — bolus (½/whole U) or TDD / % basal / ISF / ICR | `/tdd-mdi` |
| Insulin Resistant Indices — HOMA-IR, QUICKI, SPISE, Matsuda (optional OGTT) | `/insulin-resistant-indices` |
| MODY Clinical Calculator — at diagnosis (age &lt; 20) or Exeter post-6-month PPV (≤35 y) | `/mody-clinical-calculator` |
| Glycemia Risk Index (GRI) Calculator — AGP % → TIR, GRI, hypo/hyper components, zones A–E | `/glycemia-risk-index` |

### Electrolytes/Fluids (`/calculators/electrolytes`)

| Tool | Route |
| --- | --- |
| Sodium balance & replacement (FWD, hypo/hypernatremia infusion guidance) | `/sodium-balance` |
| Hyperglycemia sodium correction | `/hyperglycemia-sodium-correction` |
| Calcium correction for albumin | `/calcium-albumin` |
| Maintenance IVF (Holliday–Segar) | `/maintenance-ivf` |
| Glucose infusion rate — IV and enteral | `/gir` |

### Gonad Auxology (`/calculators/gonad-auxology`)

| Tool | Route |
| --- | --- |
| Stretched penile length (newborn) — Halil et al. and Feldman/Aaronson nomograms | `/spl-newborn` |
| Stretched penile length (child) — Bulgarian, Schonfeld, and Feldman references | `/spl-child` |
| Clitoral length/width (neonate) — Alaei et al. nomogram | `/clitoral-dimension` |
| Uterine / ovarian SDS — Gilligan 2019 pelvic US mean±SD | `/uterine-ovary-sds` |

Legacy route `/calculators/normograms` redirects to `/calculators/gonad-auxology`.

### Outpatient Auxology (`/calculators/outpatient-auxology`)

| Tool | Route |
| --- | --- |
| Pediatric hypertensive BP percentiles (AAP 2017) | `/pediatric-bp` |
| Growth Velocity SDS — infant WHO–Tanner (≤5.9 y) or pediatric HV both ancestries (>5.9 y) | `/gv-sds` |
| Anthropometric ratio tools — SHOX/XO sit–stand and arm-span screening; sitting height SDS; ACH SH/LL SDS | `/anthropometric-ratio-tools` |
| Diagnosis-Specific Growth — Shyr GAMLSS condition height SDS/%ile (2–20 y; optional unaffected overlay) | `/diagnosis-specific-growth` |
| Physical Exam Staging Guide | Coming soon |

### Outpatient Endocrinology (`/calculators/outpatient-endocrinology`)

| Tool | Route |
| --- | --- |
| Long-Acting GH IGF Correction — Table 2 SDS timing factors (Ngenla / Skytrofa / Sogroya) | `/lagh-igf-correction` |
| IGF-1 / IGFBP-3 Z-score — multi-assay SDS + optional Tanner/SMR | `/igf1-zscore-roche` |
| GH dosing — Initiate & Titrate (daily/weekly; doses/week schedule; obese Costeff/Mosteller BSA; indication start ranges; calculated vs pen dose; selectable pen strengths with exact/rounded 28-day supply) | `/gh-dosing` |
| Levothyroxine dosing — age-based mcg/kg; optional BSA (100 mcg/m²) after 1 y | `/levothyroxine-dosing` |

### Lab References (`/calculators/lab-assays`)

| Tool | Route |
| --- | --- |
| Esoterix lab search/conversion | `/esoterix-labs` |

### PEARLS (`/calculators/pearls`) — planned; hub hidden in CALCS UI

| Tool | Route |
| --- | --- |
| Hormone and Receptor review | Coming soon |
| Genes and Genetics | Coming soon (`data/calc/genes-genetics.csv`) |

Collection meaning: Peds Endo Applied Review & Learning Strategies. Catalog entries remain in code for a future hub; not listed on `/calculators` until promoted (see `predeployPHYSIS.md`).


## Planned Updates
### Larger tasks

- [ ] CHP X-ray atlas images per landmark/stage (`data/atlas/xr/`)
- [ ] PHYSIS / CALCS logo
- [ ] Google Analytics optimization for search and reach
- [ ] RedCAP pre-test cohort data (PES survey dispersal)
- [ ] PEARLS learning suite (stim-test interpretation; DKA fluids / new-onset T1DM TDD; parathyroidectomy guideline)

### Patch polish

- [ ] QC / “show calculations” footer for each tool
- [ ] Clean up footer text into info tooltips; references in copy-paste output
- [ ] Confirm copy-paste functionality for each calculator

### Calculators to add or consider

- [ ] Quick SGA/AGA/LGA determination tool (Outpatient Auxology)
- [ ] Consider tools from [EndoBora](https://www.endobora.com/?lang=en) (syndrome criteria; SMR/Tanner, Prader/Quigley/Sinnecker/FGS scoring)
- [ ] Consider TSPED website features ([ceddcozum](https://www.ceddcozum.com/))

## Changelog

Completed work tracked in `predeployPHYSIS.md` ([x] items). That file replaced `predeployPHYSIS.txt` as the Markdown release-planning checklist.

### Growth, bone age & height prediction

- [x] TW3 atlas individual stage images with side-by-side markdown stage criteria (`data/atlas/individual-stages/`, `data/atlas/stage-descriptions/`)
- [x] TW3 APH calculator from Tanner et al. (optional MPH adjustment — off by default; menarchal status for girls 11–14 y)
- [x] MPH calculation within the app; clear separation of MPH vs true MPS (parental average)
- [x] CDC growth charts plotting height/weight vs CA and BA-shifted age with predicted adult height trajectories
- [x] Adjusted RWT retained; original RWT restored alongside it; Khamis-Roche gated behind “APH without bone age”
- [x] APH result cards list missing inputs before a prediction populates
- [x] Show-work / QC audit step (`src/core/showWork/buildShowWorkReport.ts`, `src/components/ShowWorkSection.tsx`)
- [x] Copy-to-chart clinical summaries with configurable content and algorithm/atlas references
- [x] Standing vs supine height and other clinical notes moved to hover **info tooltips** for a cleaner UI
- [x] Age input fixes — no auto-padding of decimals/zeros until blur; improved years+months entry
- [x] TW3 stage slider stability, discrete stage picker, and refreshed stage-v2 atlas images
- [x] Bone age calculator UX — stage slider, image preloading, and layout improvements
- [x] TW3 workflow — Ulna-first landmark order (Ulna → Radius → thumb → 3/5 groups), dedicated Enter to save stage and advance, mobile two-column layout with vertical slider under the hand XR map
- [x] CDC growth chart viewer — click chart to open zoom/pan/print window with margin legend
- [x] Diagnosis-Specific Growth — Shyr et al. GAMLSS condition height-for-age SDS/percentile (ages 2–20; Plotly-extracted centiles + SI-digitized CF; optional study unaffected overlay); human QC of `scripts/output/dx-growth/qc/` vs SI/Shiny signed off 2026-08-27
- [x] TW3 RedCAP survey prompts — pre-test QR in stage panel before sex selected; post-test QR on TW3 bone-age result card until continue to APH; QR images open the RedCAP survey URL
- [x] TW3 chronological age “from DOB” — XR date − DOB, rounded to nearest year-month

### Electrolytes & calcium

- [x] Free water deficit (hypernatremia)
- [x] Sodium correction for hyponatremia
- [x] Sodium correction with hyperglycemia (standalone calculator)
- [x] Sodium replacement rate guidance (serum Na rise ≤ 0.5–1 mEq/L per hour; < 10–12 mEq/L in first 24 h)
- [x] Calcium correction with albumin
- [x] Renal electrolyte panel — TRP, CCR, spot UCa/UCr, and TTKG from paired serum/urine labs with result interpretation tooltips
- [x] Spot UCa/UCr ratio with age-based 95th-percentile guidance and nephrocalcinosis flags
- [x] Renal less-than assay estimates — SCr &lt;0.15, UCa &lt;5, UCr &lt;13 checkboxes; inequality bounds with Bayesian probabilities when available; optional 24h Ca max from censored UCa/UCr (Costeff/Haycock); dilute UCr rule-in for TRP and spot UCa/UCr (CCR stays invalid)
- [x] DXA BMD Interpretation — aBMD_HAZ (spine), TBLH BMC-for-actual-weight and BMC-for-lean-mass (ALPHABET Hologic), UD radius aBMD Z; race-neutral (Zemel 2025) vs race-specific (Zemel 2011 / Kalkwarf 2022); MULT height HAZ
- [x] Calcium dosing (enteral / parenteral) — bidirectional salt ↔ elemental Ca by weight and doses/day; formulation tips; range recommendations and collapsed calcitriol adjunct
- [x] Figueras-Aloy MBDP risk-score — ALP + phosphorus → Models E (4-group) and I (3-group); Bone Health collection

### Diabetes & nutrition

- [x] A1c ↔ GMI ↔ fructosamine ↔ eAG converter — four-field input (enter any one value); Cohen et al. (ADA 2003) preferred; Young et al. (MilMed 2025) alternate
- [x] Diabetes calculator collection (`/calculators/diabetes`)
- [x] MDI to ISS (insulin sliding scale) conversion
- [x] Diluted ISS generation
- [x] Maintenance IVF (mIVF) — Holliday–Segar calculations
- [x] GIR calculator — IV and enteral, with combined total
- [x] Insulin Resistant Indices — HOMA-IR, QUICKI, SPISE, and Matsuda; OGTT optional; adult / pediatric / SMR cut-offs; pediatric DM-diagnosis disclaimer
- [x] MODY Clinical Calculator — Shields 2024 at-diagnosis (age &lt; 20; Table S6 ± Abs) and Exeter 2012 post-6-month PPV (diagnosis ≤35; T1/T2 branch)
- [x] Glycemia Risk Index (GRI) Calculator — CGM AGP % (Very High / High / Low / Very Low), derived TIR, hypo/hyper components, capped GRI, zones A–E, GRI Grid (Klonoff et al. 2023)
- [x] TDD estimator and MDI calculator — meal + correction bolus (target 100 mg/dL; correction 0 if BG &lt; 100; round to ½ and whole units) or TDD / % basal (~40% recommended) / 1500 ISF / 500 ICR / 60 g meal ICRs from breakfast–dinner + Lantus

### General pediatrics

- [x] Pediatric age-based hypertension guideline calculator (BP percentiles)
- [x] CAH screening tool (17-OHP with prematurity algorithms)
- [x] CAH tool renamed to “17OHP Intrepretation in Prematurity”
- [x] BSA calculator — Haycock (weight + height) and Costeff weight-only estimate
- [x] BSA input method labels and Costeff/Haycock formula hints on `/bsa-steroid`
- [x] Steroid wean calculator / potency converter
- [x] Steroid wean dosing refinements — equal-preferred PO splits (1.25 mg), anesthesia/severe-illness rounding (5 mg PO / whole-mg IV), transition mg/day + mg/m² display, and short wean-only clinical copy
- [x] XY DSD Steroid Panel — post-hCG T/DHT (SRD5A2) and T/Δ4A (17β-HSD3) ratios with literature cutoffs; optional ASI (LH × T); Esoterix unit conversion for T, DHT, and Δ4A; AMH/USP/genetics amber disclaimer
- [x] Gonad auxology — SPL (newborn and child) and clitoral dimension nomograms with reference charts
- [x] Gonad auxology — click-to-enlarge zoomable nomograms; Feldman newborn GA reference; Feldman child −2.5 SD threshold; corrected Feldman percentile derivation from mean ± SD
- [x] Uterine / ovarian SDS — Gilligan 2019 Table 1/2/3 mean±SD Z-scores; ellipsoid volume; cycle-week overlay ≥12 y
- [x] Long-Acting GH IGF Correction — Table 2 SDS timing factors for somatrogon (Ngenla), lonapegsomatropin (Skytrofa), and somapacitan (Sogroya); Outpatient Endocrinology collection
- [x] IGF-1 Z-score (Roche Elecsys) — age- and sex-specific 2.5/50/97.5% quantile SDS
- [x] IGF-1 / IGFBP-3 Z-score — Bidlingmaier LMS, Jo Liaison/Immulite, Roche IGF-1 & IGFBP-3; optional Wit Tanner/SMR (age ≤21 y)
- [x] GH dosing — Initiate & Titrate (daily/weekly Brand (generic) formulations; formulation requires explicit selection; Doses/Week 3/4/6/7 for daily Initiate with mg/dose · mg/week · mg/kg/week results and schedule-aware 28-day supply; weekly LAGH titrate steps ±0.02/±0.04 mg/kg/dose with IGF timing notice; daily titrate early results when weight+dose ready with `??` flag placeholders; Obese track picker for current weight / IBW / LBM / Costeff or Mosteller BSA; BSA schema 4.5±1 mg/m²/week max 7.5/9.5 Turner; indication start-dose ranges; calculated vs pen-delivered dose; selectable pen strengths with exact and rounded-up 28-day supply plus max-dose / split-dose alerts; CA/BA as years+months or decimal; titrate flag cards with mean±SD GV + ancestry, IGF-1 SDS tones, residual-growth N/A, male AI card OR logic)
- [x] Growth Velocity SDS — age via years+months / total months / today−DOB; WHO–Tanner infant 12-month tables (≤5.9 y); pediatric HV SDS for both ancestries (>5.9 y); adequacy band colors with stim-test tooltip on low bands
- [x] Levothyroxine dosing — age-band mcg/kg once daily; newborn cardiac/low-T4 start snaps; optional BSA dosing (100 mcg/m²) after 1 y with direct / Costeff / Mosteller
- [x] Anthropometric ratio tools — SHOX/XO SH/H SDS > +1 (Fredriks), arm span/height < 96.5%, arm span − height ≤ −3 cm; sitting height SDS for sex/age (Fredriks 2005); ACH LL/SH/SH/H/SH/LL SDS (del Pino 2018 Tables 3–4)

### Platform & data

- [x] CDC plotting logic fixes
- [x] Top-banner attribution updated — PHYSIS is an independent app, not a fork of eatyourpeas/endocrinologist
- [x] Deployed to `calc.dom.doctor` via Cloudflare Workers
- [x] Scheduled midnight UTC GitHub sync — Worker compares `master` SHA and dispatches deploy when changed
- [x] GitHub Actions deploy workflow (Node 22 build; checkout/setup-node v5)
- [x] Release planning checklist moved from `predeployPHYSIS.txt` to `predeployPHYSIS.md`
- [x] Sequential release tagging script (`npm run release:tag`) using `vMAJOR.MINOR.PATCH` (`0.y.x` during beta; current **v0.8.2**)
- [x] Per-branch pending release deltas (`.release/pending/<branch-slug>.json`; `npm run release:pending:init|show|apply|sync-siblings`) — feature branches record one bump; master apply uses current latest tag; sibling sync brings `origin/master` into other open pending branches only (never merges them onto master; conflicts abort for discussion at that branch’s merge)
- [x] Header version + last-updated date above feedback icons (`src/data/appVersion.ts`; version **v0.8.2**; last-updated injected at build from HEAD commit date so every master push refreshes it)
- [x] Home header RedCAP survey links — logo + pre/post emoji links centered between title and GitHub feedback
- [x] Mobile home header — compact RedCAP + GitHub feedback column to avoid icon overlap
- [x] Improved PHYSIS favicon (`public/favicon-physis.png`) with cache-busting route favicon hook
- [x] Public community repo (`doctor-dom/physis-calcs`) — header Issues/Discussions/Planned Updates links; parallel Actions workflow syncs a community-safe README
- [x] Persistent footer Terms of Use link (`/terms-of-use`) sharing the disclaimer banner, with UTC last-updated timestamp
- [x] `/disclaimer` and `/terms-of-use` render from repo-root `Disclaimer.md` and [`ToU.md`](ToU.md) at Vite build/dev (synced on each master deploy)
- [x] `ToU.md` `Last updated:` stamp synced from the file’s last content-edit time (`npm run legal:stamp` on commit / master push)
- [x] CALCS collections reorganized — Electrolytes/Fluids, Insulin/Glucose, Adrenal, Gonad Auxology, Outpatient Endocrinology, Bone Health, Lab Assays; coming-soon placeholders; renal-electrolytes under Bone Health; PEARLS documented but hub hidden until promoted; legacy `/calculators/normograms` redirects to gonad-auxology
- [x] CALCS calculator chrome — back link to the active collection roster and Reset fields (remount) under the brand/GitHub header
- [x] Esoterix lab search/conversion — search by name/alias/code; seven category chips (Adrenal, HPG, Thyroid, Growth, Adrenal Medulla, Bone Health, Diabetes/Glycemia); expandable expected-value cards; SI ↔ mass conversion; Labcorp PDF link (`/esoterix-labs`)

## Clinical notes

- **TRP** < 0.85 → excess phosphorus wasting / hyperparathyroidism
- **CCR** ≤ 0.02 → consider CaSR testing; < 0.01 → familial hypocalciuric hypercalcemia (FHH) likely
- **Spot UCa/UCr** > 0.2 → higher predisposition to nephrocalcinosis; compare to age-specific 95th percentiles
- **TTKG** < 7 (when valid) → mineralocorticoid deficiency suggested in hyperkalemia
- **FWD** uses TBW fraction × weight × (NaSerum/NaTarget − 1)
- **Hyperglycemia corrected sodium** — cNa = sNa + 0.024 × (sGlu − 100)
- **Hyponatremia correction** — target serum sodium rise ≤ 0.5–1 mEq/L per hour and < 10–12 mEq/L over the first 24 hours

For clinical decision support only — verify independently.
