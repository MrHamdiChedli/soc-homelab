# 🛡️ SOC Analyst Homelab — SSH Brute Force Detection with Wazuh SIEM

![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-blue)
![Ubuntu](https://img.shields.io/badge/Ubuntu-26.04-orange)
![Windows](https://img.shields.io/badge/Windows-11-blue)
![Kali](https://img.shields.io/badge/Kali-Linux-purple)
![MITRE](https://img.shields.io/badge/MITRE-ATT%26CK-red)
![Hydra](https://img.shields.io/badge/Hydra-v9.7-lightgrey)

> **Built by:** Hamdi  
> **Date:** June 2026  
> **Goal:** Design, deploy, and operate a SOC homelab to simulate, detect, analyze, and document real-world cyber attacks using enterprise security monitoring tools.

---

# 📌 Project Overview

This project documents the setup of a fully functional **Security Operations Center (SOC) homelab** built from scratch using free and open-source tools. The lab simulates a real enterprise environment where a SIEM monitors endpoints and detects attacks in real time.

The project demonstrates the complete SOC workflow:

- Attack simulation
- Log collection
- Threat detection
- Alert triage
- MITRE ATT&CK mapping
- Incident documentation
- Security recommendations

---

# 🖥️ Lab Architecture

```text
┌───────────────────────────────────────────────────────┐
│             SOC HOMELAB (10.10.50.0/24)               │
│                                                       │
│  ┌──────────────────┐      ┌────────────────────┐     │
│  │ Kali Linux VM    │─────▶│ Windows 11 Laptop  │     │
│  │ 10.10.50.20      │      │ 10.10.50.25        │     │
│  │ (Attacker)       │      │ (Victim / Agent)   │     │
│  └──────────────────┘      └─────────┬──────────┘     │
│                                      │ Security Logs  │
│                           ┌──────────▼──────────┐     │
│                           │ Ubuntu 26.04 LTS    │     │
│                           │ 10.10.60.10         │     │
│                           │ Wazuh SIEM          │     │
│                           │ (Monitoring Server) │     │
│                           └─────────────────────┘     │
└───────────────────────────────────────────────────────┘
```

---

# 🧰 Tools & Technologies

| Category | Tool | Purpose |
|----------|------|---------|
| SIEM | Wazuh 4.7.5 | Log collection & alerting |
| Server | Ubuntu 26.04 LTS | Wazuh host |
| Attacker | Kali Linux 2024 | Attack simulation |
| Endpoint | Windows 11 | Monitored system |
| Virtualization | VMware Workstation | Virtual lab |
| Attack Tool | Hydra v9.7 | SSH brute force |
| Wordlist | rockyou.txt | Password dictionary |
| Framework | MITRE ATT&CK | Threat mapping |

---

# 📁 Repository Structure

```text
soc-homelab/
├── README.md
├── incidents/
│   └── INC-2026-001_SSH_BruteForce/
│       ├── incident_report.pdf
│       ├── incident_report.docx
│       └── screenshots/
│           ├── dashboard_overview.png
│           ├── brute_force_alerts.png
│           └── mitre_attack_t1078.png
└── configs/
    └── wazuh_setup_notes.md
```

---

# 🔴 Attack Simulation

## Objective

Simulate an SSH brute force attack against a Windows endpoint and observe how Wazuh detects and classifies the activity.

### Attack Command

```bash
hydra -l labuser -P /usr/share/wordlists/rockyou.txt ssh://10.10.50.25 -t 4 -V
```

Hydra performed thousands of password attempts using the **rockyou.txt** wordlist while the Wazuh agent forwarded Windows Security Events to the SIEM in real time.

---

# 📊 Detection Results

## Dashboard Overview

*(Insert Screenshot Here)*

The dashboard displays the overall event timeline, including the initial agent registration and the authentication failures generated during the attack simulation.

---

## Authentication Alerts

*(Insert Screenshot Here)*

Wazuh generated Rule **60122** for each failed SSH authentication attempt.

Key observations:

- Rule ID 60122
- Alert Level 5
- Hundreds of authentication failures detected
- Real-time event ingestion
- Automatic PCI DSS mapping

---

## MITRE ATT&CK Mapping

*(Insert Screenshot Here)*

| Technique | Description |
|------------|-------------|
| T1078 | Valid Accounts |
| T1531 | Account Access Removal |

Associated tactics include:

- Initial Access
- Persistence
- Defense Evasion
- Privilege Escalation
- Impact

---

# 📋 Incident Summary

| Field | Value |
|-------|-------|
| Incident ID | INC-2026-001 |
| Severity | Medium |
| Status | Detected & Contained |
| Attack Type | SSH Brute Force |
| Source | Kali Linux (10.10.50.20) |
| Target | Windows Endpoint (10.10.50.25) |
| Tool | Hydra + rockyou.txt |
| Detection | < 1 second |
| SIEM | Wazuh 4.7.5 |

📄 **Full Incident Report**

```
incidents/INC-2026-001_SSH_BruteForce/incident_report.pdf
```

---

# 🔧 Skills Demonstrated

- SIEM Deployment (Wazuh)
- Windows Event Monitoring
- Wazuh Agent Deployment
- SSH Configuration
- VMware Networking
- Attack Simulation
- Threat Detection
- Alert Triage
- Log Analysis
- MITRE ATT&CK Mapping
- Incident Response
- Incident Documentation
- Network Troubleshooting

---

# 🚀 Future Improvements

- Add Kali Linux as a monitored endpoint
- Detect Nmap reconnaissance
- Configure Active Response
- Deploy Metasploitable
- Simulate Metasploit attacks
- Develop custom Wazuh detection rules
- Expand incident documentation

---

# 🧠 Key Takeaways

- Wazuh provides near real-time detection of authentication attacks.
- MITRE ATT&CK mapping enriches alerts with valuable threat context.
- Effective network troubleshooting is essential when deploying security monitoring solutions.
- Incident documentation is a critical part of the SOC workflow.
- Strong authentication controls, MFA, and account lockout policies help mitigate brute force attacks.

---

# 📬 Connect With Me

- **LinkedIn:** https://www.linkedin.com/in/hamdichedl/

---

## Disclaimer

This project was performed in a controlled personal homelab for educational and defensive cybersecurity purposes only.

No third-party systems or production environments were targeted.
