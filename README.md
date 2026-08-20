# 🛡️ Active Directory & Identity Defense Lab (AD CS ESC1-ESC8 & Kerberoasting)

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/toprakahmetaydogmus/01-ad-identity-defense?color=blue&label=Release)](https://github.com/toprakahmetaydogmus/01-ad-identity-defense/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python: 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://python.org)
[![MITRE: Identity](https://img.shields.io/badge/MITRE%20ATT%26CK-T1558%20%7C%20T1649-red.svg)](https://attack.mitre.org)

Developer: **Toprak Ahmet Aydoğmuş**

---

## 🎯 1. Overview & Objectives
This lab provides a comprehensive detection and auditing framework for **Active Directory Certificate Services (AD CS)** misconfigurations (ESC1 through ESC8) and **Kerberoasting** attack vectors. It includes automated detection rules, auditing scripts, mock vulnerability generators, and telemetry mapping.

### Key Capabilities:
- **AD CS ESC1-ESC8 Auditor:** Identifies vulnerable certificate templates, enrollment rights, and NTLM relay endpoints.
- **Kerberoasting Detection Engine:** Inspects Event ID 4769 (TGS Request) anomalies with RC4 encryption downgrade detection.
- **Interactive TUI & Web Dashboard:** Real-time visibility into identity security posture.
- **MITRE ATT&CK Mapping:** Aligned with T1558.003 (Kerberoasting) and T1649 (Steal or Forge Authentication Certificates).

---

## 🚀 2. Quick Start

```bash
# Clone the repository
git clone https://github.com/toprakahmetaydogmus/01-ad-identity-defense.git
cd 01-ad-identity-defense

# Run the test suite
python -m unittest discover tests/

# Run the AD CS Security Auditor CLI
python -m src.ad_cs_auditor --audit-all
```

---

## 📜 3. License
Licensed under the [MIT License](LICENSE).  
Developer: **Toprak Ahmet Aydoğmuş**.
