# R2 Mechanics – Public Whitepaper 2026

**From difficult recordings to traceable records: offline-first archival transcription and evidence mapping**

R2 MECHANICS sp. z o.o., Poland · [r2-mechanics.com](https://r2-mechanics.com)

This whitepaper explains the methodological approach behind R2 Mechanics: what problem it addresses, which principles guide the design, and how evidence, uncertainty and optional interpretation are kept apart. It is a public, non-operational document. It does not contain implementation details and is not sufficient to rebuild the production pipeline (see section 16).

Related: [System Overview](system_overview_en.md) · [Architecture diagram](architecture_2026.md) · [README](../README.md)

---

## 1. Introduction

Archives, research institutions, public bodies and documentary projects hold recordings that are valuable and hard to use: long, multilingual, historical, degraded, with many speakers. A plain transcript is rarely enough. Users need to know who is speaking, in which language, where the text came from, which passages are uncertain, and how to get back to the original audio or video.

R2 Mechanics is built around that need. Its result is not a block of text but a structured, source-linked record that can be navigated, reviewed and delivered offline.

## 2. The archival audio problem

Standard transcription tends to fail in predictable ways:

- **Degraded or historical audio:** noise, narrow bandwidth, analogue artefacts and long pauses reduce what any single recogniser can recover.
- **Many speakers and overlap:** attribution errors are easy to make and hard to notice afterwards.
- **Language changes:** recordings with several languages, or fast switches within a conversation, break single-language assumptions.
- **Silent errors:** a single engine returns one confident-looking text, and its weaknesses are invisible to the reader.
- **Lost context:** a transcript detached from the media cannot be checked against what was actually said.

The problem is therefore not only recognition accuracy but also traceability and visibility of uncertainty.

## 3. Design principles

1. **Preserve the source.** The original medium is the reference.
2. **Treat transcription as evidence.** Recognition results are inputs to a record, not the record itself.
3. **Map before interpreting.** Speakers, languages and text sources are placed on the media timeline first.
4. **Keep uncertainty visible.** Differences and difficult regions stay in the result.
5. **Separate interpretation from evidence.** Optional analysis is a distinct layer.
6. **Stay navigable and portable.** Results work without a cloud service.
7. **Involve people.** Review indications support human review; they do not replace it.

## 4. Source-preserving processing

The original recording is never overwritten. A controlled processing copy is created and documented, so that every later result can be traced to the same source. For historical or degraded recordings an optional restoration step can improve intelligibility. The original remains the reference, and restored material can be explicitly identified as such in the result.

## 5. Multi-engine transcription as evidence

Recognition engines differ in strengths: some cope better with noise, some with particular languages, some with timing. R2 Mechanics can use several independent recognition perspectives on the same material and treat their outputs as evidence.

- Where independent perspectives agree, this can provide useful corroboration. Agreement is not proof, since independent systems can make the same mistake.
- Where they differ, the difference is handled in a documented way rather than silently smoothed over.
- The provenance of the selected text can be preserved, so a reader can see which source a passage comes from.

How candidates are weighed and selected is part of the proprietary pipeline and is not published. Established open technologies such as WhisperX and pyannote.audio remain part of the stack.

## 6. Evidence Mapping & Timeline Intelligence

This is the central capability of R2 Mechanics. Audio and video are treated as a timeline that carries structured information about the recording:

- speaker regions
- language regions
- text and engine provenance
- difficult or review-worthy regions
- direct navigation from any passage back to the original media

> R2 Mechanics does not reduce a recording to a single block of text. It can preserve and visualize speaker, language, transcription-source and review information along the original media timeline.

Depending on the workflow, the interactive archive can include visual maps above the transcript, for example a full-source bar and chapters, speaker tracks, language tracks, a text-source track, and markers for entities, context notes and review indications. Which tracks are present depends on the workflow; a fast media workflow, for instance, may omit chapters, entities and notes. Clicking a region moves to the corresponding passage and the corresponding point in the recording.

## 7. Speaker and language structure

**Speakers.** Speaker regions show who speaks when, so multi-speaker recordings can be read and navigated by turn. Speaker labels are technical by default. R2 Mechanics does not infer real-world identities; names are only attached where they are supported by the material or provided by the project.

**Languages.** Language regions show which language is spoken when. Together with speaker regions they make mixed-language and multi-speaker material understandable at a glance.

## 8. Multilingual processing

Recordings with several languages are a typical weak point of standard tools. R2 Mechanics can detect and structure several languages within one recording, including rapid switches, and keep them on one timeline. Language timelines and filters make such material navigable. Different recognition capabilities can be combined into one structured result, and specialised workflows exist for multilingual and language-specific material. Source-language transcription remains authoritative. Translation is an optional derived layer for research, access and multilingual navigation, kept distinct from the source-language text. The source-language transcript remains preserved as the reference, and the archive can switch between the source-language and the translated view. The public Multilingual Institutional Archive demonstration covers a long recording with 11 detected languages.

## 9. Provenance and uncertainty

Provenance answers where a passage came from. Uncertainty answers how much weight it can carry. R2 Mechanics treats both as part of the result:

- passages that deserve attention can be marked as review-worthy regions;
- where the independent perspectives agree only weakly over a whole recording, an overall review indication may be given instead of marking every passage;
- outputs can be labelled as provisional or pending review.

Review indications are navigation cues for human reviewers. They are not a measure of correctness or an error rate.

### Reference material as supporting evidence

Some projects come with existing documentation: historical transcripts, typescripts, scanned documents, PDFs, archival notes, speaker lists. R2 Mechanics can include such material as supporting evidence. Reference materials can be text-extracted and, where required, OCR-processed in a supporting workflow before comparison with the media-derived transcript, to support review, alignment and identification of discrepancies. Existing text layers can be extracted directly; OCR is used only where the material requires it.

- Original reference documents remain unchanged; extracted or OCR-derived text is treated as a derived working representation. Nothing is edited to fit the recording.
- Alignment is review support. It shows where the two differ; it does not automatically correct either side, and it does not replace or rewrite the transcription of the source recording. The media source remains the primary reference.
- A reference document is itself imperfect: typescripts and historical transcripts contain errors, omissions and editorial conventions, and OCR adds its own uncertainty. Discrepancies therefore call for human judgement.
- This branch is optional and is not used in every project.

## 10. Optional LLM analysis

Language models can add a further layer: chapters, summaries, entities and context notes. The separation is deliberate:

```text
source media
  → transcription / speaker / language evidence
    → structured timeline ──→ archive / structured outputs
         ├─ optional reference alignment (review support)
         ├─ optional translation (derived access layer)
         └─ optional LLM interpretation
```

Reference alignment, translation and LLM interpretation are parallel optional layers on the structured timeline. None of them is a source authority.

LLM-based interpretation can be configured according to the purpose of the workflow and remains distinct from source transcription and provenance. It is an optional analysis layer, not a source authority. It runs locally where the workflow requires, and it is only used when requested. Its outputs can contain errors and should be read as interpretation, not as evidence.

## 11. Interactive archive and media synchronization

The delivered result is a media-bound archive in portable HTML. Depending on the workflow it can include:

- synchronized audio or video player with a searchable transcript;
- reading, source and speaker views;
- evidence maps with speaker, language and source tracks, where the workflow provides them;
- filters and direct jump navigation;
- chapters and optional summaries;
- responsive and usable across desktop and mobile browsers, and offline-capable.

Structured exports (JSON, SRT, VTT) are derived from the same underlying record.

## 12. Fast media workflows

Not every task needs the full chain. For quick access to a recording R2 Mechanics offers a faster workflow: media player, transcript and navigation in one portable file, without the full editorial cascade, and with an optional, focused LLM summary. The evidence timeline and the maps that are available can still be used. The evidence-oriented workflow remains available when provenance and review visibility matter.

## 13. Offline-first / privacy-oriented operation

Material is processed on infrastructure operated by R2 Mechanics and is not sent to public cloud transcription services by default. Local and offline processing is supported. Deployment, handling and retention depend on the agreed environment and are defined in the project scope. Processing settings are recorded with each result so that runs can be reproduced. Archives can be delivered as self-contained, offline-capable packages. Where media is intentionally bound to an external institutional source, playback requires access to that source.

## 14. Public use cases and demonstrations

Typical users are archives and museums, universities and research institutions, public institutions with sensitive collections, and documentary and investigative media.

Current public demonstrations are hosted on [r2-mechanics.com](https://r2-mechanics.com/en/demos/): a difficult historical recording (Nixon Exhibit 21), a full-length legal hearing (Kennedy v. Braidwood), a multilingual institutional archive, two congressional hearings and a long-form lecture. They are working outputs; this repository holds no copy of them.

## 15. Limitations and human review

- Automatic recognition makes mistakes, especially with degraded audio, overlapping speech, rare languages and proper names.
- Speaker and language assignment can be wrong, particularly at short turns and rapid switches.
- Restoration can change what is audible; it is optional and can be explicitly identified.
- LLM-based analysis can be wrong or incomplete.
- Review indications show where to look; they do not guarantee that unmarked passages are correct.
- Reference documents and OCR output contain errors of their own. Alignment shows discrepancies; it does not decide which side is right.
- Translations are derived and can be inaccurate. The source-language transcript is authoritative.
- No transcript is a ground truth by itself. Project workflows can include human review before final delivery.

## 16. Proprietary boundary

This repository documents architecture, methodology, capabilities and public demonstrations. The operational production pipeline, its orchestration logic and implementation details remain proprietary. Review of the operational system is possible within cooperation frameworks or NDA-based audits.

---

**R2 MECHANICS sp. z o.o.**, Grabowa 14, 72-343 Karnice, Poland · [office@r2-mechanics.com](mailto:office@r2-mechanics.com) · [r2-mechanics.com](https://r2-mechanics.com) · Member of NVIDIA Inception
