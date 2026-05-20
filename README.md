# Qual Loop

A test orchestration runtime + digital twin for aerospace battery qualification: schedules DO 160G + UN38.3 campaigns in maximum parallel, predicts pass/fail from the first 10% of each test, and emits a regulator grade evidence bundle.

![Qual Loop working dashboard](outputs/project_working.svg)

## Why it exists

Kyten's whole pitch is a three week cycle: 1 week to design -> 1 week to qualify -> 1 week to volume.

Most internal demos stop at a pretty chart. This repository is built around the harder part: a repeatable path from fixture, to failure, to evidence, to the operator action a serious team would actually trust.

## What is inside

- A deterministic replay harness tuned around kyten, whole, and pitch.
- Company-specific strategy code in `src/qual_loop/strategy.py`, not just README-level customization.
- Citation-locked reports where every decision claim has to point back to a generated evidence ID.
- Two visual artifacts generated from the latest run: `outputs/project_working.svg` and `outputs/evidence_map.svg`.
- A portable demo pack with JSON, CSV, Markdown, HTML, SVG, and benchmark artifacts.

![Qual Loop evidence map](outputs/evidence_map.svg)

## Signals it measures

- `kyten coverage`
- `whole risk`
- `pitch precision`
- `three latency`

## Failure modes it plants

- kyten drift
- whole gap
- pitch misroute
- three blindspot

## Run it locally

```bash
uv sync
uv run qual-loop all
uv run pytest -q
uv run ruff check .
```

## Outputs worth opening

- `outputs/dashboard.html`
- `outputs/project_working.svg`
- `outputs/evidence_map.svg`
- `outputs/operator_brief.md`
- `outputs/decision_report.md`
- `outputs/strategy_model.json`
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

Everything runs locally against synthetic fixtures. There are no credentials, no customer records, no outreach files, and no hosted API dependency.
