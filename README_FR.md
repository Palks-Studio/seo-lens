<p align="center">
    <img src="docs/images/seo-lens-search-console-analysis.png"
         alt="SEO Lens analysant un export Google Search Console et transformant les données en rapport visuel"
         width="1200">
</p>

> 🇫🇷 Français | [🇬🇧 English](./README.md)

![License](https://img.shields.io/badge/License-LICENSE.md-lightgreen.svg)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=000000)
[![YouTube](https://img.shields.io/badge/YouTube-@Palks__Studio-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/@Palks_Studio)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-@Palks__Studio-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/palks-studio/)
[![Voir la ressource](https://img.shields.io/badge/Palks%20Studio-SEO%20Lens-0095b1?style=for-the-badge)](https://palks-studio.com/fr/seo-lens/)

<p align="center">
  <a href="https://palks-studio.com">
    <img src="https://img.shields.io/badge/Palks%20Studio-Website-0095b1?style=for-the-badge" />
  </a>
</p>

# SEO Lens

SEO Lens est un analyseur gratuit d'exports Google Search Console développé par Palks Studio.

L'outil transforme les données brutes exportées depuis Google Search Console en un rapport visuel permettant d'identifier plus rapidement les performances, les opportunités de positionnement et les principaux points à examiner.

Google fournit les données. SEO Lens aide à comprendre où regarder.

> Ce dépôt constitue une présentation technique et une documentation du projet.  
> Il ne contient pas de code source téléchargeable ni de fichiers de production.

Ce README documente les principes de conception et l’architecture du système.  
Il évite volontairement toute procédure opérationnelle ou détail sensible.

---

## Fonctionnement

SEO Lens fonctionne directement dans le navigateur.

1. L'utilisateur exporte ses données depuis Google Search Console au format ZIP.  
2. Le fichier ZIP est déposé dans SEO Lens.  
3. Les fichiers CSV contenus dans l'export sont lus localement.  
4. Les données sont normalisées et analysées.  
5. Un rapport est généré directement dans la page.

Aucun compte n'est nécessaire.

Aucune API Google n'est utilisée.

Aucun service d'intelligence artificielle n'est utilisé.

---

## Confidentialité

Le traitement est effectué localement dans le navigateur.

Les exports Google Search Console ne sont pas envoyés à Palks Studio et ne sont pas stockés sur un serveur par SEO Lens.

Le fichier sélectionné reste sur l'appareil de l'utilisateur pendant l'analyse.

---

## Données analysées

Selon les données disponibles dans l'export Google Search Console, SEO Lens peut analyser notamment :

- les clics  
- les impressions  
- le CTR  
- la position moyenne  
- l'évolution des performances  
- la répartition des positions  
- les requêtes  
- les opportunités de CTR  
- les pages  
- les pays  
- les appareils

Le rapport fournit également un diagnostic synthétique et une liste de priorités calculées à partir des données disponibles.

---

## Structure du rapport

Le rapport SEO Lens est organisé en huit sections :

1. Vue d'ensemble  
2. Évolution des performances  
3. Répartition des positions  
4. Opportunités  
5. Performances des pages  
6. Marchés et appareils  
7. Diagnostic  
8. Priorités SEO

Les analyses sont déterministes et reposent sur les données présentes dans l'export.

SEO Lens n'utilise pas de score SEO artificiel sur 100.

---

## Structure du projet

```text
seo-lens/
├── assets/
│   ├── css/
│   │   └── seo-lens.css
│   ├── vendor/
│   │   └── jszip.min.js
│   └── seo-lens.js
├── seo-lens_en.html
└── seo-lens_fr.html
```

### `seo-lens_fr.html`

Version française de l'interface.

Cette page est destinée à être intégrée au site Palks Studio dans la section `/fr/`.

### `seo-lens_en.html`

Version anglaise de l'interface.

Cette page est destinée à être intégrée au site Palks Studio dans la section `/en/`.

### `assets/seo-lens.js`

Contient la logique principale de SEO Lens :

- import du fichier ZIP  
- lecture des fichiers CSV  
- normalisation des données  
- calcul des indicateurs  
- détection des opportunités  
- génération des graphiques  
- génération des tableaux  
- diagnostic  
- priorisation  
- rendu dynamique du rapport  
- gestion des textes dynamiques FR / EN

La langue utilisée par le JavaScript est déterminée à partir de l'attribut `lang` de la page HTML.

### `assets/css/seo-lens.css`

Contient l'ensemble des styles propres à SEO Lens :

- interface d'import  
- rapport  
- indicateurs  
- graphiques  
- tableaux  
- diagnostic  
- priorités  
- responsive  
- modes clair et sombre

### `assets/vendor/jszip.min.js`

Bibliothèque utilisée pour lire les archives ZIP directement dans le navigateur.

---

## Architecture

SEO Lens suit une chaîne de traitement simple :

```
IMPORT
↓
PARSER
↓
NORMALISATION
↓
ANALYSE
↓
INSIGHTS / PRIORISATION
↓
RENDU
```

L'ensemble du traitement est réalisé côté client en JavaScript.

Aucun backend n'est nécessaire au fonctionnement de l'analyseur.

---

## Exports Google Search Console

SEO Lens prend en charge les principaux fichiers présents dans les exports Google Search Console, notamment leurs variantes françaises et anglaises.

Exemples :

- `Graphique.csv` / `Chart.csv`  
- `Requêtes.csv` / `Queries.csv`  
- `Pages.csv`  
- `Pays.csv` / `Countries.csv`  
- `Appareils.csv` / `Devices.csv`  
- `Filtres.csv` / `Filters.csv`

L'outil utilise des alias afin de reconnaître les noms de fichiers et certaines colonnes selon la langue de l'export.

SEO Lens fonctionne comme un ensemble de fichiers statiques HTML, CSS et JavaScript.

Aucun traitement PHP ou serveur n'est requis pour analyser les exports.

---

## Limites

SEO Lens analyse uniquement les données présentes dans l'export Google Search Console fourni par l'utilisateur.

Il ne réalise pas :

- de crawl du site  
- d'audit technique complet  
- d'analyse des backlinks  
- d'analyse du contenu HTML des pages  
- de modification du site  
- de connexion directe à Google Search Console

Les résultats doivent donc être considérés comme une lecture structurée des données Search Console, et non comme un audit SEO complet.

---

## Technologies

- HTML  
- CSS  
- JavaScript  
- JSZip  
- exports CSV Google Search Console

---

## Projet

SEO Lens est développé par **Palks Studio**.

Outil gratuit, sans compte et sans traitement distant des exports Google Search Console.

---

© Palks Studio — voir LICENSE.md  
- https://palks-studio.com