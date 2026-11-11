# Validation — 2026-11-11

## Passed

- JavaScript syntax checks: engine.js, ui.js, learning.js.
- 66 deterministic clinical and content checks (`node tests/clinical.test.cjs`; v1.1 run under JavaScriptCore with a small require shim).
- All 12 demonstrations have expected diagnostic categories and teaching notes.
- Unknown data and unresolved contraindications do not automatically qualify a patient for the 17-week regimen.
- IGRA alone does not diagnose active disease; conflicting active/latent inputs block preventive treatment routing.
- AFB/MTB mismatch, prior-treated NAAT positivity, H resistance and R resistance route separately.
- HD Z/E intervals, PD individualization, no Z dose when Z unavailable, pediatric dose-table exclusion and extreme adult weight exclusion.
- Urgent signs, ALT thresholds, vision alerts and persistent culture positivity prompt reassessment.
- 20 questions have four choices, a valid answer, explanations and source references; 10 basic and 10 advanced.
- Mindmap has 10 main branches and more than 60 explanatory leaves.
- Uploaded index.html blob matched the local artifact for the first deployment; the final artifact is independently hash-checked against repository content.

## v1.1 debugging pass (2026-11-11)

- Unknown infection site no longer routes as extrapulmonary (next steps, DS duration, DR lines).
- LTBI / no-active pathways no longer request diagnostic cultures or DST; they show contact-DST, baseline-liver and retest steps.
- "Excluded + IGRA indeterminate/unknown" is no longer described as a negative infection test.
- Month-4 culture positivity overrides the 9-month extension and shows a suspected-failure plan; blocks 17-week eligibility.
- ALT stop threshold blocks 17-week eligibility; ALT and vision alerts are written into the treatment plan (and print summary).
- Treatment title no longer says "標準6個月療程" when the duration is extended; CNS duration kept when Z is unavailable; miliary and HIV prompts added.
- UI: invalid number input clears the value instead of silently keeping the previous one; demo/reset only touch form fields; print summary expands collapsed sections; sticky live status bar below 1100 px; 16 px mobile inputs (no iOS zoom); quiz moves focus to the explanation.
- Live browser check (localhost) of all 12 demos, quiz, mind map and invalid input: no console errors.

## Verification limit

The environment blocked a local HTTP server and file-URL browser preview. The browser also denied access to the github.io origin, so desktop/mobile rendering and live interaction could not be directly verified in this session. No live-browser test pass is claimed. GitHub Pages deployment is checked through the repository's deployment status and Pages settings.

This is clinical decision support with conservative gates, not a validated mortality score or autonomous prescription system. Specialist review is required before clinical adoption.
