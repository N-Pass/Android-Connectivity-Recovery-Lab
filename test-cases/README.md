# Test cases

Rendered from the original Qase JSON. Case `status: actual` describes the case definition, not its execution result. Run 02 filenames and deviations are documented in the execution comments; the original definitions retain R01 filenames.

| Case | Suite | Definition | R01 | R02 |
|---|---|---|---|---|
| TC01 | Baseline Uploads | [Upload a PDF file over Wi-Fi](TC01.md) | Passed | Not selected |
| TC02 | Baseline Uploads | [Upload an image file over Wi-Fi](TC02.md) | Passed | Not selected |
| TC03 | Baseline Uploads | [Upload a PDF file over mobile data](TC03.md) | Passed | Not selected |
| TC04 | Offline and Network Settings | [Attempt to upload a PDF while offline](TC04.md) | Passed | Not selected |
| TC05 | Offline and Network Settings | [Recover a PDF upload after restoring Wi-Fi](TC05.md) | Passed | Passed |
| TC06 | Offline and Network Settings | [Respect Wi-Fi-only uploads when using mobile data](TC06.md) | Passed | Not selected |
| TC07 | Offline and Network Settings | [Complete a Wi-Fi-only upload after connecting to Wi-Fi](TC07.md) | Passed | Not selected |
| TC08 | Network Interruption and Recovery | [Recover an in-progress upload after Wi-Fi interruption](TC08.md) | Passed | Passed |
| TC09 | Network Interruption and Recovery | [Recover an in-progress upload after mobile data interruption](TC09.md) | Passed | Passed |
| TC10 | Network Interruption and Recovery | [Complete an upload after switching from Wi-Fi to mobile data](TC10.md) | Passed | Passed |
| TC11 | Network Interruption and Recovery | [Complete an upload after switching from mobile data to Wi-Fi](TC11.md) | Passed | Not selected |
| TC12 | App Lifecycle and Retry | [Maintain a consistent upload state after backgrounding and resuming the app](TC12.md) | Passed | Not selected |
| TC13 | App Lifecycle and Retry | [Maintain a consistent upload state after locking and unlocking the screen](TC13.md) | Passed | Not selected |
| TC14 | App Lifecycle and Retry | [Recover upload state after dismissing Google Drive from recent apps](TC14.md) | Passed | Not selected |
| TC15 | App Lifecycle and Retry | [Retry an interrupted upload without creating duplicate files](TC15.md) | Blocked | Blocked |
