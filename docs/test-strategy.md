# Test strategy and environment

## Objective and selection rationale

Evaluate whether upload state stays understandable and recoverable when an Android user loses connectivity, changes networks or leaves the app. The practical risks are an upload reported complete before a file is available, a transfer that fails to recover, a Wi-Fi-only preference being ignored, changed content, and an unexpected duplicate after recovery.

| Suite | Cases | Risk addressed |
|---|---|---|
| Baseline Uploads | TC01–TC03 | Establish successful PDF/JPG uploads over Wi-Fi and mobile data |
| Offline and Network Settings | TC04–TC07 | Queuing offline and respecting Wi-Fi-only transfers |
| Network Interruption and Recovery | TC08–TC11 | Recovery after link loss and completion across network transitions |
| App Lifecycle and Retry | TC12–TC15 | State consistency across backgrounding, screen lock, recent-app dismissal and retry |

Run 02 selected five recovery cases to examine repeatability. It was a focused repeat, not a second execution of the full suite. Wrong-fixture attempts and repeat uploads are retained as execution history and do not increase the 20 planned case executions.

## Method and test oracles

1. Use a readable local fixture and a case-specific filename; inspect the destination for pre-existing copies.
2. Configure Wi-Fi, mobile data and the Wi-Fi-only preference as specified in the case.
3. Start the operation and apply the planned interruption or lifecycle action while applicable.
4. Observe the UI state. For cases specifying an offline observation period, 30 seconds is a scenario condition, not a recovery-time SLA.
5. Restore the required conditions and observe whether action is required to resume.
6. Check cloud availability and copy count in desktop Drive, and compare the resulting file as described in the execution record.

Final case outcomes combine screenshots with tester statements. A static progress banner cannot establish which radio carried every byte, a precise outage duration or full binary integrity. No packet capture, logcat, ADB process trace or automated hash comparison of local and downloaded fixtures was supplied.

## Test data

| Format | Planned range | Recorded local display | Example content |
|---|---|---|---|
| PDF | Below 1 MB | 27.06 KB | One-page TESTE-PDF-001 document with text, accents and numbers |
| JPG | 2–3 MB fixture request | 2.35 MB | Mountain and lake image, imagem_teste.jpg |
| MP4 | 20–50 MB | 30.88 MB | Colored test bars |

Drive displayed approximately 26 KB, 2.2 MB and 29.5 MB respectively. Rounded sizes from different applications are insufficient to establish a file mismatch. Original media fixtures are not included in this evidence package; screenshots are not substitute fixtures for re-execution. The Qase JSON retains the authored case preconditions, including its broader preferred JPG size range.

## Result decisions

Passed means the execution was recorded as satisfying its applicable checks, with any deviation explicitly documented. Blocked means a required condition or action could not be exercised. TC15 requires a manual retry opportunity; automatic recovery prevents that step and therefore leaves it Blocked even when the resulting file is available.

The recorded environment is in the repository README and the case preconditions. ENV-001 was documented in text because it was not available as a selectable environment during setup.
