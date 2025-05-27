# R2 Mechanics – Structured Offline Transcription for Research and Archives

Welcome to the official documentation repository for **R2 Mechanics** – a modular, fully offline transcription system with visually structured HTML output.

> This repository serves as a public timestamped proof and documentation reference for the underlying methodology. It contains **no operational source code**. The full system runs locally and is available for review upon request in the context of institutional cooperation.

---

## 🔗 Project Website (GitHub Pages)

👉 [Visit the public landing page](https://r2-mechanics.github.io/r2-mechanics/)

---

## Objective

R2 Mechanics was developed to process sensitive audio material (e.g., interviews, oral history) in a structured, transparent and privacy-compliant manner. The system offers:

- Local transcription (based on WhisperX)
- Speaker separation and attribution
- Chapter structure with time markers
- Visual HTML output with embedded audio
- Optional: automatic scene illustration

---

## Motivation

Research institutions, archives and cultural organizations need tools to structure audio content without reliance on cloud infrastructure or license risks. R2 Mechanics fills this gap.

---

## Component Overview (abstracted)

- WhisperX (local, GPU-accelerated)
- Chapter files (.txt with timestamps, titles, optional notes)
- HTML generator (custom visual styling)
- Optional: LLM-based summaries (offline)
- Optional: image generator (Stable Diffusion on dedicated system)

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

## Status

🛠 This repository documents the architecture and design intent of R2 Mechanics.  
🔒 The full codebase and processing pipeline are not public but verifiably implemented.
