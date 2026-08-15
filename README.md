# Active Directory & Identity Defense Lab
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![CI](https://img.shields.io/badge/Build-Passing-brightgreen.svg)](#)
[![MITRE ATT&CK](https://img.shields.io/badge/MITRE-T1558%20%7C%20T1649-red.svg)](#)

Geliştirici: **Toprak Ahmet Aydoğmuş**

Kurumsal Active Directory ortamlarında **Active Directory Certificate Services (AD CS)** zafiyetlerini (ESC1-ESC8) ve **Kerberoasting** saldırılarını tespit edip önleyen profesyonel savunma platformu.

## Özellikler
- **AD CS ESC1-ESC8 Auditor:** Sertifika şablon bayraklarını (`CT_FLAG_ENROLLEE_SUPPLIES_SUBJECT`, Client Authentication EKU, Manager Approval) denetleyen çift yönlü (PowerShell ve Python CLI) analiz motoru.
- **Kerberos TGS Analizörü:** Event ID 4769 üzerinde RC4 (`0x17`) şifreleme düşürme (downgrade) saldırılarını tespit eden analiz motoru.
- **Sigma Kuralları:** `rules/` altında kurumsal SIEM entegrasyonuna hazır Sigma tespit kuralları.

## Hızlı Başlangıç
```bash
# Python test paketini çalıştırın
python -m unittest discover tests/

# CLI denetçisini çalıştırın
python scripts/ad_identity_auditor.py
```

## Lisans
MIT License - Toprak Ahmet Aydoğmuş
