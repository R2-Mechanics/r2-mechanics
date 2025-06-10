# R2 Mechanics – Strukturierte Offline-Transkription für Forschung und Archive

Willkommen im offiziellen Dokumentations-Repository für **R2 Mechanics** – ein modulares, offline arbeitendes Transkriptionssystem mit visuell strukturierter HTML-Ausgabe.

> Dieses Repository dient als öffentlich datierter Nachweis und dokumentarische Referenz für die zugrunde liegende Methodik. Es enthält **keinen operativen Quellcode**. Das vollständige System läuft lokal und ist im Rahmen von Kooperationen auf Anfrage einsehbar.

---

## 🔗 Projekt-Website (GitHub Pages)

👉 [Zur öffentlichen Landingpage](https://r2-mechanics.github.io/r2-mechanics/)

---

## 🚀 Live-Demos

Erleben Sie exemplarische HTML-Ausgaben mit interaktiver Navigation, eingebettetem Audio, Kapitelmarken und Sprechererkennung:

▶️ [JFK Moon Speech Demo](https://r2-mechanics.github.io/r2-mechanics/JFK-Moonspeech.html)  
▶️ [Apollo 11 Press Conference Demo](https://r2-mechanics.github.io/r2-mechanics/demo-apollo11/apollo11.html)

These demos illustrate the structured offline output of R2 Mechanics, featuring embedded audio, speaker-labeled segments and visual segmentation.

---


## Zielsetzung

R2 Mechanics wurde entwickelt, um sensible Audiomaterialien (z. B. Interviews, Zeitzeugenberichte) strukturiert, transparent und datenschutzkonform aufzubereiten. Das System bietet:

- Lokale Transkription (WhisperX-basiert)
- Sprechertrennung und Zuordnung
- Kapitelstruktur mit Zeitmarken
- Visuelle HTML-Ausgabe mit Audioeinbettung
- Optional: automatische Szenenillustration

---

## Motivation

Forschungseinrichtungen, Archive und kulturelle Institutionen benötigen Werkzeuge zur strukturierten Verarbeitung von Audio – ohne Cloudabhängigkeit oder Lizenzrisiken. R2 Mechanics schließt diese Lücke.

---

## Komponentenüberblick (abstrahiert)

- WhisperX (lokal, CUDA-beschleunigt)
- Kapiteldaten (.txt mit Zeitmarken, Titeln, optionalen Notizen)
- HTML-Generator (visuell angepasst)
- Optional: LLM-basierte Zusammenfassungen (offline)
- Optional: Bildgenerator (Stable Diffusion auf separatem System)

---

## 📄 Dokumentation

- [System Overview (DE)](docs/system_overview.md)
- [System Overview (EN)](docs/system_overview_en.md)
- [Whitepaper (PDF, DE)](docs/whitepaper_de.pdf)
- [Whitepaper (PDF, EN)](docs/whitepaper_en.pdf)
- [Projektsteckbrief (DE)](docs/projektsteckbrief.md)
---

## 📬 Kontakt

Für Anfragen, Kooperationen oder Pilotprojekte:

**David Thiry**  
✉️ office@r2-mechanics.com  
🔗 [GitHub: R2-Mechanics/r2-mechanics](https://github.com/R2-Mechanics/r2-mechanics)

---

## Status

🛠 Dieses Repository dokumentiert die Architektur und Zielsetzung von R2 Mechanics.  

🔒 Der Quellcode und die operative Pipeline sind nicht öffentlich, aber verifiziert vorhanden.

---

📄 [English version available → README_EN.md](README_EN.md)
