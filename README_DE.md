# R2 Mechanics – Offline-First Archiv-Transkription & Evidence Mapping

Öffentliches Dokumentations-Repository von R2 Mechanics.

R2 Mechanics macht schwierige, lange und mehrsprachige Audio- und Videoaufnahmen zu strukturierten, quellenverknüpften Dokumenten: navigierbar, prüfbar und portabel, mit lokaler, Offline-First-Verarbeitung.

> Dieses Repository dokumentiert Architektur, Methodik, Fähigkeiten und öffentliche Demonstrationen.
> Die operative Produktionspipeline, ihre Orchestrierungslogik und die Implementierungsdetails bleiben proprietär und sind **nicht** Teil dieses Repositories.

R2 Mechanics wird von der R2 MECHANICS sp. z o.o., einer polnischen Gesellschaft mit beschränkter Haftung, betrieben (Polen).

**Website:** [r2-mechanics.com](https://r2-mechanics.com) · **Live-Demos:** [r2-mechanics.com/de/transkriptions-demos](https://r2-mechanics.com/de/transkriptions-demos/)

---

## Was R2 Mechanics leistet

Archive, Forschungseinrichtungen und Dokumentarprojekte besitzen oft Aufnahmen, an denen Standard-Transkription scheitert: degradiertes oder historisches Audio, viele Sprecher, schnelle Sprachwechsel, sehr lange Sitzungen.

R2 Mechanics behandelt eine solche Aufnahme nicht als einen einzigen Textblock, sondern als strukturierten, navigierbaren Datensatz, der mit dem Originalmedium verbunden bleibt:

- strukturierte Transkripte mit Sprecherzuordnung und zitierfähigen Zeitmarken
- Sprach- und Sprecherstruktur entlang der Original-Zeitachse
- sichtbare Prüfbereiche, wo die Beleglage schwach ist
- synchronisierte Wiedergabe, Suche und Kapitelnavigation
- portable Ergebnisse, die ohne Cloud-Dienst funktionieren

---

## Architektur

### Quellenerhaltend & Offline-First

- Die Verarbeitung kann vollständig lokal laufen, ohne Cloud-Abhängigkeit.
- Die Originalaufnahme bleibt die Referenz. Sie wird nie überschrieben; eine kontrollierte Arbeitskopie wird erstellt und dokumentiert.
- Ergebnisse bleiben auf das Quellmaterial zurückführbar.

### Multi-Engine-Forensik-Transkription

- Mehrere unabhängige Erkennungsperspektiven können gemeinsam auf dasselbe Material angewendet werden.
- Abweichende Ergebnisse werden verglichen und nachvollziehbar behandelt, statt stillschweigend zusammengeführt zu werden.
- Unsichere oder problematische Bereiche verschwinden nicht im Endtext.
- Die Herkunft (Provenance) des gewählten Textes kann erhalten bleiben.

Etablierte offene Technologien wie WhisperX und pyannote.audio bleiben Teil des Stacks. Die konkrete Orchestrierung wird nicht veröffentlicht.

### Evidence Mapping & Timeline Intelligence

Das ist eine zentrale R2-Fähigkeit. Audio und Video werden als navigierbare Zeitachse behandelt, die Folgendes trägt:

- Sprecherbereiche
- Sprachbereiche
- Text- und Engine-Provenance
- Stellen, die eine Prüfung verdienen
- direkte Navigation vom Transkript zurück zum Originalmedium
- visuelle Quellen- und Evidence-Maps für lange, mehrsprachige oder schwer transkribierbare Aufnahmen

> R2 Mechanics reduziert eine Aufnahme nicht auf einen einzelnen Textblock. Sprecher-, Sprach-, Transkriptionsquellen- und Prüfinformationen können entlang der Original-Zeitachse erhalten und visualisiert werden.

### Mehrsprachige Verarbeitung

- Erkennung und Strukturierung mehrerer Sprachen innerhalb einer Aufnahme, auch bei schnellen Sprachwechseln
- Sprach-Zeitachsen und Sprachfilter
- spezialisierte Workflows für mehrsprachiges und sprachspezifisches Material
- Ergebnisse unterschiedlicher Erkennungsfähigkeiten werden in einem strukturierten Ergebnis zusammengeführt
- optionale, getrennte Übersetzungsebene für Recherche und Zugang

### Interaktives Archiv & Auslieferung

- synchronisierter Audio-/Video-Player mit durchsuchbarem Transkript
- Sprecher-, Sprach- und Quellen-Zeitachsen mit Filtern und direkter Sprungnavigation
- portable Offline-HTML-Archive, nutzbar auf Desktop, Tablet und Smartphone
- strukturierte Formate wie JSON, SRT und VTT
- optionale redaktionelle oder LLM-basierte Auswertung (Kapitel, Zusammenfassungen, Entitäten, Kontexthinweise), stets als solche gekennzeichnet

### Schnelle Media-Workflows

- schnelle Verarbeitung von Medium und Transkript ohne die volle redaktionelle Kaskade
- Media-Player, Transkript und Navigation in einer portablen Datei
- optionale, fokussierte LLM-Zusammenfassung

---

## Öffentliche Showcases / Aktuelle Demos

Die aktuellen Demos werden ausschließlich auf [r2-mechanics.com](https://r2-mechanics.com) gehostet. Dieses Repository enthält keine Kopie ihrer Ergebnisse. Die Demo-Seiten selbst sind englischsprachig.

**Highlights**

- **[Nixon Exhibit 21 – Schwieriges historisches Audio](https://r2-mechanics.com/showcases/nixon-exhibit-21/)**
  Eine schwierige historische Aufnahme als strukturierter, prüfbarer Datensatz mit synchronisiertem Quellzugriff, Sprecherstruktur, diagnostischen Prüfbereichen und quellenausgerichtetem Transkript.
- **[Kennedy v. Braidwood – Lange juristische Aufnahme](https://r2-mechanics.com/showcases/kennedy-braidwood/)**
  Eine vollständige juristische Aufnahme mit synchronisiertem Audio, Kapitelnavigation, sprecherbewussten Abschnitten und direktem Zugriff auf die Quelle.
- **[Multilingual Institutional Archive](https://r2-mechanics.com/showcases/multilingual-institutional-archive/)**
  Eine lange institutionelle Aufnahme, rekonstruiert über 11 erkannte Sprachen und mehrere Sprecher, mit quellenverknüpften Auszügen, Sprach- und Sprechernavigation und einer separaten deutschen Übersetzungsebene.

**Weitere Beispiele**

- **[UAP Congressional Hearing (2024)](https://r2-mechanics.com/en/uap-congressional-hearing-2024)**
  Eine vollständige öffentliche Anhörung mit etwa 16 Sprechern: sprecherbewusste Segmentierung, Kapitelnavigation, Wiedergabe auf Segmentebene.
- **[UAP Congressional Hearing (Sep 2025)](https://r2-mechanics.com/en/uap-hearing-sep-2025-v1)**
  Eine lange öffentliche Anhörung als navigierbares, strukturiertes Transkript mit Zeitmarken-Navigation.
- **[Alan Watts – The Natural Environment](https://r2-mechanics.com/en/alan-watts-the-natural-environment/)**
  Ein langer Vortrag als synchronisiertes Lese- und Hörerlebnis.

Die früheren 2025-Demos, die in diesem Repository lagen, wurden zurückgezogen; ihre alten URLs leiten auf die aktuelle Demo-Übersicht weiter.

---

## Anwendungsfelder

- Archive & Museen
- Universitäten & Forschungseinrichtungen
- Öffentliche Einrichtungen & sensible Sammlungen
- Dokumentar- & Investigativmedien

---

## Datenschutz / Lokale Verarbeitung

Lokale und Offline-Verarbeitung wird unterstützt. Betrieb, Handhabung und Aufbewahrung richten sich nach der vereinbarten Umgebung und werden im Projektumfang festgelegt.

Reproduzierbare Läufe: Verarbeitungseinstellungen werden mit jedem Ergebnis festgehalten.


---

## Aktueller Stand (2026)

R2 Mechanics wurde 2026 aktiv weiterentwickelt. Die heutige Architektur geht deutlich über die 2025er Demos in diesem Repository hinaus:

- Multi-Engine-Transkription mit dokumentierter Text-Provenance
- Evidence- und Review-Maps entlang der Medien-Zeitachse
- mehrsprachige Verarbeitung mit sprachbewusster Struktur
- optionale Restaurierungs-Workflows für historische Aufnahmen, bei erhaltenem Original
- portable Offline-Archive, die auch auf Smartphone und Tablet funktionieren
- schnelle Media-Workflows neben der vollen redaktionellen Verarbeitung

---

## Proprietäre Grenze

Das öffentliche Repository dokumentiert Architektur, Methodik, Fähigkeiten und öffentliche Demonstrationen. Die operative Produktionspipeline, die Orchestrierungslogik und die Implementierungsdetails bleiben proprietär. Eine Einsicht ist im Rahmen von Kooperationen oder NDA-basierten Audits möglich.

---

## Historische Dokumente (2025)

Die folgenden Dokumente sind historisch (2025). Sie beschreiben **nicht** den aktuellen Produktionsstand; das tun die Abschnitte oben.

- [System Overview (DE)](docs/system_overview.md) · [System Overview (EN)](docs/system_overview_en.md)
- [Whitepaper (DE, PDF)](docs/whitepaper_de.pdf) · [Whitepaper (EN, PDF)](docs/whitepaper_en.pdf)
- [Projektsteckbrief (DE)](docs/projektsteckbrief.md)

---

## Kontakt

**R2 MECHANICS sp. z o.o.**
Grabowa 14, 72-343 Karnice, Polen
office@r2-mechanics.com
[r2-mechanics.com](https://r2-mechanics.com)

Eingetragen im Unternehmerregister des Nationalen Gerichtsregisters (KRS), Registergericht: Amtsgericht Stettin-Centrum (Szczecin-Centrum), XIII. Wirtschaftsabteilung. KRS 0001230326 · NIP 8571944744 · REGON 544304629

Member of NVIDIA Inception

---

[English → README.md](README.md) | [Français → README_FR.md](README_FR.md)
