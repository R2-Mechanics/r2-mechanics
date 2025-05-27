# System Overview – R2 Mechanics (öffentlich, nicht-operativ)

Dieses Dokument beschreibt die Grundstruktur, Zielsetzung und methodische Umsetzung von **R2 Mechanics** – einem System zur strukturierten, datenschutzkonformen Transkription und Visualisierung audiobasierter Inhalte.

Ziel ist es, eine nachvollziehbare, aber nicht rekonstruierbare Beschreibung der Systemarchitektur bereitzustellen, die den First-Mover-Anspruch absichert und potenziellen Partnern Orientierung bietet.

---

## 🔧 Systemstruktur (abstrahiert)

### **1. Eingabeformate:**
- Einzelne Audiodateien (z. B. `.mp3`, `.wav`)
- Optional: Begleitinformationen wie Sprecherlisten, Zeitmarkierungen, Metadaten

### **2. Verarbeitungsschritte:**
1. **Transkription (lokal):**
   - CUDA-beschleunigt
   - Diarisierung (Sprechertrennung)
2. **Strukturierung:**
   - Einlesen oder Generieren einer Kapiteldatei (`.txt`)
   - Einbindung von Titel, Startzeit, Beschreibung
3. **Optionale LLM-Verarbeitung:**
   - Lokale Generierung von Zusammenfassungen oder semantischen Notizen
4. **(Optional) Visualisierung mit Bildgenerator:**
   - Kapitelbasierte Szenenillustration via Prompt-to-Image (offline)

### **3. Ausgabeformate:**
- Interaktives HTML-Transkript:
  - Audio-Player
  - klickbare Kapitelabschnitte
  - Zeitmarken
  - Sprecherzuordnung (optional namentlich)
  - CSS-Styling im R2-Mechanics-Stil

---

## 🧩 Verzeichnisstruktur (in Anwendung)

```
input_audio/                  # Originaldateien
output_html/                  # Generierte Endformate
  projektname_transkript.html
chapters/                     # Kapitelstruktur-Dateien
  projektname_chapters.txt
summaries/                    # Optional generierte Kurzfassungen
images/                       # Optional generierte Illustrationen
scripts/                      # Ausgelagerte Python-Module (nicht veröffentlicht)
```

---

## 🔐 Offenlegung & Schutz

Dieses Dokument dient der **transparenzbasierten Prioritätssicherung**:
- Es enthält keine operativen Befehle oder Scripts
- Die Methodik ist systematisch dokumentiert, aber nicht reproduzierbar
- Das vollständige System wird ausschließlich **lokal und offline betrieben**

Für kooperationsbereite Institutionen stehen Vorführversionen und Testläufe auf Anfrage bereit.

Kontakt: **David Thiry** – office@r2-mechanics.com
