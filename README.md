# security-automation-python

A collection of modular Python automation scripts designed to streamline security operations, automate incident response workflows, and conduct rapid security auditing. This repository provides defensive and offensive automation capabilities to reduce manual triage times for security teams.

---

## 🎯 Purpose & Scope

This project leverages Python to eliminate repetitive security workflows and accelerate operational tasks. The automation suite targets four core domains:

* **Log Parsing & Triage:** Scanning massive log files (Nginx, Syslog, CloudTrail) to isolate malicious indicators (brute force signatures, SQL injection patterns) and generate clean summaries.
* **API Ingestion & Threat Enrichment:** Querying public threat intelligence APIs (VirusTotal, AlienVault, Shodan) in parallel to automatically flag bad IPs or file hashes.
* **Network & Asset Auditing:** Automating local subnet scanning, port validation, and detecting newly exposed or unauthorized network assets.
* **Incident Response Playbooks:** Automating containment tasks, such as generating firewall block list rules or querying endpoint active connections during an active incident.

---

## 🚀 Key Features

* **Asynchronous Execution:** Built utilizing `asyncio` and `concurrent.futures` to process large log arrays and bulk API queries rapidly.
* **Modular Architecture:** Pure Python design without bloated dependencies—easily imported into broader DevSecOps and CI/CD pipelines.
* **SIEM/SOAR Ingestion Ready:** Output structures default to cleanly formatted JSON strings for direct pipeline integration.
* **Dynamic Alerting:** Inbound alert modules to push immediate warning summaries to Slack, Microsoft Teams, or custom webhooks when high-severity anomalies are detected.

---

## 📂 Project Structure

```text
security-automation-python/
├── scripts/
│   ├── log_parser.py          # Asynchronous log regex analyzer and anomaly aggregator
│   ├── ip_threat_enrich.py    # Queries threat intelligence APIs for bulk IP analysis
│   ├── network_auditor.py     # Port scanner and active banner grabbing automation
│   └── ir_containment.py      # Generates host firewall rule payloads for rapid containment
├── config/
│   ├── settings.sample.yaml   # API credentials and alert webhook configuration template
│   └── signatures.json        # User-definable regex patterns for malicious request detection
├── requirements.txt           # Python project package dependencies
└── README.md                  # System manual and scripting documentation
