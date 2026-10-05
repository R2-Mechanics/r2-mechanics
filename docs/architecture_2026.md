# R2 Mechanics – Public Architecture Diagram (2026)

Conceptual architecture of R2 Mechanics. The diagram shows layers and data flow, not the implementation. Orchestration logic, engine selection and decision rules are proprietary and not shown.

Source: this file (Mermaid, rendered by GitHub). Related: [System Overview](system_overview_en.md) · [Whitepaper](whitepaper_public_en.md) · [README](../README.md)

```mermaid
flowchart TD
    SRC["<b>SOURCE MEDIA</b><br/>audio · video<br/>original preserved as reference"]
    RST["Optional restoration<br/>historical / degraded recordings"]
    TL["<b>MEDIA &amp; TIMELINE LAYER</b><br/>speech · timing · segmentation"]

    SPK["<b>Speaker analysis</b><br/>speaker regions"]
    LNG["<b>Language analysis</b><br/>language regions · switches"]
    ASR["<b>Transcription evidence</b><br/>multiple independent ASR perspectives<br/>specialist multilingual processing"]

    MRG["<b>Provenance-aware text selection</b><br/>differences stay visible"]

    EVD["<b>EVIDENCE &amp; SOURCE TIMELINE</b><br/>speaker · language · text source<br/>review-worthy regions<br/>navigation back to the source"]

    LLM["<b>Optional analysis</b><br/>chapters · summaries · entities · context notes<br/>configurable · distinct from source evidence"]
    EXP["<b>Direct structured export</b><br/>JSON · SRT · VTT"]

    ARC["<b>INTERACTIVE MEDIA ARCHIVE</b><br/>synchronized player · searchable transcript<br/>evidence maps · filters · jump navigation<br/>portable, offline-capable HTML"]

    SRC --> TL
    SRC -. "historical material" .-> RST -.-> TL
    TL --> SPK
    TL --> LNG
    TL --> ASR
    SPK --> EVD
    LNG --> EVD
    ASR --> MRG --> EVD
    EVD --> EXP
    EVD --> ARC
    EVD -. "optional<br/>(skipped in fast media workflow)" .-> LLM
    LLM -.-> ARC

    classDef source fill:#16324a,stroke:#79a8ff,color:#edf3f8;
    classDef core fill:#12352f,stroke:#65d7bd,color:#edf3f8;
    classDef optional fill:#2b2b3a,stroke:#9aa3b5,color:#edf3f8,stroke-dasharray: 4 3;
    classDef delivery fill:#3a2f14,stroke:#e0b84f,color:#edf3f8;
    class SRC source;
    class TL,SPK,LNG,ASR,MRG,EVD core;
    class RST,LLM optional;
    class EXP,ARC delivery;
```

## Reading the diagram

- **Source first.** The original recording stays the temporal reference for everything downstream.
- **Evidence before interpretation.** Speaker, language and transcription-source information are mapped on one timeline before any optional analysis is added.
- **Optional analysis is a separate layer.** It can be configured for the purpose of the workflow and is not the source of the transcription.
- **Parallel outputs.** Structured exports and the interactive archive both come from the same evidence timeline. Neither is a prerequisite of the other.
- **Optional analysis feeds the archive.** Where a workflow asks for it, the analysis layer adds chapters, summaries and similar enrichment to the archive.
- **Fast media workflow.** A fast media run skips the full editorial analysis, not the evidence timeline: player, transcript, navigation and the maps that are available stay usable.
