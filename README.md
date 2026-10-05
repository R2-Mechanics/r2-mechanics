# R2 Mechanics – Offline-First Archival Transcription & Evidence Mapping

Public documentation repository of R2 Mechanics.

R2 Mechanics turns difficult, long-form and multilingual audio and video into structured, source-linked records: navigable, reviewable and portable, with local, offline-first processing.

> This repository documents architecture, methodology, capabilities and public demonstrations.
> The operational production pipeline, its orchestration logic and implementation details remain proprietary and are **not** part of this repository.

R2 Mechanics is operated by R2 MECHANICS sp. z o.o., a Polish limited liability company based in Poland.

**Website:** [r2-mechanics.com](https://r2-mechanics.com) · **Live demos:** [r2-mechanics.com/en/demos](https://r2-mechanics.com/en/demos/)

---

## What it does

Archives, research institutions and documentary projects often hold recordings that standard transcription cannot handle: degraded or historical audio, many speakers, rapid language changes, very long sessions.

R2 Mechanics treats such a recording not as a single block of text but as a structured, navigable record that stays connected to the original media:

- structured transcripts with speaker attribution and citable timestamps
- language and speaker structure along the original timeline
- visible review regions where the evidence is weak
- synchronized playback, search and chapter navigation
- portable outputs that work without a cloud service

---

## Architecture

### Source-preserving & offline-first processing

- Processing can run fully locally, with no cloud dependency.
- The original recording remains the reference. It is never overwritten; a controlled processing copy is created and documented.
- Results stay traceable to the source material.

### Multi-engine forensic transcription

- Several independent recognition perspectives can be used together on the same material.
- Differing results are compared and handled in a documented way instead of being silently merged.
- Uncertain or problematic regions are not hidden in the final text.
- The provenance of the selected text can be preserved.

Established open technologies such as WhisperX and pyannote.audio remain part of the stack. The concrete orchestration is not published.

### Evidence Mapping & Timeline Intelligence

This is a core R2 capability. Audio and video are treated as a navigable timeline that carries:

- speaker regions
- language regions
- text and engine provenance
- passages that deserve review
- direct navigation from the transcript back to the original media
- visual source and evidence maps for long, multilingual or hard-to-transcribe recordings

> R2 Mechanics does not reduce a recording to a single block of text. It can preserve and visualize speaker, language, transcription-source and review information along the original media timeline.

### Multilingual processing

- detection and structuring of several languages within one recording, including rapid language switches
- language timelines and language filters
- specialized workflows for multilingual and language-specific material
- results from different recognition capabilities are merged into one structured record
- optional derived translation layer for research, access and multilingual navigation; the source-language transcript remains preserved as the reference, and the archive can switch between the source-language and the translated view

### Reference-assisted review

- Existing reference material (transcripts, typescripts, PDFs, scans, archival documentation, speaker lists and other metadata) can be included where a project has it.
- Existing text layers can be extracted directly; OCR is used only where the material requires it, in a supporting workflow before comparison with the media-derived transcript.
- Original reference documents remain unchanged; extracted or OCR-derived text is treated as a derived working representation.
- The text is aligned with and compared to the media-derived transcript to support review and the identification of discrepancies.
- Reference material supports review. It does not automatically correct or replace anything, and the media source remains the primary reference.
- This branch is optional and is not used in every project.

### Interactive archive & delivery

- synchronized audio/video player with a searchable transcript
- speaker, language and source timelines with filters and direct jump navigation
- portable offline HTML archives, responsive and usable across desktop and mobile browsers
- structured formats such as JSON, SRT and VTT
- optional editorial or LLM-based analysis (chapters, summaries, entities, context notes), always labelled as such

### Fast media workflows

- quick media-and-transcript processing without the full editorial cascade
- media player, transcript and navigation in one portable file
- optional, focused LLM summary

---

## Public Showcases / Current Demos

The current demos are hosted exclusively on [r2-mechanics.com](https://r2-mechanics.com). This repository holds no copy of their outputs.

**Featured**

- **[Nixon Exhibit 21 – Difficult Historical Audio](https://r2-mechanics.com/showcases/nixon-exhibit-21/)**
  A difficult historical recording as a structured, reviewable record with synchronized source access, speaker structure, diagnostic review regions and a source-aligned transcript.
- **[Kennedy v. Braidwood – Long-Form Legal Audio](https://r2-mechanics.com/showcases/kennedy-braidwood/)**
  A full-length legal recording with synchronized audio, chapter navigation, speaker-aware sections and direct access to the source.
- **[Multilingual Institutional Archive](https://r2-mechanics.com/showcases/multilingual-institutional-archive/)**
  A long institutional recording reconstructed across 11 detected languages and multiple speakers, with source-linked excerpts, language and speaker navigation and a separate German translation layer.

**Additional examples**

- **[UAP Congressional Hearing (2024)](https://r2-mechanics.com/en/uap-congressional-hearing-2024)**
  A full-length public hearing with about 16 speakers: speaker-aware segmentation, chapter navigation, segment-level playback.
- **[UAP Congressional Hearing (Sep 2025)](https://r2-mechanics.com/en/uap-hearing-sep-2025-v1)**
  A long public hearing as a navigable, structured transcript with timestamp navigation.
- **[Alan Watts – The Natural Environment](https://r2-mechanics.com/en/alan-watts-the-natural-environment/)**
  A long-form lecture as a synchronized reading and listening experience.

Earlier 2025 demos that were hosted in this repository have been retired; their old URLs forward to the current demo overview.

---

## Use Cases

- Archives & museums
- Universities & research institutions
- Public institutions & sensitive collections
- Documentary & investigative media

See [what you receive](https://r2-mechanics.com/en/what-you-receive/) and [use cases](https://r2-mechanics.com/en/use-cases/).

---

## Privacy / Local Processing

Local and offline processing is supported. Deployment, handling and retention depend on the agreed environment and are defined in the project scope.

Reproducible runs: processing settings are recorded with each result.


---

## Current status (2026)

R2 Mechanics has been actively developed throughout 2026. The architecture today goes well beyond the 2025 demos in this repository:

- multi-engine transcription with documented text provenance
- evidence and review maps along the media timeline
- multilingual processing with language-aware structure
- optional derived translation layer and reference-assisted review (extraction, alignment, discrepancy identification)
- optional restoration workflows for historical recordings, with the original preserved
- portable offline archives, responsive and usable across desktop and mobile browsers
- fast media workflows next to the full editorial processing

---

## Proprietary Boundary

The public repository documents architecture, methodology, capabilities and public demonstrations. The operational production pipeline, orchestration logic and implementation details remain proprietary. Access for review is possible within cooperation frameworks or NDA-based audits.

---

## Documentation

- [System Overview 2026 (EN)](docs/system_overview_en.md) · [System Overview 2026 (DE)](docs/system_overview.md)
- [Whitepaper 2026 (EN)](docs/whitepaper_public_en.md) · [Whitepaper 2026 (DE)](docs/whitepaper_public.md)
- [Architecture diagram 2026](docs/architecture_2026.md)

**Historical (2025)** – these do **not** describe the current production state: [Whitepaper 2025 (EN, PDF)](docs/whitepaper_en.pdf) · [Whitepaper 2025 (DE, PDF)](docs/whitepaper_de.pdf) · [Project Profile (DE)](docs/projektsteckbrief.md)
---

## Contact

**R2 MECHANICS sp. z o.o.**
Grabowa 14, 72-343 Karnice, Poland
office@r2-mechanics.com
[r2-mechanics.com](https://r2-mechanics.com/en/contact/)

Registered in the Register of Entrepreneurs of the National Court Register (KRS), District Court Szczecin-Centrum in Szczecin, XIII Commercial Division. KRS 0001230326 · NIP 8571944744 · REGON 544304629

Member of NVIDIA Inception

---

[Deutsch → README_DE.md](README_DE.md) | [Français → README_FR.md](README_FR.md)
