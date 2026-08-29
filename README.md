# Intrusion Detection System — Backend Service

[![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688?style=flat-square&logo=fastapi)](https://fastapi.tiangolo.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

> Modular FastAPI backend service powering real-time network intrusion detection, live packet sniffing, multi-engine threat scoring, and persistent security alert logging.

---

## System Components

- **Packet Sniffer (packet_sniffer.py):** Real-time network interface listener capturing live TCP/UDP/ICMP traffic for feature extraction.
- **Feature Extractor (eature_extractor.py):** Extracts statistical packet features (packet length, flag rates, port access patterns) for inspection.
- **Signature Detector (signature_detector.py):** Matches incoming traffic against known attack signatures and malicious patterns.
- **Anomaly Detector (nomaly_detector.py):** Machine learning anomaly detector (model.pkl) evaluating unexpected traffic variations.
- **Adaptive & Geo Engines (daptive_engine.py, geo_engine.py):** Performs IP reputation lookup, geographical origin tagging, and threshold adaptation.
- **Threat Scoring (	hreat_score.py):** Aggregates multi-engine findings into normalized threat severity scores.

---

## API Endpoints

- GET /health — Health check status.
- GET /alerts — Retrieve historical incident logs from SQLite database (lerts.db).
- POST /detect — Submit packet features for manual threat evaluation.

---

## Quick Start

`ash
# Clone repository
git clone https://github.com/Aikagra-rgb/IDS_Project-backend.git
cd IDS_Project-backend

# Install dependencies
pip install -r requirements.txt

# Launch FastAPI service
uvicorn main:app --reload
`

---

## License

Distributed under the MIT License.
