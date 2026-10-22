# Results, deviations and limitations

## Supported conclusion

The final Qase records contain 18 Passed and 2 Blocked outcomes across 20 planned case executions. The observed recovery scenarios generally resumed automatically when connectivity returned. Both TC15 executions completed through automatic recovery, leaving the intended manual retry path untested. There are no final Failed results.

## Deviations and observations

| Run / case | Observation | Interpretation |
|---|---|---|
| R01 TC02 | imagem_teste.jpg used instead of the planned case filename | Naming deviation preserved in result comments |
| R01 TC04 | Upload resumed after connectivity returned | Cleanup observation after the offline checks |
| R01 TC05 | About one second reported after reconnection | Visual estimate; no stopwatch or performance metric |
| R01 TC06 | Generic uploading banner, but details showed waiting for Wi-Fi | Wi-Fi-only restriction was the decisive observation; no completed cloud file reported during the observation period |
| R01 TC10 | Initial attempt completed after Wi-Fi was restored | Initial attempt did not validate the intended transition; repeat retained separately |
| R01 TC10 | Two files named TC10_R01_attempt2_video.mp4 | Tester reported two manually initiated uploads; not attributed to automatic app duplication |
| R02 TC08 | PDF used in an earlier attempt | Excluded from the planned MP4 result; correct video attempt retained |
| R02 TC10 | Wi-Fi disabled before mobile data enabled | Passed as recorded, with deviation: recovery across an offline interval; uninterrupted handover remains unverified |
| R01 and R02 TC15 | Automatic recovery after network restoration | Manual retry unavailable; both final outcomes Blocked |

## Export reconciliation

Run 01 has 15 CSV rows. Run 02 has seven rows for five cases because TC15 has status history Passed → Retest → Blocked. Final totals select the latest `finish_time` for each case within each run. The first TC15 R02 row already contains a Blocked explanation despite the Passed status; the latest row resolves that inconsistency. Original rows are retained unchanged.

The JSON exports 15 case definitions across four suites and does not contain the execution evidence or final run outcomes. `status: actual` is case-definition metadata. The CSVs supply final outcomes and comments, while screenshots are separate assets.

All individual step statuses in the CSV exports are Untested. Results were recorded at the case level. This package does not change those steps to Passed. `time_spent_ms` is Qase recorded time and must not be interpreted as upload duration, recovery latency or network throughput. Export finish times are preserved without inferring their timezone.

## Evidence strength and remaining coverage

The ZIPs contain 108 image members, of which 100 are byte-distinct. Eight R01 members repeat previous screenshots exactly. They are mapped in the evidence index and retained in the original archive. This is independent of the two manually created TC10 attempt2 files in Drive.

File identity and playback claims in Qase comments are tester reports. The package review did not download the cloud fixtures or independently verify byte counts, hashes, duration or beginning/middle/end playback. Some original comments contain more detailed checks than the brief conversational confirmations; they remain original records rather than newly certified measurements.

Screenshots show moments in time and do not prove every transition, radio setting or elapsed interval. Some file names are truncated, and some captures show general upload status. In particular, the TC05 R01 desktop result is visible, but the adjacent offline/local-file captures name TC04 and are retained as TC04 context. These captures are not relabeled as proof of a TC05 offline queue. TC07 R01 has phone evidence in the ZIP; its desktop check is documented in the tester comment.

Only one device, OS configuration, app version and carrier were exercised. Recent-app dismissal does not demonstrate Android Force Stop or confirmed process death. Screen locking does not establish Doze coverage. Battery endurance, throughput, packet loss, signal degradation, large-file stress and service-side error injection were not measured.

## Follow-up work

- Exercise the manual retry path only when a reproducible supported state exposes it; record the condition without forcing a false Passed result.
- Repeat TC10 with mobile data enabled before Wi-Fi is disabled, recording the transition and final file.
- Capture file-specific upload details and radio settings at each transition; preserve explicit elapsed-time observations.
- Add local/downloaded fixture hashes and playback observations if binary integrity is a future test objective.
- Record per-step results in future Qase runs and expand the device/network matrix.
