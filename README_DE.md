# 🧭 R2 Mechanics – Strukturierte Offline-Transkription & KI-Analyse-Infrastruktur

Dies ist das offizielle Dokumentations-Repository von **R2 Mechanics** — ein modulares, vollständig offline arbeitendes Transkriptions- und Analysesystem für Archive, Forschungseinrichtungen und kulturelle Institutionen.  
Die Plattform verarbeitet komplexes Audio- und Videomaterial zu strukturierten, sprechergetrennten und navigierbaren HTML-Berichten — **ohne Cloud-Abhängigkeit**.

> Dieses Repository dient als öffentlicher, datierter Nachweis der Methodik und Systemarchitektur.  
> Es enthält **keinen operativen Quellcode**. Das vollständige System läuft lokal und kann im Rahmen von Kooperationen oder NDA-basierten Audits eingesehen werden.

---

## 🌐 Öffentliche Website

👉 [Offizielle Landingpage (GitHub Pages)](https://r2-mechanics.github.io/r2-mechanics/)

---

## 🎧 Live-Demos

Interaktive HTML-Berichte mit eingebettetem Audio, Kapitelnavigation und Sprecher-Diarisierung:

- ▶️ [JFK Moon Speech Demo](https://r2-mechanics.github.io/r2-mechanics/JFK-Moonspeech.html) — strukturierte Rede mit Kapiteln und Zeitmarken  
- ▶️ [Apollo 11 Press Conference](https://r2-mechanics.github.io/r2-mechanics/demo-apollo11/apollo11.html) — mehrere Sprecher, historische Q&A-Sitzung  
- ▶️ [Kennedy v. Braidwood Management — Oral Argument Transcript (Demo)](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html) — Dual-Pipeline-Beispiel mit interaktiver Wiedergabe (Pipeline A) und forschungsorientiertem Transkript (Pipeline B). [🔗 Vollansicht öffnen](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html)  
- ▶️ [Alan Watts — The Natural Environment (Interactive Edition)](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html) — philosophische Vorlesung mit präziser Diarisierung, synchronisiertem Audio-Text-Abgleich, Kapitelstruktur und offline-kompatibler Dokumentation. [🔗 Vollansicht öffnen](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html)  
- ▶️ [UAP Congressional Hearing (2024)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing/uap-2024.html) — zweistündige Sitzung mit vollständiger Struktur  
- ▶️ [UAP Hearing 2025 (EN Demo)](https://project.r2-mechanics.com/demos/uap-hearing-Sep-2025/uap-hearing-Sep-2025.html) — strukturierte Version mit Annotationen und Auto-Scroll  
- ▶️ [UAP Hearing (PL/EN Demo)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing-pl/start-pl.html) — zweisprachige Demo  
- ▶️ [Oral-History.Digital – Pagenstecher Project](https://r2-mechanics.github.io/r2-mechanics/vortraege-de/pagenstecher-project.html) — Archiv-Transkript im HTML-Format  

Diese Demos zeigen die **strukturierte Offline-Ausgabe** mit semantischer Segmentierung, Sprecher-Zuordnung und optionalen visuellen Erweiterungen.

---

## 🎯 Zielsetzung

**R2 Mechanics** ermöglicht die strukturierte, transparente und DSGVO-konforme Verarbeitung sensibler Audio- und Videomaterialien – z. B. Interviews, Oral-History-Aufnahmen oder historische Protokolle.

### Hauptmerkmale

- 100 % **Offline-Betrieb** — air-gapped, ohne Telemetrie  
- **GPU-beschleunigte Transkription** mit WhisperX (large-v3)  
- **Sprecher-Diarisierung** mit pyannote.audio (4.x)  
- **Semantische Kapitelbildung & Zusammenfassungen** über lokale LLMs (LM Studio / Ollama)  
- **Strukturierte HTML/DOCX-Ausgabe** zur Archivierung oder Publikation  
- **Energieautarke Infrastruktur** mit USV-gepufferter Redundanz  

---

## 🧩 Systemarchitektur (Überblick)

R2 Mechanics arbeitet innerhalb der isolierten Umgebung `r2_asr4` und kombiniert:

| Ebene | Komponente | Funktion |
|-------|-------------|-----------|
| **ASR + Diarisierung** | WhisperX (large-v3) + pyannote.audio (4.x) | Wortgenaue Transkription und Sprecher-Segmentierung |
| **Semantische Analyse** | Lokales LLM (LM Studio / Ollama) | Themen-, Entitäten- und Zusammenfassungs-Generierung |
| **Ausgabe-Ebene** | Markdown / DOCX / HTML | Strukturierte Berichte mit Kapitel-Navigation |
| **Audit & Resilienz** | WARC-Archive + Logs | Deterministische, reproduzierbare Läufe |
| **Energie-System** | Erneuerbare / USV / NVMe-Infrastruktur | Dauerbetrieb 24-7 (10-Jahres-Zyklus) |

---

## 🛡 Governance & Compliance (Überblick)

- **Zugriffssteuerung & Governance** – projektweise Trennung, RBAC (owner / contributor / viewer), optionale 2FA/MFA; keine Subprozessoren.  
- **Datenlebenszyklus & Aufbewahrung** – definierter Zyklus (Ingest → Processing → Review → Delivery → Deletion); 30 / 60 / 90-Tage-Optionen.  
- **Reproduzierbarkeit & Version-Pinning** – jeder Lauf speichert Modell-Versionen (WhisperX large-v3, pyannote.audio 4.x), CUDA/Torch-Stack und Config-Hashes.  
- **Sicherheits-Profil** – vollständig air-gapped, verschlüsselte Eingabe und Speicherung, unveränderliche Offline-Backups.  
- **Compliance** – Verarbeitung ausschließlich innerhalb der EU (Polen); AVV/DPA und TOM-Dokumente auf Anfrage verfügbar.  
- **Release-Management** – quartalsweise Releases; Projekt-Versionen bleiben gefroren bis zur Freigabe.  
- **Datenschutz & Transparenz** – NDA-basierter Zugang möglich; alle Phasen auditierbar; Quellcode aus Sicherheits- und Integritätsgründen nicht öffentlich.  

---

## ⚙️ Komponenten (abstrahiert)

- **WhisperX (Offline CUDA)** – ASR + Alignment  
- **pyannote.audio (4.x)** – Sprecher-Diarisierung  
- **LLM-Analyse (LM Studio / Ollama)** – Themen, Entitäten, Zusammenfassungen  
- **HTML-Generator** – strukturierte Berichte mit Audio-Playback  
- **Optionale Module** – SDXL-Bildgenerierung, mehrsprachige Kontext-Ebenen  

---

## 📄 Dokumentation

- [System Overview (DE)](docs/system_overview.md)  
- [System Overview (EN)](docs/system_overview_en.md)  
- [Whitepaper (DE, PDF)](docs/whitepaper_de.pdf)  
- [Whitepaper (EN, PDF)](docs/whitepaper_en.pdf)  
- [Projektsteckbrief (DE)](docs/projektsteckbrief.md)

---

## 📬 Kontakt

**David Thiry**  
📧 office@r2-mechanics.com  
🌐 [https://r2-mechanics.com](https://r2-mechanics.com)  
🔗 [GitHub: R2-Mechanics / r2-mechanics](https://github.com/R2-Mechanics/r2-mechanics)

---

## 🔒 Status

🧱 Dieses Repository dokumentiert die **Architektur, Methodik und Compliance-Struktur** von R2 Mechanics.  
🛠 Die operative Pipeline ist funktionsfähig und unter NDA verifizierbar, jedoch nicht öffentlich verfügbar.

---

📄 [Français → README_FR.md](README_FR.md)  |  [English → README.md](README.md)
