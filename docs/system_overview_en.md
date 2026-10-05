# System Overview – R2 Mechanics (public, non-operational) · 2026

Technical short reference for the architecture of R2 Mechanics. It describes layers, concepts and outputs. It is not an implementation guide: orchestration logic, engine selection, decision rules, thresholds and prompts are proprietary and not part of this repository.

Related: [Architecture diagram](architecture_2026.md) · [Whitepaper](whitepaper_public_en.md) · [README](../README.md) · [Live demos](https://r2-mechanics.com/en/demos/)

---

## 1. What changed since 2025

The 2025 description was a linear chain: transcription, speaker separation, an LLM-written report. Today R2 Mechanics is organised around a different idea:

> keep the source → structure the evidence → map it on the timeline → keep uncertainty visible → only then, optionally, interpret.

Transcription is one evidence layer among several. Language and speaker structure, text provenance and review-worthy regions are mapped on the same timeline as the original media. LLM-based analysis is an optional layer on top, not the source of the transcript.

---

## 2. Architecture layers

```text
SOURCE MEDIA                        audio / video, original preserved
        ↓
SOURCE & TIMELINE ANALYSIS          speech structure · speaker regions
                                    language regions · media timing
        ↓
TRANSCRIPTION LAYER                 multiple independent ASR perspectives
                                    provenance-aware text selection
                                    specialist multilingual processing
        ↓
EVIDENCE & TIMELINE INTELLIGENCE    speaker · language · text-source mapping
                                    difficult / review-worthy regions
                                    synchronized navigation to the source
        ↓
OPTIONAL ANALYSIS                   focused summaries, editorial and
                                    contextual enrichment — only when the
                                    workflow asks for it
        ↓
DELIVERY                            synchronized media player · searchable
                                    transcript · visual maps · filters
                                    offline HTML · JSON / SRT / VTT
```

The same flow as a diagram: [architecture_2026.md](architecture_2026.md). Two optional branches sit alongside this flow: a derived translation layer and reference-assisted review (concepts D and G).

---

## 3. Core concepts

### A. Source-preserving processing
The original recording remains the temporal reference. It is never overwritten; a controlled processing copy is created and documented. Every result stays traceable to the source.

### B. Multi-engine transcription
Several independent transcription perspectives can be used on the same material. Differences are compared and handled in a documented way rather than silently merged. The provenance of the selected text can be preserved. How candidates are weighed is not published. Established open technologies such as WhisperX and pyannote.audio remain part of the stack.

### C. Evidence Mapping & Timeline Intelligence
A core R2 capability. The recording is treated as a navigable timeline that carries:

- speaker regions
- language regions
- text and engine provenance
- difficult or review-worthy regions
- direct navigation back to the original media

> R2 Mechanics does not reduce a recording to a single block of text. It can preserve and visualize speaker, language, transcription-source and review information along the original media timeline.

Review indications are navigation cues for human reviewers. They are not a statement of correctness or error rate.

### D. Multilingual processing
Several languages, including rapid switches within one recording, can be detected and structured. Language timelines and filters make mixed-language material navigable. Different recognition capabilities can be combined into one structured result. An optional, derived translation layer (for research, access and multilingual navigation) is kept separate: the source-language transcript remains preserved as the reference, and the archive can switch between the source-language and the translated view.

### E. Processing profiles
Described conceptually. Concrete configurations are not published.

| Profile | Purpose |
|---|---|
| Forensic / evidence-oriented processing | Difficult or historical material; several evidence layers; review visibility |
| Multilingual specialist processing | Recordings with several or rapidly changing languages, or with a specific language focus |
| Fast media processing | Quick media-and-transcript output without the full editorial cascade |

For historical or degraded recordings an optional restoration step is available. The original stays the reference.

### F. Archive & delivery
The result is a media-bound, navigable and offline-capable archive. Depending on the workflow it can include a synchronized player, searchable transcript, reading / source / speaker views, evidence maps, filters and jump navigation. Structured exports (JSON, SRT, VTT) come from the same evidence timeline.

### G. Reference-assisted review
Where a project has existing reference material (transcripts, typescripts, PDFs, scans, archival documentation, speaker lists or other metadata), it can be included as supporting evidence. Reference materials can be text-extracted and, where required, OCR-processed in a supporting workflow before comparison with the media-derived transcript. Existing text layers can be extracted directly; OCR is used only where the material requires it. Original reference documents remain unchanged; extracted or OCR-derived text is treated as a derived working representation. The text is compared and aligned with the media-derived transcript to support review and the identification of discrepancies. Reference material does not automatically correct or replace anything, and the media source remains the primary reference. The branch is optional and not used in every project.

---

## 4. Optional analysis layer

Chapters, summaries, entities and context notes can be generated with local language models when a workflow asks for them. LLM-based interpretation can be configured according to the purpose of the workflow and remains distinct from source transcription and provenance. Outputs can be labelled as provisional or pending review.

---

## 5. Inputs and outputs

| Inputs | Outputs |
|---|---|
| Audio and video files | Interactive offline HTML archive |
| Optional metadata (e.g. speaker lists) and reference material (transcripts, scans, PDFs, archival documentation) | Structured transcript with speakers and timestamps |
| | JSON, SRT, VTT |
| | Optional summaries, chapters, entities, context notes, derived translation layer, reference comparison for review support |

---

## 6. Operation

- Local, offline-first processing is supported; material is not sent to public cloud transcription services by default.
- Handling, storage and retention conditions are defined in the project scope.
- Runs are reproducible: processing settings are recorded with each result.
- Project workflows can include human review before final delivery.

See [Trust](https://r2-mechanics.com/en/trust/).

---

## 7. Disclosure & boundary

This document serves transparent, non-operational disclosure of capabilities and methodology.

- It contains no scripts, commands, configurations or decision rules.
- It is not sufficient to reproduce the production pipeline.
- Review of the operational system is possible within cooperation frameworks or NDA-based audits.

Operated by **R2 MECHANICS sp. z o.o.**, Poland · [office@r2-mechanics.com](mailto:office@r2-mechanics.com) · [r2-mechanics.com](https://r2-mechanics.com)
