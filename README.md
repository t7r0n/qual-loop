# Qual Loop

A test orchestration runtime + digital twin for aerospace battery qualification: schedules DO 160G + UN38.3 campaigns in maximum parallel, predicts pass/fail from the first 10% of each test, and emits a regulator grade evidence bundle.

## Why This Exists

Kyten's whole pitch is a three week cycle: 1 week to design -> 1 week to qualify -> 1 week to volume. The 1 week to qualify claim is the most aggressive - real world aerospace battery qualification under DO 160G + UN38.3 + customer specific abuse profiles takes 8 - 16 weeks at most suppliers because test campaigns are sequential, instrumentation is hand stitched per build, and pass/fail decisions wait on a human engineer to read scope traces.

## What It Builds

- Replays synthetic `kyten` and `whole` cases against the project's evidence rules.
- Scores `kyten_coverage`, `whole_risk`, and `pitch_precision` so regressions are visible in CSV and JSON.
- Plants `kyten drift` and `whole gap` failures as negative controls.
- Writes citation-locked decision claims; unsupported claims fail verification.
- Exports a review dashboard and demo pack for `qual-loop` without hosted services.

## Local Run

```bash
uv sync
uv run qual-loop all
uv run pytest -q
uv run ruff check .
```

## Outputs

- `outputs/analysis.json`
- `outputs/scenario_report.csv`
- `outputs/decision_report.md`
- `outputs/evidence_packet.md`
- `outputs/dashboard.html`
- `outputs/demo_pack.zip`

## Sources

- https://www.ycombinator.com/companies/kyten-technologies
- https://www.ycombinator.com/launches/PIU-kyten-the-modern-aerospace-battery-pack-supplier
- https://x.com/maddox_lucas
- https://www.linkedin.com/in/lucasmaddox/
- https://www.linkedin.com/in/cooper-mcbride/
- https://advisingblog.ece.uw.edu/2026/03/24/wired-for-success-career-panels-cooper-mcbride-co-founder-kyten-former-space-x-4-29-330-p-m/
- https://www.batterydesign.net/legislation-rules-and-regulations/un38-3-transport-test/
- https://incompliancemag.com/an-overview-of-aerospace-battery-compliance/
- https://ntrs.nasa.gov/api/citations/20210009584/downloads/AIAA_BatteryScaling.pdf
- https://tracxn.com/d/companies/kytentech/__rCxrrADqobRURixJbkXFA9L7gyIdZbUznTW9kxtP-4Y

## Boundary

This repository uses synthetic fixtures only. It has no credentials, no customer data, no outreach data, and no dependency on a hosted API.
