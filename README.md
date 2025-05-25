# R2 Mechanics – Strukturierte Offline-Transkription für Forschung und Archive

Willkommen im offiziellen Dokumentations-Repository für **R2 Mechanics** – ein modulares, offline arbeitendes Transkriptionssystem mit visuell strukturierter HTML-Ausgabe.

> Dieses Repository dient als öffentlich datierter Nachweis und dokumentarische Referenz für die zugrunde liegende Methodik. Es enthält **keinen operativen Quellcode**. Das vollständige System läuft lokal und ist im Rahmen von Kooperationen auf Anfrage einsehbar.

## Zielsetzung
R2 Mechanics wurde entwickelt, um sensible Audiomaterialien (z. B. Interviews, Zeitzeugenberichte) strukturiert, transparent und datenschutzkonform aufzubereiten. Das System bietet:

- Lokale Transkription (WhisperX-basiert)
- Sprechertrennung und Zuordnung
- Kapitelstruktur mit Zeitmarken
- Visuelle HTML-Ausgabe mit Audioeinbettung
- Optional: automatische Szenenillustration

## Motivation
Forschungseinrichtungen, Archive und kulturelle Institutionen benötigen Werkzeuge zur strukturierten Verarbeitung von Audio – ohne Cloudabhängigkeit oder Lizenzrisiken. R2 Mechanics schließt diese Lücke.

## Komponentenüberblick (abstrahiert)
- WhisperX (lokal, CUDA-beschleunigt)
- Kapiteldaten (.txt mit Zeitmarken, Titeln, optionalen Notizen)
- HTML-Generator (visuell angepasst)
- Optional: LLM-basierte Zusammenfassungen (offline)
- Optional: Bildgenerator (Stable Diffusion auf separatem System)

## Repositorium-Gliederung
