# R2 Mechanics – Structured Offline Transcription and Interactive Archival Output

Welcome to the official documentation repository for **R2 Mechanics** – a modular, fully offline transcription and analysis system that produces interactive, visually structured HTML archives.

> This repository serves as a public, timestamped proof-of-concept and documentation reference. It contains **no operational source code**. The full system runs entirely offline and is available for review or pilot deployments in cooperation with research and cultural institutions.

---

## 🔗 Project Website (GitHub Pages)

👉 [Visit the public landing page](https://r2-mechanics.github.io/r2-mechanics/)

---

## 🚀 Live Demos

Explore example outputs with interactive navigation, embedded audio players, chapter markers, speaker attributions, and AI-generated annotations:

▶️ [JFK Moon Speech Demo](https://r2-mechanics.github.io/r2-mechanics/JFK-Moonspeech.html)  
▶️ [Apollo 11 Press Conference Demo](https://r2-mechanics.github.io/r2-mechanics/demo-apollo11/apollo11.html)  
▶️ [UAP Congressional Hearing Demo](https://r2-mechanics.github.io/r2-mechanics/demo-uap/uap.html)

These demos showcase the **structured offline HTML output** with:
- Secure local transcription (WhisperX)
- Speaker separation and time-aligned segments
- Automatic chapter structure
- Integrated LLM-based notes with precise timestamps
- Optional Stable Diffusion–generated chapter illustrations

---

## 🎯 Objective

**R2 Mechanics** was developed to help research institutions, archives, and cultural organizations process sensitive audio materials in a structured, transparent, and privacy-compliant manner.  

Key goals:
- 100 % offline operation, fully auditable
- No cloud dependencies or license conflicts
- Human-readable, long-term archivable outputs

---

## ⚙️ Key Features

- Local GPU-accelerated transcription (WhisperX)
- Speaker diarization and time-stamped segmentation
- Automated LLM annotations (notes/sidenotes) with exact timecodes
- Chapter-based summaries with generated time markers
- Stable Diffusion integration for chapter illustrations
- Fully structured HTML export:
  - Audio player with jump links
  - Table of contents
  - Chapter headings with images
  - Per-chapter summaries and notes
  - Clear speaker roles and time anchors
  - CSS-styled for readability

---

## 🧩 Component Overview (abstracted)

- **Transcription**: WhisperX (local, CUDA-accelerated)
- **Structuring**: Chapter files (.txt with timestamps, titles, descriptions)
- **LLM-based Analysis**: Offline generation of summaries and time-aligned notes
- **Image Generation**: Stable Diffusion (local prompt-to-image pipeline)
- **HTML Generator**: Fully styled, interactive output with audio and navigation

---

## 📄 Documentation

- [System Overview (EN)](docs/system_overview_en.md)
- [System Overview (DE)](docs/system_overview.md)
- [Whitepaper (PDF, EN)](docs/whitepaper_en.pdf)
- [Whitepaper (PDF, DE)](docs/whitepaper_de.pdf)

---

## 📬 Contact

For cooperation inquiries, demos, or pilot projects:

**David Thiry**  
✉️ office@r2-mechanics.com  
🔗 [GitHub: R2-Mechanics/r2-mechanics](https://github.com/R2-Mechanics/r2-mechanics)

---

## 🚦 Status

🛠 This repository documents the system architecture, use cases, and demo outputs.  
🔒 The full codebase and processing pipeline remain private but are verifiably implemented and available for institutional cooperation.

---
