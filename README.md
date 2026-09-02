<p align="center">
    <img src="docs/images/seo-lens-search-console-analysis.png"
         alt="SEO Lens analyzing a Google Search Console export and transforming the data into a visual report"
         width="1200">
</p>

> 🇬🇧 English | [🇫🇷 Français](./README_FR.md)

![License](https://img.shields.io/badge/License-LICENSE.md-lightgreen.svg)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=000000)
[![YouTube](https://img.shields.io/badge/YouTube-@Palks__Studio-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/@Palks_Studio)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-@Palks__Studio-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/palks-studio/)
[![View the resource](https://img.shields.io/badge/Palks%20Studio-SEO%20Lens-0095b1?style=for-the-badge)](https://palks-studio.com/en/seo-lens/)

<p align="center">
  <a href="https://palks-studio.com">
    <img src="https://img.shields.io/badge/Palks%20Studio-Website-0095b1?style=for-the-badge" />
  </a>
</p>

# SEO Lens

SEO Lens is a free Google Search Console export analyzer developed by Palks Studio.

The tool transforms raw data exported from Google Search Console into a visual report, making it easier to identify performance, ranking opportunities, and the main areas worth investigating.

Google provides the data. SEO Lens helps you understand where to look.

> This repository is a technical presentation and documentation repository.  
> It does not contain downloadable source code or production files.

This README documents design principles and system architecture.  
It intentionally avoids operational procedures and sensitive details.

---

## How it works

SEO Lens runs directly in your browser.

1. The user exports their data from Google Search Console as a ZIP file.  
2. The ZIP file is dropped into SEO Lens.  
3. The CSV files contained in the export are read locally.  
4. The data is normalized and analyzed.  
5. A report is generated directly on the page.

No account is required.

No Google API is used.

No artificial intelligence service is used.

---

## Privacy

Processing is performed locally in the browser.

Google Search Console exports are not sent to Palks Studio and are not stored on a server by SEO Lens.

The selected file remains on the user's device during the analysis.

---

## Data analyzed

Depending on the data available in the Google Search Console export, SEO Lens can analyze:

- clicks  
- impressions  
- CTR  
- average position  
- performance trends  
- ranking distribution  
- queries  
- CTR opportunities  
- pages  
- countries  
- devices

The report also provides a concise diagnostic and a list of priorities calculated from the available data.

---

## Report structure

The SEO Lens report is organized into eight sections:

1. Overview  
2. Performance trends  
3. Ranking distribution  
4. Opportunities  
5. Page performance  
6. Markets and devices  
7. Diagnostic  
8. SEO priorities

The analyses are deterministic and based on the data contained in the export.

SEO Lens does not use an artificial SEO score out of 100.

---

## Project structure

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

French version of the interface.

This page is intended to be integrated into the Palks Studio website under the `/fr/` section.

### `seo-lens_en.html`

English version of the interface.

This page is intended to be integrated into the Palks Studio website under the `/en/` section.

### `assets/seo-lens.js`

Contains the main SEO Lens logic:

- ZIP file import  
- CSV file parsing  
- data normalization  
- metric calculations  
- opportunity detection  
- chart generation  
- table generation  
- diagnostic  
- prioritization  
- dynamic report rendering  
- FR / EN dynamic text management

The language used by the JavaScript is determined from the HTML page's `lang` attribute.

### `assets/css/seo-lens.css`

Contains all styles specific to SEO Lens:

- import interface  
- report  
- metrics  
- charts  
- tables  
- diagnostic  
- priorities  
- responsive layout  
- light and dark modes

### `assets/vendor/jszip.min.js`

Library used to read ZIP archives directly in the browser.

---

## Architecture

SEO Lens follows a simple processing pipeline:

```
IMPORT
↓
PARSER
↓
NORMALIZATION
↓
ANALYSIS
↓
INSIGHTS / PRIORITIZATION
↓
RENDERING
```

All processing is performed client-side in JavaScript.

No backend is required for the analyzer to work.

---

## Google Search Console exports

SEO Lens supports the main files included in Google Search Console exports, including their French and English variants.

Examples:

- `Graphique.csv` / `Chart.csv`  
- `Requêtes.csv` / `Queries.csv`  
- `Pages.csv`  
- `Pays.csv` / `Countries.csv`  
- `Appareils.csv` / `Devices.csv`  
- `Filtres.csv` / `Filters.csv`

The tool uses aliases to recognize file names and certain columns depending on the language of the export.

SEO Lens works as a set of static HTML, CSS, and JavaScript files.

No PHP or server-side processing is required to analyze exports.

---

## Limitations

SEO Lens analyzes only the data contained in the Google Search Console export provided by the user.

It does not perform:

- website crawling  
- a complete technical SEO audit  
- backlink analysis  
- analysis of page HTML content  
- website modifications  
- a direct connection to Google Search Console

The results should therefore be considered a structured interpretation of Search Console data, not a complete SEO audit.

---

## Technologies

- HTML  
- CSS  
- JavaScript  
- JSZip  
- Google Search Console CSV exports

---

## Project

SEO Lens is developed by **Palks Studio**.

Free tool, no account required, with no remote processing of Google Search Console exports.

---

© Palks Studio — see LICENSE.md  
- https://palks-studio.com