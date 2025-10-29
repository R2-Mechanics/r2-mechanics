# R2 Mechanics – Structured Offline Transcription & AI Analysis Infrastructure

Official documentation repository of R2 Mechanics — a modular offline transcription and analysis system designed for archives, research institutions, and cultural heritage projects.  
The platform converts complex audio and video materials into structured, speaker-labeled, and navigable HTML reports — **without any cloud dependency**.

> This repository serves as a public, timestamped reference of methodology and system architecture.  
> It **does not** include operational source code. The full pipeline runs locally and is available for review within cooperation frameworks or NDA-based audits.

---

## 🌐 Public Website

👉 [Official Landing Page (GitHub Pages)](https://r2-mechanics.github.io/r2-mechanics/)

---

## 🎧 Live Demos

Explore interactive HTML reports featuring embedded audio, chapter navigation, and diarized speaker segmentation:

- ▶️ [JFK Moon Speech Demo](https://r2-mechanics.github.io/r2-mechanics/JFK-Moonspeech.html) — structured speech with chapters & timestamps  
- ▶️ [Apollo 11 Press Conference](https://r2-mechanics.github.io/r2-mechanics/demo-apollo11/apollo11.html) — multi-speaker historic Q&A session  
- ▶️ [Kennedy v. Braidwood Management — Oral Argument Transcript (Demo)](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html) — dual-pipeline showcase featuring an interactive playback interface (Pipeline A) and a research-optimized transcript (Pipeline B). [🔗 Open in full view](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html)  
- ▶️ [Alan Watts — The Natural Environment (Interactive Edition)](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html) — philosophical lecture demo featuring precise diarization, synchronized audio-text alignment, structured chapters, and offline-ready documentation. [🔗 Open in full view](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html)  
- ▶️ [UAP Congressional Hearing (2024)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing/uap-2024.html) — full-length, two-hour session  
- ▶️ [UAP Hearing 2025 (EN Demo)](https://project.r2-mechanics.com/demos/uap-hearing-Sep-2025/uap-hearing-Sep-2025.html) — structured with annotations and auto-scroll  
- ▶️ [UAP Hearing (PL/EN Demo)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing-pl/start-pl.html) — bilingual structure example  
- ▶️ [Oral-History.Digital – Pagenstecher Project](https://r2-mechanics.github.io/r2-mechanics/vortraege-de/pagenstecher-project.html) — archive-style HTML transcript  

These demos illustrate **structured offline output** with semantic segmentation, speaker attribution, and optional visual enrichments.


---

## 🎯 Objectives

R2 Mechanics enables the **structured, transparent, and GDPR-compliant processing** of sensitive audio and video material  
(e.g. interviews, oral history, archival recordings).

### Key features

- 100 % **offline operation** — air-gapped, telemetry-free  
- **GPU-accelerated transcription** with WhisperX (large-v3)  
- **Speaker diarization** using pyannote.audio (4.x)  
- **Semantic chaptering & summaries** via local LLMs (LM Studio / Ollama)  
- **Structured HTML / DOCX outputs** ready for archiving or publication  
- **Energy-autonomous infrastructure** with UPS-buffered redundancy  

---

## 🧩 System Architecture (Overview)

R2 Mechanics operates within the isolated environment `r2_asr4`, combining:

| Layer | Component | Function |
|-------|------------|-----------|
| **ASR + Diarization** | WhisperX (large-v3) + pyannote.audio (4.x) | word-level transcription & speaker segmentation |
| **Semantic Analysis** | local LLM (LM Studio / Ollama) | topic, entity & summary generation |
| **Output Generation** | Markdown / DOCX / HTML | structured reports with chapter navigation |
| **Audit & Resilience** | WARC archives + logs | deterministic, reproducible runs |
| **Energy System** | Renewable / UPS / NVMe infra | sustained 24-7 operation (10-year design cycle) |

---

## 🛡 Governance & Compliance Snapshot

- **Access Control & Governance** – per-project isolation, RBAC (owner / contributor / viewer), optional 2FA/MFA; no subprocessors.  
- **Data Lifecycle & Retention** – defined cycle (ingest → process → review → delivery → deletion); configurable 30 / 60 / 90 days policy.  
- **Reproducibility & Version Pinning** – each run records model versions (WhisperX large-v3, pyannote.audio 4.x), CUDA/Torch stack and config hashes.  
- **Security Posture** – fully air-gapped infrastructure, encrypted ingest/storage, immutable offline backups.  
- **Compliance** – processing exclusively within EU (Poland); AVV/DPA and TOM documents available on request.  
- **Release Management** – quarterly releases; project versions remain frozen until approved for upgrade.  
- **Privacy & Transparency** – NDA-based access possible; all stages audit-ready; source kept private for security integrity.

---

## ⚙️ Components (Abstracted)

- **WhisperX (offline CUDA)** – ASR + alignment  
- **Pyannote.audio (4.x)** – speaker diarization  
- **LLM Analysis (LM Studio / Ollama)** – topics, entities, summaries  
- **HTML Generator** – structured reports with audio playback  
- **Optional Modules** – SDXL image generation, multilingual context layers  

---

## 📄 Documentation

- [System Overview (DE)](docs/system_overview.md)  
- [System Overview (EN)](docs/system_overview_en.md)  
- [Whitepaper (DE, PDF)](docs/whitepaper_de.pdf)  
- [Whitepaper (EN, PDF)](docs/whitepaper_en.pdf)  
- [Project Profile (DE)](docs/projektsteckbrief.md)

---

## 📬 Contact

**David Thiry**  
📧 office@r2-mechanics.com  
🌐 [https://r2-mechanics.com](https://r2-mechanics.com)  
🔗 [GitHub: R2-Mechanics / r2-mechanics](https://github.com/R2-Mechanics/r2-mechanics)

---

## 🔒 Status

🧱 This repository documents the **architecture, methodology, and compliance framework** of R2 Mechanics.  
🛠 The operational pipeline is fully functional and verifiable under NDA but not publicly distributed.

---

📄 [Français → README_FR.md](README_FR.md)  |  [Deutsch → README_DE.md](README_DE.md)
