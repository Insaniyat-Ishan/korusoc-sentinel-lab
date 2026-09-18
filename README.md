# KoruSOC — Microsoft Sentinel Detection and Response Lab

KoruSOC is a hands-on security operations project built to develop practical experience with Microsoft Sentinel, KQL, detection engineering and incident investigation.

The project uses a fictional organisation and sanitised lab data. It does not contain information belonging to real users or organisations.

## Project objectives

- Configure a Microsoft Sentinel lab environment
- Collect and analyse security telemetry
- Develop custom KQL detection queries
- Create and tune analytics rules
- Investigate simulated security incidents
- Map activity to MITRE ATT&CK
- Produce analyst playbooks and incident reports
- Demonstrate clear technical documentation

## Current environment

| Component | Configuration |
|---|---|
| Azure subscription | Azure for Students |
| Resource group | `rg-korusoc-lab` |
| Log Analytics workspace | `law-korusoc-lab-01` |
| Region | Australia East |
| Microsoft Sentinel | Not enabled yet |
| Data sources | Not connected yet |

## Planned incident scenarios

1. Password spraying followed by a successful authentication
2. Suspicious PowerShell execution
3. Privileged account or role modification
4. Possible data exfiltration

## Planned repository structure

```text
korusoc-sentinel-lab/
├── architecture/
├── detections/
├── incidents/
├── playbooks/
├── sample-data/
├── screenshots/
├── .gitignore
├── LICENSE
└── README.md
```

## Project status

**Phase 1 — Environment foundation**

- [x] Created Azure for Students subscription
- [x] Configured cost monitoring
- [x] Created the KoruSOC resource group
- [x] Created the Log Analytics workspace
- [ ] Enable Microsoft Sentinel
- [ ] Connect the first data source
- [ ] Run the first KQL query
- [ ] Build the first custom detection
- [ ] Investigate and document the first incident

## Safety and privacy

All testing will be performed inside an authorised lab environment. The repository will not contain credentials, access tokens, subscription identifiers, personal information, live malicious payloads or data belonging to third parties.
