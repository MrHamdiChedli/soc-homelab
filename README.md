# 🛡️ SOC Analyst Homelab Portfolio

![Wazuh](https://img.shields.io/badge/Wazuh-SIEM-blue)
![Windows](https://img.shields.io/badge/Windows-11-blue)
![Ubuntu](https://img.shields.io/badge/Ubuntu-26.04-orange)
![Kali](https://img.shields.io/badge/Kali-Linux-purple)
![MITRE](https://img.shields.io/badge/MITRE-ATT%26CK-red)
![Nmap](https://img.shields.io/badge/Nmap-Reconnaissance-success)
![Hydra](https://img.shields.io/badge/Hydra-Brute%20Force-lightgrey)

> **Author:** Hamdi  
> **Role:** Cybersecurity Student | Aspiring SOC Analyst  
> **Status:** 🚧 Active Project  
> **Focus:** Blue Team | Detection Engineering | Incident Response | Threat Hunting

---

# 📌 About This Project

This repository documents my journey of building a **Security Operations Center (SOC) Homelab** from scratch.

The goal is to gain practical, hands-on experience with the technologies, tools, and workflows used by SOC analysts in enterprise environments.

Rather than only studying cybersecurity theory, I wanted to understand how attacks happen, how defenders detect them, and how incidents are investigated and documented.

Every project in this repository is performed inside a **controlled virtual lab** built specifically for learning and defensive security research.

---

# 🎯 Objectives

This homelab is designed to help me develop practical skills in:

- Security Information and Event Management (SIEM)
- Windows Event Log Analysis
- Linux Administration
- Threat Detection
- Incident Response
- Digital Forensics
- Detection Engineering
- MITRE ATT&CK Mapping
- Network Security
- Blue Team Operations
- Threat Hunting
- Malware Analysis
- Security Automation

---

# 🖥️ Homelab Architecture

```text
                         ┌────────────────────────────┐
                         │       Home Router          │
                         └────────────┬───────────────┘
                                      │
                        10.10.50.0/24 │
                                      │
        ┌─────────────────────────────┼─────────────────────────────┐
        │                             │                             │
        │                             │                             │
┌─────────────────┐         ┌─────────────────┐          ┌──────────────────┐
│ Kali Linux VM   │         │ Windows 11 VM   │          │ Ubuntu Server    │
│                 │────────▶│                 │─────────▶│ Wazuh SIEM        │
│ Attacker        │         │ Victim / Agent  │          │ Monitoring Server │
│ 10.10.50.20     │         │ 10.10.50.25     │          │ 10.10.60.10      │
└─────────────────┘         └─────────────────┘          └──────────────────┘
```

---

# 🔧 Technologies Used

| Category | Technology |
|----------|------------|
| SIEM | Wazuh |
| Virtualization | VMware Workstation |
| Server OS | Ubuntu 26.04 LTS |
| Attacker OS | Kali Linux |
| Endpoint | Windows 11 |
| Scanning | Nmap |
| Brute Force | Hydra |
| Packet Analysis | Wireshark |
| Framework | MITRE ATT&CK |
| Version Control | Git & GitHub |

---

# 📂 Repository Structure

```text
SOC-Homelab/
│
├── README.md
│
├── incidents/
│   ├── INC-2026-001_SSH_BruteForce/
│   ├── INC-2026-002_Network_Reconnaissance/
│   └── Future Incidents...
│
├── screenshots/
│
├── diagrams/
│
├── configs/
│
└── docs/
```

---

# 🔥 Completed Projects

## ✅ Incident 001 — SSH Brute Force Detection

### Objective

Simulate an SSH brute force attack against a Windows endpoint and validate Wazuh's detection capabilities.

### Attack Tool

- Hydra

### Skills Learned

- SSH configuration
- Wazuh agent deployment
- Windows Event Logs
- SIEM alert analysis
- MITRE ATT&CK mapping
- Incident documentation

---

## ✅ Incident 002 — Network Reconnaissance Detection

### Objective

Simulate the reconnaissance phase of an attack by performing host discovery, full TCP port scanning, and vulnerability assessment using Nmap.

### Attack Tool

- Nmap

### Techniques Used

- Host Discovery
- Port Scanning
- OS Detection
- Vulnerability Scanning

### Skills Learned

- Network enumeration
- Open port analysis
- Attack surface assessment
- MITRE ATT&CK T1046
- Security reporting

---

# 📊 Current Skills Demonstrated

- SIEM Deployment
- Endpoint Monitoring
- Windows Event Analysis
- Linux Administration
- VMware Networking
- Network Troubleshooting
- Log Analysis
- Threat Detection
- Alert Triage
- MITRE ATT&CK Mapping
- Incident Documentation
- Security Recommendations
- Technical Reporting

---

# 📚 Learning Roadmap

The homelab will continue expanding with more realistic attack simulations.

## Planned Projects

- [ ] Detect Nmap scans automatically in Wazuh
- [ ] Configure Active Response
- [ ] Add Kali as a monitored endpoint
- [ ] Deploy Sysmon
- [ ] Integrate Microsoft Sentinel
- [ ] Build Sigma detection rules
- [ ] Create YARA rules
- [ ] Threat Hunting exercises
- [ ] PowerShell attack detection
- [ ] Credential dumping detection
- [ ] Pass-the-Hash simulation
- [ ] Mimikatz detection
- [ ] Metasploit exploitation
- [ ] Reverse shell detection
- [ ] Persistence detection
- [ ] Scheduled task abuse
- [ ] Windows Defender bypass techniques
- [ ] Malware analysis
- [ ] Phishing simulations
- [ ] DNS tunneling detection
- [ ] Ransomware behavior analysis
- [ ] Network segmentation
- [ ] Wazuh custom rules
- [ ] Detection engineering projects

---

# 🎓 What I'm Learning

This homelab allows me to practice skills commonly expected from a Tier 1 SOC Analyst, including:

- Monitoring security events
- Investigating alerts
- Understanding attacker behavior
- Mapping attacks to MITRE ATT&CK
- Writing professional incident reports
- Identifying security weaknesses
- Recommending defensive controls
- Building detection logic
- Improving visibility across endpoints

Every incident follows a complete investigation workflow:

1. Attack Simulation
2. Detection
3. Alert Analysis
4. Threat Intelligence
5. MITRE Mapping
6. Incident Documentation
7. Lessons Learned
8. Security Recommendations

---

# 📈 Long-Term Goal

My objective is to build a portfolio that demonstrates practical cybersecurity skills through real-world simulations rather than theoretical exercises.

By documenting each attack from both the attacker and defender perspectives, I aim to deepen my understanding of detection engineering, incident response, and SOC operations while continuously improving my technical abilities.

This repository represents my ongoing learning journey and will continue to grow as I complete new projects and explore more advanced attack techniques and defensive strategies.

---

# 🤝 Connect With Me

**LinkedIn**

https://www.linkedin.com/in/hamdichedl/

---

## ⚠️ Disclaimer

All activities documented in this repository were performed in a **controlled personal homelab** for educational and defensive cybersecurity purposes only.

No production systems, third-party infrastructure, or unauthorized networks were targeted.
