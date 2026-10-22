# Android Connectivity & Recovery Lab

Manual Android QA portfolio by **Nicholas Passos**, using Google Drive uploads to investigate network interruption, recovery and app lifecycle behavior on a physical Samsung Galaxy S24 FE.

**15 test cases · 2 runs · 20 planned case executions · 18 Passed · 2 Blocked · 0 Failed**

| Run | Scope | Passed | Blocked | Failed |
|---|---|---:|---:|---:|
| [Run 01](results/R01.md) | Initial execution of TC01–TC15 | 14 | 1 | 0 |
| [Run 02](results/R02.md) | Recovery repeatability: TC05, TC08, TC09, TC10, TC15 | 4 | 1 | 0 |
| Total | 20 planned case executions | 18 | 2 | 0 |

TC15 was Blocked in both runs because the upload recovered automatically, preventing the planned manual retry from being exercised. TC10 Run 02 passed with a documented deviation: the Wi-Fi-to-mobile transition included an offline interval. These outcomes do not establish uninterrupted handover or manual retry coverage.

## Review the work

- [Test strategy and environment](docs/test-strategy.md): scope, risks, data and decision rules.
- [Test cases](test-cases/README.md): 15 procedures rendered from Qase.
- [Results and limitations](docs/results-and-limitations.md): conclusions, deviations and remaining coverage.
- [Evidence index](evidence/README.md): 100 distinct screenshots grouped by run and case, traced to 108 original archive members.
- [Original exports](exports/original): unmodified Qase JSON, both CSVs and both supplied evidence ZIPs.

## What this project demonstrates

The work connects expected app behavior to repeatable manual scenarios: establish a baseline, interrupt connectivity, observe the pending state, restore a connection, and check the resulting cloud file. Qase records case-level outcomes and execution comments. Phone and desktop captures support the observations, with tester confirmation for actions that static screenshots cannot establish.

The portfolio preserves invalid attempts, status corrections and evidence limitations. No product defect was established by these executions. The sample is limited to one device and app version and is not a claim that Google Drive is defect-free.

## Environment

| Component | Recorded value |
|---|---|
| Device | Samsung Galaxy S24 FE |
| OS | Android 16 / One UI 8.5 |
| App | Google Drive 2.26.387 |
| App language | Portuguese (Brazil) |
| Mobile network | Claro BR; 5G indicator observed |
| Management | Qase |
| Destination folder | QA-Connectivity-Lab |
| Local fixture folder | Downloads/ACRL-Test-Files |

Screenshots retain the original Portuguese interface; case documentation and results are in English. Execution dates span October 19–21, 2026 as recorded in the exports. No automated app tests, network traces or performance instrumentation are included.

## Package provenance

Manual actions and observations were supplied by the tester. AI assistance supported documentation, evidence organization and export reconciliation. Source exports and image bytes were preserved. See [source checksums](exports/source-checksums.json) and the [evidence manifest](evidence/manifest.json). These checksums describe the supplied evidence files, not the integrity of the PDF/JPG/MP4 fixtures uploaded to Drive.
