# System Overview – R2 Mechanics (öffentlich, nicht-operativ) · 2026

Technische Kurzreferenz zur Architektur von R2 Mechanics. Sie beschreibt Ebenen, Konzepte und Ergebnisse. Sie ist keine Implementierungsanleitung: Orchestrierungslogik, Engine-Auswahl, Entscheidungsregeln, Schwellenwerte und Prompts sind proprietär und nicht Teil dieses Repositories.

Siehe auch: [Architekturdiagramm](architecture_2026.md) · [Whitepaper](whitepaper_public.md) · [README](../README_DE.md) · [Live-Demos](https://r2-mechanics.com/de/transkriptions-demos/)

---

## 1. Was sich seit 2025 geändert hat

Die Beschreibung von 2025 war eine lineare Kette: Transkription, Sprechertrennung, LLM-Bericht. Heute folgt R2 Mechanics einer anderen Idee:

> Quelle erhalten → Evidenz strukturieren → auf der Zeitachse kartieren → Unsicherheit sichtbar halten → erst danach optional interpretieren.

Die Transkription ist eine Evidenzebene unter mehreren. Sprach- und Sprecherstruktur, Text-Provenance und prüfwürdige Bereiche werden auf derselben Zeitachse wie das Originalmedium abgebildet. LLM-basierte Analyse ist eine optionale Ebene darüber und nicht die Quelle des Transkripts.

---

## 2. Architekturebenen

```text
QUELLMEDIUM                         Audio / Video, Original erhalten
        ↓
QUELLEN- & ZEITACHSENANALYSE        Sprechaktivität · Sprecherbereiche
                                    Sprachbereiche · Medien-Timing
        ↓
TRANSKRIPTIONSEBENE                 mehrere unabhängige ASR-Perspektiven
                                    provenance-bewusste Textauswahl
                                    spezialisierte mehrsprachige Verarbeitung
        ↓
EVIDENCE & TIMELINE INTELLIGENCE    Sprecher-, Sprach-, Textquellen-Mapping
                                    schwierige / prüfwürdige Bereiche
                                    synchronisierte Navigation zur Quelle
        ↓
OPTIONALE ANALYSE                   fokussierte Zusammenfassungen,
                                    redaktionelle und kontextuelle Anreicherung
                                    — nur wenn der Workflow es verlangt
        ↓
AUSLIEFERUNG                        synchronisierter Media-Player · durchsuch-
                                    bares Transkript · visuelle Maps · Filter
                                    Offline-HTML · JSON / SRT / VTT
```

Derselbe Ablauf als Diagramm: [architecture_2026.md](architecture_2026.md). Zwei optionale Zweige liegen neben diesem Ablauf: eine abgeleitete Übersetzungsebene und die referenzgestützte Prüfung (Konzepte D und G).

---

## 3. Kernkonzepte

### A. Quellenerhaltende Verarbeitung
Die Originalaufnahme bleibt die zeitliche Referenz. Sie wird nie überschrieben; eine kontrollierte Arbeitskopie wird erstellt und dokumentiert. Jedes Ergebnis bleibt auf die Quelle zurückführbar.

### B. Multi-Engine-Transkription
Mehrere unabhängige Transkriptionsperspektiven können auf dasselbe Material angewendet werden. Unterschiede werden verglichen und nachvollziehbar behandelt, statt stillschweigend zusammengeführt zu werden. Die Herkunft des gewählten Textes kann erhalten bleiben. Wie Kandidaten gewichtet werden, wird nicht veröffentlicht. Etablierte offene Technologien wie WhisperX und pyannote.audio bleiben Teil des Stacks.

### C. Evidence Mapping & Timeline Intelligence
Eine zentrale R2-Fähigkeit. Die Aufnahme wird als navigierbare Zeitachse behandelt, die Folgendes trägt:

- Sprecherbereiche
- Sprachbereiche
- Text- und Engine-Provenance
- schwierige oder prüfwürdige Bereiche
- direkte Navigation zurück zum Originalmedium

> R2 Mechanics reduziert eine Aufnahme nicht auf einen einzelnen Textblock. Sprecher-, Sprach-, Transkriptionsquellen- und Prüfinformationen können entlang der Original-Zeitachse erhalten und visualisiert werden.

Prüfhinweise sind Navigationshilfen für menschliche Prüfer. Sie sind keine Aussage über Korrektheit oder Fehlerrate.

### D. Mehrsprachige Verarbeitung
Mehrere Sprachen, auch schnelle Wechsel innerhalb einer Aufnahme, können erkannt und strukturiert werden. Sprach-Zeitachsen und Filter machen gemischtsprachiges Material navigierbar. Unterschiedliche Erkennungsfähigkeiten können in einem strukturierten Ergebnis zusammengeführt werden. Eine optionale, abgeleitete Übersetzungsebene (für Recherche, Zugang und mehrsprachige Navigation) bleibt getrennt: Das Transkript in der Quellsprache bleibt als Referenz erhalten, und das Archiv kann zwischen der Quellsprach- und der übersetzten Ansicht umschalten.

### E. Verarbeitungsprofile
Nur konzeptionell beschrieben. Konkrete Konfigurationen werden nicht veröffentlicht.

| Profil | Zweck |
|---|---|
| Forensische / evidenzorientierte Verarbeitung | Schwieriges oder historisches Material; mehrere Evidenzebenen; Prüfsichtbarkeit |
| Mehrsprachige Spezialverarbeitung | Aufnahmen mit mehreren oder schnell wechselnden Sprachen oder mit besonderem Sprachfokus |
| Schnelle Media-Verarbeitung | Schnelle Ausgabe aus Medium und Transkript ohne die volle redaktionelle Kaskade |

Für historische oder degradierte Aufnahmen steht ein optionaler Restaurierungsschritt zur Verfügung. Das Original bleibt die Referenz.

### F. Archiv & Auslieferung
Das Ergebnis ist ein mediengebundenes, navigierbares und offline-fähiges Archiv. Je nach Workflow kann es einen synchronisierten Player, ein durchsuchbares Transkript, Lese-, Quellen- und Sprecheransicht, Evidence-Maps, Filter und Sprungnavigation enthalten. Strukturierte Exporte (JSON, SRT, VTT) entstehen aus derselben Evidenz-Zeitachse.

### G. Referenzgestützte Prüfung
Wenn ein Projekt vorhandenes Referenzmaterial besitzt (Transkripte, Typoskripte, PDFs, Scans, Archivdokumentation, Sprecherlisten oder andere Metadaten), kann es als unterstützende Evidenz einbezogen werden. Referenzmaterial kann textlich erschlossen und, wo erforderlich, in einem unterstützenden Workflow per OCR verarbeitet werden, bevor es mit dem aus dem Medium abgeleiteten Transkript verglichen wird. Vorhandene Textebenen können direkt extrahiert werden; OCR kommt nur zum Einsatz, wenn das Material es erfordert. Originale Referenzdokumente bleiben unverändert; extrahierter oder per OCR gewonnener Text wird als abgeleitete Arbeitsrepräsentation behandelt. Der Text wird mit dem aus dem Medium abgeleiteten Transkript verglichen und abgeglichen, um die Prüfung und das Erkennen von Abweichungen zu unterstützen. Referenzmaterial korrigiert oder ersetzt nichts automatisch, und die Medienquelle bleibt die primäre Referenz. Der Zweig ist optional und wird nicht in jedem Projekt genutzt.

---

## 4. Optionale Analyseebene

Kapitel, Zusammenfassungen, Entitäten und Kontexthinweise können mit lokalen Sprachmodellen erzeugt werden, wenn ein Workflow sie verlangt. LLM-basierte Interpretation kann je nach Zweck des Workflows konfiguriert werden und bleibt von Quelltranskription und Provenance getrennt. Ergebnisse können als vorläufig oder prüfungsausstehend gekennzeichnet werden.

---

## 5. Ein- und Ausgaben

| Eingaben | Ausgaben |
|---|---|
| Audio- und Videodateien | Interaktives Offline-HTML-Archiv |
| Optionale Metadaten (z. B. Sprecherlisten) und Referenzmaterial (Transkripte, Scans, PDFs, Archivdokumentation) | Strukturiertes Transkript mit Sprechern und Zeitmarken |
| | JSON, SRT, VTT |
| | Optional Zusammenfassungen, Kapitel, Entitäten, Kontexthinweise, abgeleitete Übersetzungsebene, Referenzvergleich zur Prüfunterstützung |

---

## 6. Betrieb

- Lokale, Offline-First-Verarbeitung wird unterstützt; Material wird standardmäßig nicht an öffentliche Cloud-Transkriptionsdienste gesendet.
- Handhabung, Speicherung und Aufbewahrung werden im Projektumfang festgelegt.
- Läufe sind reproduzierbar: Verarbeitungseinstellungen werden mit jedem Ergebnis festgehalten.
- Projekt-Workflows können eine menschliche Prüfung vor der finalen Auslieferung enthalten.

Siehe [Vertrauen / Trust](https://r2-mechanics.com/en/trust/).

---

## 7. Offenlegung & Grenze

Dieses Dokument dient der transparenten, nicht-operativen Offenlegung von Fähigkeiten und Methodik.

- Es enthält keine Skripte, Befehle, Konfigurationen oder Entscheidungsregeln.
- Es reicht nicht aus, die Produktionspipeline nachzubauen.
- Eine Einsicht in das operative System ist im Rahmen von Kooperationen oder NDA-basierten Audits möglich.

Betrieben von der **R2 MECHANICS sp. z o.o.**, Polen · [office@r2-mechanics.com](mailto:office@r2-mechanics.com) · [r2-mechanics.com](https://r2-mechanics.com)
