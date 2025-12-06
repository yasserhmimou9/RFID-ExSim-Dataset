# RFID-ExSim-Dataset
RFID-ExSim is a multi-scenario experimental RFID dataset collected using a fully controlled acquisition pipeline with dual ESP32-MFRC522 readers and twelve passive RFID tags.
The dataset captures normal RFID behavior, multi-reader interactions, and several adversarial conditions, enabling reproducible research in RFID security, anomaly detection, access control, and signal-level characterization.

The repository provides the processed dataset, session metadata, scenario plans, and documentation necessary to fully reproduce the experimental protocol.

# Dataset Summary

The RFID-ExSim dataset contains over 400,000 timestamped RFID read events, generated across five experimental scenarios:

S1 — Baseline Legitimate Reads

Normal operation across multiple distances (1–4 cm) and orientations (0°, 45°, 90°).

S2 — Simultaneous Reads / Collisions

Two readers (A and B) attempt to read the same tag at the same time to measure collision patterns.

S3 — Tag Duplication / UID-Level Ambiguity

Evaluation of behavior when two distinct physical tags share the same UID (clone simulation).

S4 — Replay / Injection

Capture–replay timing, UID reuse, and software-injected read events for controlled adversarial evaluation.

S5 — High-Rate Flooding (DoS-like)

Stress tests involving rapid or continuous tag presentation, generating high-throughput read bursts.

Each record includes:

Millisecond-level ISO-8601 timestamp

Reader ID (ESP32_A, ESP32_B)

Tag local ID (TAG01–TAG12)

Hashed UID (privacy-preserving)

Scenario code (S1…S5)

Distance & orientation

# Documentation

Comprehensive documentation is included in the docs/ directory:

methodology.md — complete description of the acquisition pipeline

scenarios.md — detailed definitions of S1–S5 scenarios

esp32_reader directory contains:
notes_wiring :wiring , and ESP32-MFRC522 configuration

figures/ — pipeline diagrams and experimental setup images

These documents ensure full reproducibility, consistent with Scientific Data recommendations.

# Data Format

All processed files follow a unified JSON Lines schema:

timestamp_iso

session_id

scenario

device_id

tag_local_id

uid_hash

distance_cm

orientation_deg

event

raw_payload

This canonical structure allows direct use in ML pipelines and anomaly-detection systems.


# Intended Use

RFID-ExSim is designed for:

RFID security research

Clone/replay detection

Multi-reader timing analysis

Collision modeling

Anomaly detection

Signal-level RSSI/Timestamp pattern exploration

Benchmarking ML models for IoT security

The dataset is fully open for academic and industrial research.


Raw payload from MFRC522

Session identifier

# Dataset Download

The complete dataset (processed files S1→S5, metadata, and documentation) is available for direct download:

OneDrive Dataset Link:
https://emsicorp-my.sharepoint.com/:u:/g/personal/y_hmimou_emsi_ma/IQB3N2OgnHNEQbgHXo_cGcjgAa-GQJkvy1Sw8FEboRSxSoc?e=MnOZZ2

This link provides anonymous access for reviewers, in full compliance with Scientific Data first-round review requirements.
# Support & Contact

For questions regarding the dataset or reproduction of experiments, please contact:

Yasser Hmimou
Email: y.hmimou@emsi.ma
Affiliation: ENSET-2IACS / EMSI-LPRI
