# KORU-001 — Azure diagnostic settings modified

## Summary

| Field | Value |
|---|---|
| Date | 19 September 2026 NZST |
| Detection | KORU-DET-001 |
| Severity | Medium |
| Data source | Azure Activity |
| Outcome | Benign positive |
| Closure reason | Suspicious but expected |

Microsoft Sentinel detected successful writes to an Azure diagnostic setting. The activity was generated as an authorised test of the KoruSOC detection and response workflow.

## Trigger

The `Autoscale` Activity Log category was temporarily disabled and immediately restored. This produced two successful `MICROSOFT.INSIGHTS/DIAGNOSTICSETTINGS/WRITE` events.

## Investigation

1. Opened the Sentinel incident and reviewed the alert timeline.
2. Confirmed that Account and IP entities were extracted by the analytics rule.
3. Opened the underlying Log Analytics events.
4. Verified that both operations were successful writes to diagnostic settings.
5. Confirmed that the events originated from the expected lab account and source IP.
6. Verified that the original logging configuration had been restored.
7. Checked for unexpected follow-on activity and found none.

## Findings

- Two matching events occurred seconds apart.
- Both events had `ActivityStatusValue` set to `Success`.
- The initiating identity and source IP were expected for the authorised test.
- All intended Activity Log categories were enabled after the test.
- Alerts were grouped into a single incident, reducing duplicate case noise.

## Analyst decision

The rule correctly detected real configuration changes. The activity was expected and authorised, so the incident was classified as **Benign Positive — suspicious but expected**, not as a false positive.

No containment or remediation was required.

## Improvements identified

- Treat delete operations as higher severity than write operations.
- Add approved deployment identities to a watchlist for context, not silent exclusion.
- Add change-window context before using the rule in a production environment.
- Preserve account and IP entity mappings for investigation while removing them from public evidence.

## Evidence

- [Custom incident created](../screenshots/05-custom-incident.png)
- [Sanitised investigation events](../screenshots/06-investigation-events.png)
- [Incident closed as benign positive](../screenshots/07-closed-benign-positive.png)
