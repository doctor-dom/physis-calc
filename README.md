# PHYSIS

**Pediatric Height Yielded through Skeletal Interpretation System**

Pediatric endocrine clinical decision support — bone age scoring, adult height prediction, growth charting, and additional calculators for inpatient and outpatient practice. PHYSIS is a **standalone application built from scratch** for pediatric endocrinology workflows. 

**Inspiration**

PHYSIS draws on published methods and clinical references with its main focus of making important clinical tools available and easily accessible. While entirely developed by myself, PHYSIS takes inspiration from [Bone Age](https://play.google.com/store/apps/details?id=uk.co.eatyourpeas.tannerwhitehouse) and [endocrinologist](https://github.com/eatyourpeas/endocrinologist), both developed by [eatyourpeas](https://github.com/eatyourpeas). Inspiration for additional clinical tools from [Child Metrics](https://www.ceddcozum.com/), developed and maintained by the Turkish Society for Pediatric Endocrinology and Diabetes (TSPED).

**Disclaimer**

Please be sure to read the [Disclaimer](https://calc.dom.doctor/disclaimer) and [Terms of Use](ToU.md) before using PHYSIS.

**P.H.Y.S.I.S. Production:** [https://calc.dom.doctor](https://calc.dom.doctor)

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

### Electrolytes (`/calculators/electrolytes`)

| Tool | Route |
| --- | --- |
| Sodium balance & replacement (FWD, hypo/hypernatremia infusion guidance) | `/sodium-balance` |
| Hyperglycemia sodium correction | `/hyperglycemia-sodium-correction` |
| Renal electrolyte indices (TRP, CCR, spot UCa/UCr, TTKG) | `/renal-electrolytes` |
| Calcium correction for albumin | `/calcium-albumin` |

Legacy routes `/trp` and `/ccr` redirect to `/renal-electrolytes`.

### Diabetes (`/calculators/diabetes`)

| Tool | Route |
| --- | --- |
| A1c ↔ GMI ↔ fructosamine ↔ eAG (Cohen et al. preferred; Young et al. alternate) | `/a1c-converter` |
| Insulin MDI → sliding scale (ISS) | `/insulin-mdi-iss` |
| Diluted ISS generation | `/insulin-diluted-iss` |

### Fluids & nutrition (`/calculators`)

| Tool | Route |
| --- | --- |
| Maintenance IVF (Holliday–Segar) | `/maintenance-ivf` |
| Glucose infusion rate — IV and enteral | `/gir` |

### General pediatrics (`/calculators`)

| Tool | Route |
| --- | --- |
| BSA (Haycock or Costeff weight-only) & steroid potency wean/converter | `/bsa-steroid` |
| Pediatric hypertensive BP percentiles (AAP 2017) | `/pediatric-bp` |
| 17OHP Intrepretation in Prematurity (Olgemöller 2003 and Pode-Shakked 2018) | `/cah-screening` |




### Gonad auxology (`/calculators/gonad-auxology`)


| Tool                                                                           | Route                 |
| ------------------------------------------------------------------------------ | --------------------- |
| Stretched penile length (newborn) — Halil et al. and Feldman/Aaronson nomograms | `/spl-newborn`        |
| Stretched penile length (child) — Bulgarian, Schonfeld, and Feldman references | `/spl-child`          |
| Clitoral length/width (neonate) — Alaei et al. nomogram                        | `/clitoral-dimension` |


## Planned Updates
### Larger tasks

- [ ] CHP X-ray atlas images per landmark/stage (`data/atlas/xr/`)
- [ ] PHYSIS / CALCS logo
- [ ] Google Analytics optimization for search and reach
- [ ] RedCAP pre-test cohort data (PES survey dispersal)

### Patch polish

- [ ] QC / “show calculations” footer for each tool
- [ ] Clean up footer text into info tooltips; references in copy-paste output
- [ ] Confirm copy-paste functionality for each calculator
- [ ] UD radius / DXA BMD scoring tools
- [ ] Consider better calculator organization by organ system

### Calculators to add or consider

- [ ] Elemental calcium calculator (salt ↔ elemental and dosage)
- [ ] Consider tools from [EndoBora](https://www.endobora.com/?lang=en) (syndrome criteria; SMR/Tanner, Prader/Quigley/Sinnecker/FGS scoring)
- [ ] ESOTERIX lab values search tool (`.md`) and unit converter
- [ ] IGF-1 LMS/SMS (Z-score) calculator — Roche, Esoterix, Severance references in `data/references/`
- [ ] Esoterix/Labcorp IGF-1 SMS scraper for LMS quantiles
- [ ] Time-based IGF-1 interpretation calculator for long-acting GH
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
- [x] TW3 RedCAP survey prompts — pre-test QR in stage panel before sex selected; post-test QR on TW3 bone-age result card until continue to APH
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

### Diabetes & nutrition

- [x] A1c ↔ GMI ↔ fructosamine ↔ eAG converter — four-field input (enter any one value); Cohen et al. (ADA 2003) preferred; Young et al. (MilMed 2025) alternate
- [x] Diabetes calculator collection (`/calculators/diabetes`)
- [x] MDI to ISS (insulin sliding scale) conversion
- [x] Diluted ISS generation
- [x] Maintenance IVF (mIVF) — Holliday–Segar calculations
- [x] GIR calculator — IV and enteral, with combined total

### General pediatrics

- [x] Pediatric age-based hypertension guideline calculator (BP percentiles)
- [x] CAH screening tool (17-OHP with prematurity algorithms)
- [x] CAH tool renamed to “17OHP Intrepretation in Prematurity”
- [x] BSA calculator — Haycock (weight + height) and Costeff weight-only estimate
- [x] BSA input method labels and Costeff/Haycock formula hints on `/bsa-steroid`
- [x] Steroid wean calculator / potency converter
- [x] Steroid wean dosing refinements — equal-preferred PO splits (1.25 mg), anesthesia/severe-illness rounding (5 mg PO / whole-mg IV), transition mg/day + mg/m² display, and short wean-only clinical copy
- [x] Gonad auxology — SPL (newborn and child) and clitoral dimension nomograms with reference charts
- [x] Gonad auxology — click-to-enlarge zoomable nomograms; Feldman newborn GA reference; Feldman child −2.5 SD threshold; corrected Feldman percentile derivation from mean ± SD

### Platform & data

- [x] CDC plotting logic fixes
- [x] Top-banner attribution updated — PHYSIS is an independent app, not a fork of eatyourpeas/endocrinologist
- [x] Deployed to `calc.dom.doctor` via Cloudflare Workers
- [x] Scheduled midnight UTC GitHub sync — Worker compares `master` SHA and dispatches deploy when changed
- [x] GitHub Actions deploy workflow (Node 22 build; checkout/setup-node v5)
- [x] Release planning checklist moved from `predeployPHYSIS.txt` to `predeployPHYSIS.md`
- [x] Sequential release tagging script (`npm run release:tag`) using `vMAJOR.MINOR.PATCH` (`0.y.x` during beta)
- [x] Header version + last-updated date above feedback icons (`src/data/appVersion.ts`)
- [x] Home header RedCAP survey links — logo + pre/post emoji links centered between title and GitHub feedback
- [x] Improved PHYSIS favicon (`public/favicon-physis.png`) with cache-busting route favicon hook
- [x] Public community repo (`doctor-dom/physis-calc`) — header Issues/Discussions/Planned Updates links; parallel Actions workflow syncs a community-safe README
- [x] Persistent footer Terms of Use link (`/terms-of-use`) sharing the disclaimer banner, with UTC last-updated timestamp

## Clinical notes

- **TRP** < 0.85 → excess phosphorus wasting / hyperparathyroidism
- **CCR** ≤ 0.02 → consider CaSR testing; < 0.01 → familial hypocalciuric hypercalcemia (FHH) likely
- **Spot UCa/UCr** > 0.2 → higher predisposition to nephrocalcinosis; compare to age-specific 95th percentiles
- **TTKG** < 7 (when valid) → mineralocorticoid deficiency suggested in hyperkalemia
- **FWD** uses TBW fraction × weight × (NaSerum/NaTarget − 1)
- **Hyperglycemia corrected sodium** — cNa = sNa + 0.024 × (sGlu − 100)
- **Hyponatremia correction** — target serum sodium rise ≤ 0.5–1 mEq/L per hour and < 10–12 mEq/L over the first 24 hours

For clinical decision support only — verify independently.
