# Validation — 2026-11-11

## Passed

- JavaScript syntax checks: engine.js, ui.js, learning.js.
- 55 deterministic clinical and content checks (`node tests/clinical.test.cjs`).
- All 12 demonstrations have expected diagnostic categories and teaching notes.
- Unknown data and unresolved contraindications do not automatically qualify a patient for the 17-week regimen.
- IGRA alone does not diagnose active disease; conflicting active/latent inputs block preventive treatment routing.
- AFB/MTB mismatch, prior-treated NAAT positivity, H resistance and R resistance route separately.
- HD Z/E intervals, PD individualization, no Z dose when Z unavailable, pediatric dose-table exclusion and extreme adult weight exclusion.
- Urgent signs, ALT thresholds, vision alerts and persistent culture positivity prompt reassessment.
- 20 questions have four choices, a valid answer, explanations and source references; 10 basic and 10 advanced.
- Mindmap has 10 main branches and more than 60 explanatory leaves.
- Uploaded index.html blob matched the local artifact for the first deployment; the final artifact is independently hash-checked against repository content.

## Verification limit

The environment blocked a local HTTP server and file-URL browser preview. The browser also denied access to the github.io origin, so desktop/mobile rendering and live interaction could not be directly verified in this session. No live-browser test pass is claimed. GitHub Pages deployment is checked through the repository's deployment status and Pages settings.

This is clinical decision support with conservative gates, not a validated mortality score or autonomous prescription system. Specialist review is required before clinical adoption.
