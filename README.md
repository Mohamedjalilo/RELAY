# 🚑 RELAY — Bridging the Gap Before Arrival
### Human-in-the-Loop Pre-Hospital Emergency Triage & Handover System

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Mohamedjalilo/RELAY/blob/main/RELAY_.ipynb)

> **⚠️ Clinical Disclaimer:** RELAY is an educational and research prototype, **not** an approved medical device. All Artificial Intelligence (AI) outputs are preliminary drafts that require explicit review and confirmation by a qualified clinician before any clinical action or dispatch decision.

## 🎯 The Clinical Problem
In overcrowded Emergency Departments (EDs) and resource-constrained pre-hospital settings, ambulance handovers often depend on unstructured verbal reports delivered under time pressure, noise, and demanding conditions.

Important patient information may be fragmented, delayed, or overlooked during communication. Without structured pre-arrival information, receiving hospital teams may have limited time to prepare for incoming emergencies.

## 💡 The Solution: RELAY
**RELAY** bridges the communication gap between ambulance crews and hospital Emergency Rooms (ERs) before the patient arrives.

Its prototype includes two connected interfaces:
1. **Paramedic Intake Terminal:** A bilingual (Egyptian Arabic / English) voice-enabled interface that transcribes spoken patient information and uses AI-assisted extraction to organize patient demographics, vital signs, consciousness assessments (Alert, Voice, Pain, Unresponsive [AVPU] and Glasgow Coma Scale [GCS]), current medications, and Estimated Time of Arrival (ETA). It also generates a unique traceable Patient Identifier (ID) (`PT-YYYYMMDD-NNN-XXX`) and preserves the original transcript.
2. **Hospital ER Live Dashboard (`/er`):** A live dashboard that displays incoming confirmed cases, calculated Mean Arterial Pressure (MAP), Shock Index (SI), and standardized clinical readiness checklists.

## 🛡️ Safety-First Architecture & Clinical Governance
- **Human-in-the-Loop Gate:** No autonomous clinical actions. Paramedics can review, edit, and confirm extracted information before it is saved or transmitted. Manual edits are visibly identified to support accountability.
- **Deterministic Clinical Rules Engine:** A separate rule-based layer calculates MAP and SI and applies predefined clinical thresholds, including relevant Emergency Severity Index (ESI) and Pediatric Advanced Life Support (PALS) criteria. This provides an additional safety layer alongside AI-assisted processing and supports a rules-only decision mode when external AI services are unavailable.
- **Protected Health Information (PHI) Redaction:** Automated redaction is designed to remove patient names, national identification numbers, and phone numbers before external Large Language Model (LLM) processing, while masking national identification numbers in local Comma-Separated Values (CSV) logs.

## 🚀 Quickstart
1. Click **Open in Colab** above.
2. Run the notebook cell and provide your `GEMINI_API_KEY` when prompted, or configure it through Google Colaboratory (Colab) Secrets.
3. Open the Paramedic Terminal using the demo credentials (`ID: EMS001`, Personal Identification Number [PIN]: `2580`).
4. Open the ER Live Dashboard in a second browser tab to view incoming confirmed cases.

> **Demo Note:** The prototype requires a running Google Colab session and a valid Gemini Application Programming Interface (API) key. It is not currently a permanently hosted, publicly accessible application.
