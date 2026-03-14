# Microsoft Sentinel SOC Lab

A personal learning lab built to develop hands-on SIEM experience using Microsoft Sentinel — coming from a background in endpoint security and EDR operations (Microsoft Defender for Endpoint, SentinelOne, CrowdStrike Falcon).

This repository contains KQL detection rules, threat hunting queries, and incident response playbooks mapped to real-world attack scenarios and MITRE ATT&CK techniques.

---

## Why I Built This

I have 3+ years of enterprise endpoint security experience across 80,000+ endpoints — investigating alerts, triaging incidents, and applying KQL queries in MDE Advanced Hunting for compliance reporting and security posture analysis.

This lab extends that knowledge into the SIEM layer — building KQL detection rules and hunting queries designed for Microsoft Sentinel, with plans to connect data sources and test against live logs once the free tier workspace is configured.

---

## Repository Structure

```
sentinel-soc-lab/
├── detection-rules/          # KQL analytics rules for Sentinel
├── hunting-queries/          # Proactive threat hunting queries
├── playbooks/                # Incident response playbooks
├── setup-guide/              # How to set up the free Sentinel lab
└── sample-data/              # Sample log data for testing queries
```

---

## Detection Rules

| Rule | MITRE Technique | Severity |
|------|----------------|----------|
| Brute Force Login Detection | T1110 | High |
| Suspicious PowerShell Execution | T1059.001 | High |
| Lateral Movement via SMB | T1021.002 | High |
| Data Exfiltration over DNS | T1048.003 | Medium |
| Privilege Escalation Detection | T1068 | High |
| Suspicious Scheduled Task | T1053.005 | Medium |

---

## Hunting Queries

| Query | Purpose |
|-------|---------|
| Rare Process Detection | Identify processes seen on very few machines |
| Beaconing Detection | Identify regular outbound connections |
| Encoded PowerShell | Find base64 encoded command execution |
| After Hours Logins | Detect logins outside business hours |

---

## Skills Demonstrated

- KQL (Kusto Query Language) for detection and hunting
- MITRE ATT&CK framework mapping
- SIEM detection engineering
- Incident response workflow design
- Log correlation across multiple data sources

---

## Background

**Current Role:** Security Analyst — Endpoint Security & EDR Operations, DXC Technology  
**Experience:** 3+ years across MDE, SentinelOne, CrowdStrike Falcon  
**Other Projects:** [Behavioural Baseline Detector](https://github.com/pranavibunny/behavioral-baseline-detector) | [AI SOC Triage Assistant](https://github.com/pranavibunny/ai-soc-triage-assistant) | [Prompt Injection Detector](https://github.com/pranavibunny/prompt-injection-detector)

---

