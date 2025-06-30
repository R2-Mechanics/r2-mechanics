# 📜 System Overview – R2 Mechanics (public, non-operational)

This document describes the basic structure, goals, and methodological approach of **R2 Mechanics** – a system for structured, privacy-compliant transcription, annotation, and interactive visualization of audio-based content.

The goal is to provide a transparent, yet non-reproducible, description of the system architecture that establishes first-mover claims and offers orientation for potential partners.

---

## 🔧 System Structure (abstracted)

### **1. Input Formats**

* Individual audio files (e.g., `.mp3`, `.wav`)
* Optional: Supplementary metadata such as speaker lists, timecodes, annotations

---

### **2. Processing Steps**

1. **Transcription (local, offline):**

   * CUDA-accelerated
   * WhisperX with speaker diarization
   * Secure, GDPR-compliant operation without cloud

2. **Structuring:**

   * Reading or generating a chapter file (`.txt`)
   * Includes title, start time, description per chapter

3. **LLM-Assisted Analysis:**

   * Local generation of summaries
   * Automatic semantic notes with precise timestamps
   * Formatted as consistent second-based markers

4. **Visual Enrichment:**

   * Chapter-based image generation via Stable Diffusion
   * Local prompt-to-image pipeline
   * Serious, documentary-style illustrations

---

### **3. Output Formats**

* **Interactive HTML Transcript**:

  * Audio player with jump links
  * Automatically generated table of contents (TOC)
  * Chapter headings with SD-generated illustrations
  * Per-chapter summaries
  * Speaker segments with timestamps and roles
  * Integrated notes / side annotations (time-correlated)
  * Fully styled with R2 Mechanics CSS
  * Optional export as static website / GitHub Pages

---

## 🧹 Directory Structure (typical usage)

```
input_audio/           # Original audio files
output_html/           # Generated end formats
  project_transcript.html
chapters/              # Chapter structure files
  project_chapters.txt
summaries/             # Generated summaries
notes/                 # LLM annotation files
images/                # Generated illustrations
scripts/               # Own Python modules (not public)
```

---

## ✅ Features

* GPU-accelerated local transcription (WhisperX)
* Speaker diarization and timestamp generation
* Automated LLM annotations with exact times
* SD-generated chapter images, fully offline
* HTML export with audio, navigation, jump links
* 100 % offline and auditable – no cloud uploads
* Easily integrable into archival or research workflows

---

## 🔐 Disclosure & Protection

This document serves **transparency-based priority protection**:

* Contains no operational scripts or executable commands
* Methodology is systematically documented but not directly reproducible
* The full system is operated **exclusively locally and offline**

Demo versions and test runs are available for interested institutions upon request.

📧 Contact: **David Thiry** – [office@r2-mechanics.com](mailto:office@r2-mechanics.com)
