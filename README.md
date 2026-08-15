# Active Directory & Identity Defense Lab
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform: PowerShell](https://img.shields.io/badge/Platform-PowerShell%20%7C%20Sysmon-blueviolet.svg)](#)
[![MITRE ATT&CK](https://img.shields.io/badge/MITRE-T1558%20%7C%20T1649-red.svg)](#)

Geliştirici: **Toprak Ahmet Aydoğmuş**

Bu laboratuvar; kurumsal Active Directory ortamlarında kimlik güvenliği, **Active Directory Certificate Services (AD CS)** yanlış yapılandırma denetimi (ESC1-ESC8) ve **Kerberoasting** saldırı tespiti için geliştirilmiş eksiksiz PowerShell denetim motoru ve Sigma tespit kurallarını içerir.

## Mimari Şema
```mermaid
graph TD
    User[Domain User / Analyst] -->|Audit Script| ADCS[AD CS Certificate Templates]
    ADCS -->|Analyze Flags| Auditor[Audit-ADCS-Templates.ps1]
    Auditor -->|Flag ESC1: CT_FLAG_ENROLLEE_SUPPLIES_SUBJECT| Alert[Security Alert & Remediation]
    Attacker[Kerberoasting Simulation] -->|RC4 TGS Request| KDC[Domain Controller KDC]
    KDC -->|Event ID 4769 Encryption: 0x17| Analyzer[Analyze-KerberosEvents.ps1]
```

## Dosyalar ve Araçlar
- `scripts/Audit-ADCS-Templates.ps1`: Sertifika şablonlarını ESC1, ESC2, ESC3, ESC4 risklerine karşı denetleyen analiz motoru.
- `scripts/Analyze-KerberosEvents.ps1`: Kerberos TGS isteklerini (Event 4769) inceleyip RC4 şifreleme düşürme (downgrade) saldırılarını tespit eden analiz motoru.
- `rules/sigma_adcs_esc1.yml`: AD CS şüpheli sertifika talebi Sigma kuralı.
- `rules/sigma_kerberoasting_rc4.yml`: RC4 Kerberoasting tespiti Sigma kuralı.

## Hızlı Başlangıç & Test
```powershell
# 1. AD CS Sertifika Şablonu Güvenlik Denetimini Çalıştırın
.\scripts\Audit-ADCS-Templates.ps1

# 2. Kerberoasting Event Log Analizini Çalıştırın
.\scripts\Analyze-KerberosEvents.ps1
```

## Lisans
MIT License - Toprak Ahmet Aydoğmuş
