# SOC Incident Report – Network Reconnaissance (Nmap)

## Overview

This project documents a simulated network reconnaissance attack performed in a personal SOC homelab.

The objective was to understand how attackers perform reconnaissance before attempting exploitation and how defenders can identify and mitigate these activities.

This report follows a SOC analyst style incident documentation process, including:

- Incident Summary
- Attack Timeline
- MITRE ATT&CK Mapping
- Technical Analysis
- Risk Assessment
- Security Recommendations
- Lessons Learned

---

## Lab Environment

| Machine | Purpose |
|----------|----------|
| Kali Linux | Attacker |
| Windows 11 | Victim |
| Wazuh SIEM | Monitoring & Log Collection |
| VMware Workstation | Virtualization |

---

## Tools Used

- Nmap
- Wazuh SIEM
- VMware Workstation
- Windows 11
- Kali Linux

---

## Attack Scenario

The attacker performed three phases of reconnaissance:

1. Host Discovery
2. Full TCP Port Scan
3. Vulnerability Assessment

Example commands:

```bash
nmap -sn 10.10.50.0/24

nmap -p- 10.10.50.25

nmap -O --script vuln 10.10.50.25
```

---

## MITRE ATT&CK

| Tactic | Technique |
|---------|-----------|
| Discovery | T1046 – Network Service Discovery |
| Discovery | T1046.001 – Port Scanning |
| Reconnaissance | T1595 – Active Scanning |

---

## Key Findings

- Multiple hosts discovered on the network.
- Open SMB and RDP services increased the attack surface.
- The SIEM server was reachable from the attacker network.
- Unknown devices should always be investigated.

---

## Recommendations

- Disable unnecessary services.
- Restrict RDP access.
- Disable SMB if not required.
- Segment the network using VLANs.
- Create Wazuh detection rules for Nmap scans.
- Implement firewall rules between network segments.

---

## Learning Objectives

This project demonstrates:

- Network reconnaissance techniques
- Port scanning with Nmap
- Security analysis
- Incident documentation
- MITRE ATT&CK mapping
- SOC reporting best practices

---

## Repository Contents

```
.
├── SOC_Incident_Report_INC-2026-002.pdf
├── SOC_Incident_Report_INC-2026-002.docx
├── README.md
```

---

## Disclaimer

This project was conducted in a controlled homelab environment for educational and defensive cybersecurity purposes only.

No production systems or third-party infrastructure were targeted.

---

## Author

**Hamdi**

SOC Analyst | Cybersecurity Student

Currently building practical Blue Team and SOC projects using:

- Wazuh
- Microsoft Sentinel
- Wireshark
- Nmap
- Kali Linux
- Windows
