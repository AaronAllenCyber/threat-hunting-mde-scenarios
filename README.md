# threat-hunting-mde-scenarios
Threat Hunting Scenarios
# Threat Hunting Scenarios — Microsoft Defender for Endpoint

A collection of four structured threat hunting scenarios designed for incident response practice and tabletop exercises. Each scenario follows the **NIST-aligned hunt methodology** (Prepare → Collect → Analyze → Investigate → Respond → Document → Improve) and includes KQL queries, MITRE ATT&CK mappings, and response guidance.

**Platform:** Microsoft Defender for Endpoint (MDE) / Microsoft Sentinel  
**Query Language:** KQL (Kusto Query Language)  
**Framework:** MITRE ATT&CK for Enterprise

---

## Scenarios

| # | Title | Key TTPs | Difficulty |
|---|---|---|---|
| [01](./scenario-01-exposed-devices.md) | Devices Accidentally Exposed to the Internet | T1110 · T1078 · T1133 | Beginner |
| [02](./scenario-02-network-slowdowns.md) | Sudden Network Slowdowns (Internal Port Scan) | T1046 · T1059.001 · T1105 | Beginner |
| [03](./scenario-03-data-exfiltration.md) | Suspected Data Exfiltration from PIP'd Employee | T1560.001 · T1048 · T1059.001 | Intermediate |
| [04](./scenario-04-pwncrypt-ransomware.md) | Zero-Day Ransomware Outbreak (PwnCrypt) | T1486 · T1059.001 · T1204.002 | Intermediate |

---

## How Each Scenario Is Structured

Each scenario follows a consistent seven-phase format:

1. **Preparation** — Threat context, scope, and hypothesis
2. **Data Collection** — Relevant MDE tables and log sources
3. **Data Analysis** — KQL queries to surface IOCs and anomalies
4. **Investigation** — Deep-dive guidance and MITRE ATT&CK mapping
5. **Response** — Containment and remediation actions
6. **Documentation** — What to record and why
7. **Lessons Learned** — Defensive improvements and hunt refinements

---

## MDE Tables Referenced

| Table | Scenarios |
|---|---|
| `DeviceInfo` | 01 |
| `DeviceLogonEvents` | 01 |
| `DeviceNetworkEvents` | 02 · 03 |
| `DeviceFileEvents` | 02 · 03 · 04 |
| `DeviceProcessEvents` | 02 · 03 · 04 |

---

## Skills Demonstrated

- Threat hunting methodology (hypothesis-driven)
- KQL query development for endpoint telemetry
- IOC identification and pivot-based investigation
- MITRE ATT&CK TTP mapping
- Incident response and containment procedures
- Security posture improvement recommendations

---

## Setup Notes

These scenarios are designed to run against a **Windows VM onboarded to Microsoft Defender for Endpoint**. A pre-existing honeypot (`windows-target-`) can also be observed in lieu of deploying your own VM.

> ⚠️ **If deploying your own VM:** Use strong credentials. VMs exposed to the internet for Scenario 01 will be targeted by real-world bots within minutes.

Each scenario (except Scenario 01) includes a PowerShell simulation script that populates the relevant MDE tables with realistic telemetry for hunting practice.

---

*Built as part of a hands-on cybersecurity lab series focused on Microsoft Defender for Endpoint and incident response.*
