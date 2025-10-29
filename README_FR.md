# R2 Mechanics – Infrastructure de Transcription et d’Analyse IA Hors Ligne

Bienvenue dans le dépôt officiel de **R2 Mechanics** — un système modulaire de transcription et d’analyse entièrement hors ligne, conçu pour les archives, les institutions de recherche et les projets de patrimoine culturel.  
La plateforme transforme des enregistrements audio et vidéo complexes en rapports HTML structurés, annotés par locuteur et navigables — **sans aucune dépendance au cloud**.

> Ce dépôt sert de référence publique et datée sur la méthodologie et l’architecture du système.  
> Il **ne contient pas** de code source opérationnel. L’ensemble du pipeline fonctionne localement et peut être consulté dans le cadre de partenariats ou d’audits sous accord de confidentialité (NDA).

---

## 🌐 Site Web Public

👉 [Page d’accueil officielle (GitHub Pages)](https://r2-mechanics.github.io/r2-mechanics/)

---

## 🎧 Démonstrations (Aperçu Chronologique)

Découvrez des rapports HTML interactifs avec audio intégré, navigation par chapitres et segmentation automatique des locuteurs — illustrant l’évolution du pipeline R2 Mechanics depuis les premiers prototypes jusqu’aux applications multi-pipelines avancées.

---

### 🕰️ Avril / Mai 2025 – Premiers Proof-of-Concepts
- ▶️ **Avril 2025** – [Discours de JFK sur la Lune](https://r2-mechanics.github.io/r2-mechanics/JFK-Moonspeech.html) — discours structuré avec chapitres et horodatages  
- ▶️ **Avril / Mai 2025** – [Conférence de presse Apollo 11](https://r2-mechanics.github.io/r2-mechanics/demo-apollo11/apollo11.html) — session historique multi-intervenants (Q&R)  

---

### 🗃️ Juillet 2025 – Projet d’Archives
- ▶️ **Juillet 2025 – Early Pipeline :** [Oral-History.Digital – Projet Pagenstecher](https://r2-mechanics.github.io/r2-mechanics/vortraege-de/pagenstecher-project.html) — transcription HTML adaptée aux besoins archivistiques  

---

### 🧾 Septembre / Octobre 2025 – Démos Institutionnelles & Auditions
- ▶️ **Septembre 2025** – [Audition du Congrès sur les UAP (2024)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing/uap-2024.html) — session complète de deux heures  
- ▶️ **Septembre / Octobre 2025** – [UAP Hearing (Démo PL / EN)](https://r2-mechanics.github.io/r2-mechanics/uap-hearing-pl/start-pl.html) — exemple bilingue  

---

### ⚙️ Octobre 2025 – Pipelines Avancés & Formats de Recherche
- ▶️ **Octobre 2025 – Nouvelle Pipeline :** [Kennedy v. Braidwood Management — Transcription d’Audience (Démo)](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html) — démonstration à double pipeline présentant une interface interactive (Pipeline A) et une transcription orientée recherche (Pipeline B). [🔗 Voir en plein écran](https://project.r2-mechanics.com/demos/Kennedy-Braidwood/Kennedy.v.Braidwood.Management.html)  
- ▶️ **Octobre 2025 – Nouvelle Pipeline :** [Alan Watts — The Natural Environment (Édition Interactive)](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html) — conférence philosophique avec diarisation précise, alignement audio-texte synchronisé, chapitres structurés et documentation hors ligne. [🔗 Voir en plein écran](https://project.r2-mechanics.com/demos/Alan_Watts/The_Natural_Environment.html)  
- ▶️ **Octobre 2025 – Nouvelle Pipeline :** [UAP Hearing 2025 (Démo EN)](https://project.r2-mechanics.com/demos/uap-hearing-Sep-2025/uap-hearing-Sep-2025.html) — transcription structurée avec annotations et défilement automatique  

---

Ces démonstrations illustrent la **production hors ligne structurée**, avec segmentation sémantique, attribution des locuteurs et enrichissements visuels optionnels.

---


## 🎯 Objectif

**R2 Mechanics** permet le traitement **structuré, transparent et conforme au RGPD** d’enregistrements audio et vidéo sensibles — par exemple : entretiens, témoignages, archives historiques.

### Caractéristiques principales

- 100 % **hors ligne** — infrastructure isolée, sans télémétrie  
- **Transcription accélérée GPU** avec WhisperX (large-v3)  
- **Diarisation des locuteurs** via pyannote.audio (4.x)  
- **Chapitrage sémantique et résumés** à l’aide de LLM locaux (LM Studio / Ollama)  
- **Sorties structurées HTML / DOCX** prêtes à l’archivage ou à la publication  
- **Infrastructure énergétique autonome** avec redondance UPS  

---

## 🧩 Architecture du Système (Aperçu)

R2 Mechanics fonctionne dans un environnement isolé `r2_asr4`, combinant :

| Couche | Composant | Fonction |
|--------|------------|-----------|
| **ASR + Diarisation** | WhisperX (large-v3) + pyannote.audio (4.x) | Transcription mot à mot et segmentation des locuteurs |
| **Analyse sémantique** | LLM local (LM Studio / Ollama) | Génération de thèmes, entités et résumés |
| **Sortie** | Markdown / DOCX / HTML | Rapports structurés avec navigation par chapitres |
| **Audit & Résilience** | Archives WARC + journaux | Exécutions déterministes et reproductibles |
| **Énergie** | Sources renouvelables / UPS / NVMe | Fonctionnement continu 24 h/24 – cycle de 10 ans |

---

## 🛡 Gouvernance & Conformité

- **Contrôle d’accès & Gouvernance** – isolation par projet, RBAC (owner / contributor / viewer), 2FA/MFA optionnelle ; aucun sous-traitant.  
- **Cycle de vie des données & rétention** – ingest → traitement → révision → livraison → suppression ; rétention configurable 30 / 60 / 90 jours.  
- **Reproductibilité & Version-Pinning** – chaque exécution archive les versions des modèles (WhisperX large-v3, pyannote.audio 4.x), le stack CUDA/Torch et les hashes de configuration.  
- **Sécurité** – infrastructure totalement isolée, ingest chiffré, stockage sécurisé, sauvegardes immutables hors ligne.  
- **Conformité** – traitement exclusif au sein de l’UE (Pologne) ; AVV/DPA et TOM disponibles sur demande.  
- **Gestion des versions** – mises à jour trimestrielles ; versions gelées jusqu’à validation.  
- **Confidentialité & Transparence** – accès possible sous NDA ; toutes les étapes auditables ; code source non public pour raisons de sécurité et d’intégrité.

---

## ⚙️ Composants (Abstraits)

- **WhisperX (Offline CUDA)** – ASR + alignement  
- **pyannote.audio (4.x)** – diarisation des locuteurs  
- **Analyse LLM (LM Studio / Ollama)** – thèmes, entités, résumés  
- **Générateur HTML** – rapports structurés avec lecture audio  
- **Modules optionnels** – génération d’images (SDXL), contextes multilingues  

---

## 📄 Documentation

- [Aperçu du Système (DE)](docs/system_overview.md)  
- [System Overview (EN)](docs/system_overview_en.md)  
- [Livre Blanc (DE, PDF)](docs/whitepaper_de.pdf)  
- [Whitepaper (EN, PDF)](docs/whitepaper_en.pdf)  
- [Fiche de Projet (DE)](docs/projektsteckbrief.md)

---

## 📬 Contact

**David Thiry**  
📧 office@r2-mechanics.com  
🌐 [https://r2-mechanics.com](https://r2-mechanics.com)  
🔗 [GitHub : R2-Mechanics / r2-mechanics](https://github.com/R2-Mechanics/r2-mechanics)

---

## 🔒 Statut

🧱 Ce dépôt documente l’**architecture, la méthodologie et le cadre de conformité** de R2 Mechanics.  
🛠 Le pipeline opérationnel est entièrement fonctionnel et vérifiable sous NDA, mais non distribué publiquement.

---

📄 [Deutsch → README_DE.md](README_DE.md)  |  [English → README.md](README.md)
