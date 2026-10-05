# R2 Mechanics – Transcription d’archives offline-first & Evidence Mapping

Dépôt public de documentation de R2 Mechanics.

R2 Mechanics transforme des enregistrements audio et vidéo difficiles, longs et multilingues en documents structurés et reliés à leur source : navigables, vérifiables et portables, avec un traitement local de type offline-first.

> Ce dépôt documente l’architecture, la méthodologie, les capacités et les démonstrations publiques.
> Le pipeline de production opérationnel, sa logique d’orchestration et ses détails d’implémentation restent propriétaires et ne font **pas** partie de ce dépôt.

R2 Mechanics est exploité par R2 MECHANICS sp. z o.o., société polonaise à responsabilité limitée (sp. z o.o.), Pologne.

**Site web :** [r2-mechanics.com](https://r2-mechanics.com) · **Démos en ligne :** [r2-mechanics.com/en/demos](https://r2-mechanics.com/en/demos/)

---

## Ce que fait R2 Mechanics

Les archives, institutions de recherche et projets documentaires détiennent souvent des enregistrements que la transcription standard ne sait pas traiter : audio dégradé ou historique, nombreux locuteurs, changements de langue rapides, sessions très longues.

R2 Mechanics ne traite pas un tel enregistrement comme un bloc de texte unique, mais comme un document structuré et navigable, qui reste relié au média d’origine :

- transcriptions structurées avec attribution des locuteurs et horodatages citables
- structure des langues et des locuteurs le long de la ligne temporelle d’origine
- zones de vérification visibles là où les preuves sont faibles
- lecture synchronisée, recherche et navigation par chapitres
- livrables portables qui fonctionnent sans service cloud

---

## Architecture

### Préservation de la source & offline-first

- Le traitement peut se dérouler entièrement en local, sans dépendance au cloud.
- L’enregistrement original reste la référence. Il n’est jamais écrasé ; une copie de travail contrôlée est créée et documentée.
- Les résultats restent traçables jusqu’au matériau source.

### Transcription forensique multi-moteurs

- Plusieurs perspectives de reconnaissance indépendantes peuvent être utilisées ensemble sur le même matériau.
- Les résultats divergents sont comparés et traités de façon documentée, au lieu d’être fusionnés silencieusement.
- Les zones incertaines ou problématiques ne disparaissent pas dans le texte final.
- La provenance du texte retenu peut être conservée.

Des technologies ouvertes établies comme WhisperX et pyannote.audio font toujours partie de la pile. L’orchestration concrète n’est pas publiée.

### Evidence Mapping & Timeline Intelligence

C’est une capacité centrale de R2. L’audio et la vidéo sont traités comme une ligne temporelle navigable qui porte :

- les zones de locuteurs
- les zones de langues
- la provenance du texte et des moteurs
- les passages qui méritent une vérification
- la navigation directe du transcript vers le média d’origine
- des cartes visuelles de sources et de preuves pour les enregistrements longs, multilingues ou difficiles à transcrire

> R2 Mechanics ne réduit pas un enregistrement à un seul bloc de texte. Les informations sur les locuteurs, les langues, les sources de transcription et la vérification peuvent être conservées et visualisées le long de la ligne temporelle du média d’origine.

### Traitement multilingue

- détection et structuration de plusieurs langues au sein d’un même enregistrement, y compris lors de changements de langue rapides
- lignes temporelles des langues et filtres de langue
- workflows spécialisés pour le matériau multilingue ou propre à une langue
- les résultats de différentes capacités de reconnaissance sont réunis dans un résultat structuré commun
- couche de traduction dérivée et optionnelle pour la recherche, l’accès et la navigation multilingue ; la transcription en langue source reste conservée comme référence, et l’archive peut basculer entre la vue en langue source et la vue traduite

### Vérification assistée par matériel de référence

- Le matériel de référence existant (transcriptions, tapuscrits, PDF, scans, documentation d’archives, listes de locuteurs et autres métadonnées) peut être intégré lorsqu’un projet en dispose.
- Les couches de texte existantes peuvent être extraites directement ; l’OCR n’est utilisé que lorsque le matériau l’exige, dans un workflow de soutien avant la comparaison avec la transcription issue du média.
- Les documents de référence originaux restent inchangés ; le texte extrait ou obtenu par OCR est traité comme une représentation de travail dérivée.
- Le texte est aligné et comparé à la transcription issue du média afin de faciliter la vérification et l’identification des divergences.
- Le matériel de référence soutient la vérification. Il ne corrige ni ne remplace rien automatiquement, et la source média reste la référence principale.
- Cette branche est optionnelle et n’est pas utilisée dans tous les projets.

### Archive interactive & livraison

- lecteur audio/vidéo synchronisé avec transcript interrogeable
- lignes temporelles des locuteurs, des langues et des sources, avec filtres et navigation par saut direct
- archives HTML offline portables, responsive et utilisables dans les navigateurs de bureau et mobiles
- formats structurés tels que JSON, SRT et VTT
- analyse éditoriale ou basée sur LLM en option (chapitres, résumés, entités, notes de contexte), toujours signalée comme telle

### Workflows média rapides

- traitement rapide du média et du transcript sans la cascade éditoriale complète
- lecteur, transcript et navigation dans un seul fichier portable
- résumé LLM ciblé en option

---

## Showcases publics / Démos actuelles

Les démos actuelles sont hébergées exclusivement sur [r2-mechanics.com](https://r2-mechanics.com). Ce dépôt n’en contient aucune copie. Les pages de démo sont en anglais.

**À la une**

- **[Nixon Exhibit 21 – Audio historique difficile](https://r2-mechanics.com/showcases/nixon-exhibit-21/)**
  Un enregistrement historique difficile devenu un document structuré et vérifiable, avec accès synchronisé à la source, structure des locuteurs, zones de vérification diagnostiques et transcript aligné sur la source.
- **[Kennedy v. Braidwood – Enregistrement juridique long](https://r2-mechanics.com/showcases/kennedy-braidwood/)**
  Un enregistrement juridique complet avec audio synchronisé, navigation par chapitres, sections par locuteur et accès direct à la source.
- **[Multilingual Institutional Archive](https://r2-mechanics.com/showcases/multilingual-institutional-archive/)**
  Un long enregistrement institutionnel reconstruit sur 11 langues détectées et plusieurs locuteurs, avec extraits reliés à la source, navigation par langue et par locuteur et couche de traduction allemande séparée.

**Autres exemples**

- **[UAP Congressional Hearing (2024)](https://r2-mechanics.com/en/uap-congressional-hearing-2024)**
  Une audition publique complète avec environ 16 intervenants : segmentation par locuteur, navigation par chapitres, lecture au niveau du segment.
- **[UAP Congressional Hearing (Sep 2025)](https://r2-mechanics.com/en/uap-hearing-sep-2025-v1)**
  Une longue audition publique sous forme de transcript structuré et navigable, avec navigation par horodatage.
- **[Alan Watts – The Natural Environment](https://r2-mechanics.com/en/alan-watts-the-natural-environment/)**
  Une longue conférence présentée comme une expérience de lecture et d’écoute synchronisées.

Les anciennes démos de 2025 hébergées dans ce dépôt ont été retirées ; leurs anciennes URL redirigent vers l’aperçu actuel des démos.

---

## Cas d’usage

- Archives & musées
- Universités & institutions de recherche
- Institutions publiques & collections sensibles
- Médias documentaires & d’investigation

---

## Confidentialité / Traitement local

Le traitement local et offline est pris en charge. Le déploiement, la gestion et la conservation dépendent de l’environnement convenu et sont définis dans le périmètre du projet.

Exécutions reproductibles : les paramètres de traitement sont enregistrés avec chaque résultat.


---

## État actuel (2026)

R2 Mechanics a été activement développé tout au long de 2026. L’architecture actuelle va nettement au-delà des démos de 2025 présentes dans ce dépôt :

- transcription multi-moteurs avec provenance documentée du texte
- cartes de preuves et de vérification le long de la ligne temporelle du média
- traitement multilingue avec structure tenant compte des langues
- couche de traduction dérivée optionnelle et vérification assistée par matériel de référence (extraction, alignement, identification des divergences)
- workflows de restauration en option pour les enregistrements historiques, avec conservation de l’original
- archives offline portables, responsive et utilisables dans les navigateurs de bureau et mobiles
- workflows média rapides en complément du traitement éditorial complet

---

## Limite propriétaire

Le dépôt public documente l’architecture, la méthodologie, les capacités et les démonstrations publiques. Le pipeline de production opérationnel, la logique d’orchestration et les détails d’implémentation restent propriétaires. Un examen est possible dans le cadre de coopérations ou d’audits sous NDA.

---

## Documentation

- [System Overview 2026 (EN)](docs/system_overview_en.md) · [System Overview 2026 (DE)](docs/system_overview.md)
- [Whitepaper 2026 (EN)](docs/whitepaper_public_en.md) · [Whitepaper 2026 (DE)](docs/whitepaper_public.md)
- [Schéma d’architecture 2026](docs/architecture_2026.md)

Ces documents sont disponibles en anglais et en allemand.

**Historique (2025)** – ne décrivent **pas** l’état actuel de la production : [Whitepaper 2025 (EN, PDF)](docs/whitepaper_en.pdf) · [Whitepaper 2025 (DE, PDF)](docs/whitepaper_de.pdf) · [Fiche projet (DE)](docs/projektsteckbrief.md)
---

## Contact

**R2 MECHANICS sp. z o.o.**
Grabowa 14, 72-343 Karnice, Pologne
office@r2-mechanics.com
[r2-mechanics.com](https://r2-mechanics.com)

Inscrite au registre des entrepreneurs du Registre judiciaire national (KRS), tribunal d’enregistrement : tribunal de district de Szczecin-Centrum, XIIIe division commerciale. KRS 0001230326 · NIP 8571944744 · REGON 544304629

Member of NVIDIA Inception

---

[English → README.md](README.md) | [Deutsch → README_DE.md](README_DE.md)
