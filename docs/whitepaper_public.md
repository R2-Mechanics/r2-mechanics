# R2 Mechanics – Öffentliches Whitepaper 2026

**Von schwierigen Aufnahmen zu nachvollziehbaren Dokumenten: Offline-First Archiv-Transkription und Evidence Mapping**

R2 MECHANICS sp. z o.o., Polen · [r2-mechanics.com](https://r2-mechanics.com)

Dieses Whitepaper erklärt den methodischen Ansatz hinter R2 Mechanics: welches Problem er adressiert, welche Prinzipien das Design leiten und wie Evidenz, Unsicherheit und optionale Interpretation getrennt bleiben. Es ist ein öffentliches, nicht-operatives Dokument. Es enthält keine Implementierungsdetails und reicht nicht aus, die Produktionspipeline nachzubauen (siehe Abschnitt 16).

Siehe auch: [System Overview](system_overview.md) · [Architekturdiagramm](architecture_2026.md) · [README](../README_DE.md)

---

## 1. Einführung

Archive, Forschungseinrichtungen, öffentliche Stellen und Dokumentarprojekte besitzen Aufnahmen, die wertvoll und schwer nutzbar sind: lang, mehrsprachig, historisch, degradiert, mit vielen Sprechern. Ein einfaches Transkript reicht selten. Nutzer müssen wissen, wer spricht, in welcher Sprache, woher der Text stammt, welche Stellen unsicher sind und wie man zum Original-Audio oder -Video zurückkommt.

R2 Mechanics ist auf diesen Bedarf ausgelegt. Das Ergebnis ist kein Textblock, sondern ein strukturierter, quellenverknüpfter Datensatz, der navigiert, geprüft und offline ausgeliefert werden kann.

## 2. Das Problem archivalischer Audioaufnahmen

Standard-Transkription scheitert auf vorhersehbare Weise:

- **Degradiertes oder historisches Audio:** Rauschen, schmale Bandbreite, analoge Artefakte und lange Pausen begrenzen, was ein einzelner Erkenner wiedergewinnen kann.
- **Viele Sprecher und Überlappung:** Zuordnungsfehler passieren leicht und fallen später schwer auf.
- **Sprachwechsel:** Aufnahmen mit mehreren Sprachen oder schnellen Wechseln innerhalb eines Gesprächs brechen Ein-Sprach-Annahmen.
- **Stille Fehler:** Eine einzelne Engine liefert einen überzeugend wirkenden Text, dessen Schwächen für den Leser unsichtbar sind.
- **Verlorener Kontext:** Ein vom Medium gelöstes Transkript lässt sich nicht gegen das tatsächlich Gesagte prüfen.

Das Problem ist also nicht nur die Erkennungsgenauigkeit, sondern auch Nachvollziehbarkeit und Sichtbarkeit von Unsicherheit.

## 3. Designprinzipien

1. **Die Quelle erhalten.** Das Originalmedium ist die Referenz.
2. **Transkription als Evidenz behandeln.** Erkennungsergebnisse sind Eingaben für einen Datensatz, nicht der Datensatz selbst.
3. **Erst kartieren, dann interpretieren.** Sprecher, Sprachen und Textquellen werden zuerst auf der Medien-Zeitachse platziert.
4. **Unsicherheit sichtbar halten.** Unterschiede und schwierige Bereiche bleiben im Ergebnis.
5. **Interpretation von Evidenz trennen.** Optionale Analyse ist eine eigene Ebene.
6. **Navigierbar und portabel bleiben.** Ergebnisse funktionieren ohne Cloud-Dienst.
7. **Menschen einbeziehen.** Prüfhinweise unterstützen die menschliche Prüfung und ersetzen sie nicht.

## 4. Quellenerhaltende Verarbeitung

Die Originalaufnahme wird nie überschrieben. Eine kontrollierte Arbeitskopie wird erstellt und dokumentiert, sodass jedes spätere Ergebnis auf dieselbe Quelle zurückführbar ist. Bei historischen oder degradierten Aufnahmen kann ein optionaler Restaurierungsschritt die Verständlichkeit verbessern. Das Original bleibt die Referenz, und restauriertes Material kann im Ergebnis ausdrücklich als solches kenntlich gemacht werden.

## 5. Multi-Engine-Transkription als Evidenz

Erkennungs-Engines haben unterschiedliche Stärken: manche kommen besser mit Rauschen zurecht, manche mit bestimmten Sprachen, manche mit Timing. R2 Mechanics kann mehrere unabhängige Erkennungsperspektiven auf dasselbe Material anwenden und ihre Ausgaben als Evidenz behandeln.

- Wo unabhängige Erkennungsperspektiven übereinstimmen, kann dies eine zusätzliche Bestätigung liefern. Übereinstimmung ist kein Beweis, denn unabhängige Systeme können denselben Fehler machen.
- Wo sie abweichen, wird der Unterschied nachvollziehbar behandelt, statt stillschweigend geglättet zu werden.
- Die Herkunft des gewählten Textes kann erhalten bleiben, sodass ein Leser sieht, aus welcher Quelle eine Passage stammt.

Wie Kandidaten gewichtet und ausgewählt werden, gehört zur proprietären Pipeline und wird nicht veröffentlicht. Etablierte offene Technologien wie WhisperX und pyannote.audio bleiben Teil des Stacks.

## 6. Evidence Mapping & Timeline Intelligence

Das ist die zentrale Fähigkeit von R2 Mechanics. Audio und Video werden als Zeitachse behandelt, die strukturierte Informationen über die Aufnahme trägt:

- Sprecherbereiche
- Sprachbereiche
- Text- und Engine-Provenance
- schwierige oder prüfwürdige Bereiche
- direkte Navigation von jeder Passage zurück zum Originalmedium

> R2 Mechanics reduziert eine Aufnahme nicht auf einen einzelnen Textblock. Sprecher-, Sprach-, Transkriptionsquellen- und Prüfinformationen können entlang der Original-Zeitachse erhalten und visualisiert werden.

Je nach Workflow kann das interaktive Archiv visuelle Maps über dem Transkript enthalten, zum Beispiel eine Volltext-Leiste und Kapitel, Sprecherspuren, Sprachspuren, eine Textquellen-Spur sowie Marker für Entitäten, Kontexthinweise und Prüfhinweise. Welche Spuren vorhanden sind, hängt vom Workflow ab; ein schneller Media-Workflow kann etwa Kapitel, Entitäten und Hinweise weglassen. Ein Klick auf einen Bereich springt zur entsprechenden Passage und zur entsprechenden Stelle in der Aufnahme.

## 7. Sprecher- und Sprachstruktur

**Sprecher.** Sprecherbereiche zeigen, wer wann spricht, sodass Mehrsprecher-Aufnahmen nach Redebeiträgen gelesen und navigiert werden können. Sprecherlabels sind standardmäßig technisch. R2 Mechanics schließt nicht auf reale Identitäten; Namen werden nur dort zugeordnet, wo das Material sie stützt oder das Projekt sie vorgibt.

**Sprachen.** Sprachbereiche zeigen, welche Sprache wann gesprochen wird. Zusammen mit den Sprecherbereichen machen sie gemischtsprachiges und mehrsprecheriges Material auf einen Blick verständlich.

## 8. Mehrsprachige Verarbeitung

Aufnahmen mit mehreren Sprachen sind ein typischer Schwachpunkt von Standardwerkzeugen. R2 Mechanics kann mehrere Sprachen innerhalb einer Aufnahme erkennen und strukturieren, auch bei schnellen Wechseln, und sie auf einer Zeitachse halten. Sprach-Zeitachsen und Filter machen solches Material navigierbar. Unterschiedliche Erkennungsfähigkeiten können in einem strukturierten Ergebnis zusammengeführt werden, und es gibt spezialisierte Workflows für mehrsprachiges und sprachspezifisches Material. Eine getrennte Übersetzungsebene für Recherche und Zugang ist optional und bleibt vom Text in der Quellsprache getrennt. Die öffentliche Demonstration Multilingual Institutional Archive zeigt eine lange Aufnahme mit 11 erkannten Sprachen.

## 9. Provenance und Unsicherheit

Provenance beantwortet, woher eine Passage stammt. Unsicherheit beantwortet, wie viel Gewicht sie tragen kann. R2 Mechanics behandelt beides als Teil des Ergebnisses:

- Passagen, die Aufmerksamkeit verdienen, können als prüfwürdige Bereiche markiert werden;
- wo die unabhängigen Perspektiven über eine ganze Aufnahme hinweg nur schwach übereinstimmen, kann ein Gesamthinweis gegeben werden, statt jede Passage zu markieren;
- Ergebnisse können als vorläufig oder prüfungsausstehend gekennzeichnet werden.

Prüfhinweise sind Navigationshilfen für menschliche Prüfer. Sie sind kein Maß für Korrektheit und keine Fehlerrate.

## 10. Optionale LLM-Analyse

Sprachmodelle können eine weitere Ebene ergänzen: Kapitel, Zusammenfassungen, Entitäten und Kontexthinweise. Die Trennung ist bewusst:

```text
Quellmedium
  → Transkriptions- / Sprecher- / Sprach-Evidenz
    → strukturierte Zeitachse
      → optionale LLM-Interpretation
```

LLM-basierte Interpretation kann je nach Zweck des Workflows konfiguriert werden und bleibt von Quelltranskription und Provenance getrennt. Sie ist eine optionale Analyseebene und keine Quellautorität. Sie läuft lokal, wo der Workflow es verlangt, und wird nur auf Anforderung genutzt. Ihre Ausgaben können Fehler enthalten und sind als Interpretation zu lesen, nicht als Evidenz.

## 11. Interaktives Archiv und Mediensynchronisation

Das gelieferte Ergebnis ist ein mediengebundenes Archiv als portables HTML. Je nach Workflow kann es Folgendes enthalten:

- synchronisierter Audio- oder Video-Player mit durchsuchbarem Transkript;
- Lese-, Quellen- und Sprecheransicht;
- Evidence-Maps mit Sprecher-, Sprach- und Quellenspuren, soweit der Workflow sie bereitstellt;
- Filter und direkte Sprungnavigation;
- Kapitel und optionale Zusammenfassungen;
- responsiv und nutzbar in Desktop- und Mobil-Browsern sowie offline-fähig.

Strukturierte Exporte (JSON, SRT, VTT) werden aus demselben zugrunde liegenden Datensatz abgeleitet.

## 12. Schnelle Media-Workflows

Nicht jede Aufgabe braucht die volle Kette. Für schnellen Zugang zu einer Aufnahme bietet R2 Mechanics einen schnelleren Workflow: Media-Player, Transkript und Navigation in einer portablen Datei, ohne die volle redaktionelle Kaskade und mit einer optionalen, fokussierten LLM-Zusammenfassung. Die Evidenz-Zeitachse und die verfügbaren Maps lassen sich weiterhin nutzen. Der evidenzorientierte Workflow bleibt verfügbar, wenn Provenance und Prüfsichtbarkeit zählen.

## 13. Offline-First / datenschutzorientierter Betrieb

Material wird auf von R2 Mechanics betriebener Infrastruktur verarbeitet und standardmäßig nicht an öffentliche Cloud-Transkriptionsdienste gesendet. Lokale und Offline-Verarbeitung wird unterstützt. Betrieb, Handhabung und Aufbewahrung richten sich nach der vereinbarten Umgebung und werden im Projektumfang festgelegt. Verarbeitungseinstellungen werden mit jedem Ergebnis festgehalten, damit Läufe reproduzierbar sind. Archive können als in sich geschlossene, offline-fähige Pakete geliefert werden. Wo Medien bewusst an eine externe institutionelle Quelle gebunden sind, setzt die Wiedergabe den Zugriff auf diese Quelle voraus.

## 14. Öffentliche Anwendungsfelder und Demonstrationen

Typische Nutzer sind Archive und Museen, Universitäten und Forschungseinrichtungen, öffentliche Einrichtungen mit sensiblen Sammlungen sowie Dokumentar- und Investigativmedien.

Die aktuellen öffentlichen Demonstrationen liegen auf [r2-mechanics.com](https://r2-mechanics.com/de/transkriptions-demos/): eine schwierige historische Aufnahme (Nixon Exhibit 21), eine vollständige juristische Anhörung (Kennedy v. Braidwood), ein mehrsprachiges institutionelles Archiv, zwei Kongress-Anhörungen und ein langer Vortrag. Es sind echte Ergebnisse; dieses Repository enthält keine Kopie davon.

## 15. Grenzen und menschliche Prüfung

- Automatische Erkennung macht Fehler, besonders bei degradiertem Audio, überlappender Sprache, seltenen Sprachen und Eigennamen.
- Sprecher- und Sprachzuordnung kann falsch sein, insbesondere bei kurzen Redebeiträgen und schnellen Wechseln.
- Restaurierung kann verändern, was hörbar ist; sie ist optional und kann ausdrücklich kenntlich gemacht werden.
- LLM-basierte Analyse kann falsch oder unvollständig sein.
- Prüfhinweise zeigen, wo man hinschauen sollte; sie garantieren nicht, dass nicht markierte Passagen korrekt sind.
- Kein Transkript ist für sich eine Ground Truth. Projekt-Workflows können eine menschliche Prüfung vor der finalen Auslieferung enthalten.

## 16. Proprietäre Grenze

Dieses Repository dokumentiert Architektur, Methodik, Fähigkeiten und öffentliche Demonstrationen. Die operative Produktionspipeline, ihre Orchestrierungslogik und die Implementierungsdetails bleiben proprietär. Eine Einsicht in das operative System ist im Rahmen von Kooperationen oder NDA-basierten Audits möglich.

---

**R2 MECHANICS sp. z o.o.**, Grabowa 14, 72-343 Karnice, Polen · [office@r2-mechanics.com](mailto:office@r2-mechanics.com) · [r2-mechanics.com](https://r2-mechanics.com) · Member of NVIDIA Inception
