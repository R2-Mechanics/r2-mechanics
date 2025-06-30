# 📜 System Overview – R2 Mechanics (öffentlich, nicht-operativ)

Dieses Dokument beschreibt die Grundstruktur, Zielsetzung und methodische Umsetzung von **R2 Mechanics** – einem System zur strukturierten, datenschutzkonformen Transkription, Annotation und interaktiven Visualisierung audiobasierter Inhalte.

Ziel ist es, eine nachvollziehbare, aber nicht vollständig rekonstruierbare Beschreibung der Systemarchitektur bereitzustellen, die den First-Mover-Anspruch absichert und potenziellen Partnern Orientierung bietet.

---

## 🔧 Systemstruktur (abstrahiert)

### **1. Eingabeformate**
- Einzelne Audiodateien (z. B. `.mp3`, `.wav`)
- Optional: Begleitinformationen wie Sprecherlisten, Zeitmarkierungen, Metadaten

---

### **2. Verarbeitungsschritte**
1. **Transkription (lokal, offline):**
   - CUDA-beschleunigt
   - WhisperX mit Diarisierung (Sprechertrennung)
   - Sicherer, DSGVO-konformer Betrieb ohne Cloud

2. **Strukturierung:**
   - Einlesen oder Erzeugen einer Kapiteldatei (`.txt`)
   - Titel, Startzeit, Beschreibung pro Kapitel

3. **LLM-gestützte Analyse:**
   - Lokale Generierung von Zusammenfassungen
   - Automatische semantische Notizen mit exakten Zeitmarken
   - Formatierung in konsistente Sekundentimestamps

4. **Visuelle Anreicherung:**
   - Kapitelbasierte Bildgenerierung via Stable Diffusion
   - Lokale Prompt-to-Image-Pipeline
   - Seriosität und Dokumentarcharakter

---

### **3. Ausgabeformate**
- **Interaktives HTML-Transkript**:
  - Audio-Player mit Sprungmarken
  - Automatisch generiertes Inhaltsverzeichnis (TOC)
  - Kapitelüberschriften mit SD-generierten Illustrationen
  - Zusammenfassungen pro Kapitel
  - Sprechersegmente mit Zeitmarken und Rollen
  - Integrierte Notizen / Sidenotes (zeitkorreliert)
  - Vollständiges CSS-Styling im R2-Mechanics-Stil
  - Optionaler Export als statische Website / GitHub Pages

---

## 🧩 Verzeichnisstruktur (typische Anwendung)

```
input_audio/ # Original-Audiodateien
output_html/ # Generierte Endformate
projektname_transkript.html
chapters/ # Kapitelstruktur-Dateien
projektname_chapters.txt
summaries/ # Generierte Kurzfassungen
notes/ # LLM-Annotationsdateien
images/ # Generierte Illustrationen
scripts/ # Eigene Python-Module (nicht öffentlich)

```

---

## ✅ Besonderheiten
- GPU-beschleunigte lokale Transkription (WhisperX)
- Sprechertrennung und Zeitmarken
- Automatisierte LLM-Annotationen mit exakten Zeiten
- SD-Kapitelbilder, offline generiert
- HTML-Export mit Audio, Navigation, Sprunglinks
- 100 % offline und auditierbar – kein Cloud-Upload nötig
- Einfach integrierbar in Archiv- oder Forschungs-Workflows

---

## 🔐 Offenlegung & Schutz

Dieses Dokument dient der **transparenzbasierten Prioritätssicherung**:
- Es enthält keine operativen Skripte oder ausführbaren Befehle
- Die Methodik ist systematisch dokumentiert, aber nicht direkt reproduzierbar
- Das vollständige System wird ausschließlich **lokal und offline betrieben**

Für kooperationsbereite Institutionen stehen Vorführversionen und Testläufe auf Anfrage bereit.

📧 Kontakt: **David Thiry** – office@r2-mechanics.com
