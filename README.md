# Intranets Design System

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)
[![Version](https://img.shields.io/badge/version-2.0.0-informational.svg)](https://github.com/intranetsfr/intranets-design-system)
[![Docs](https://img.shields.io/badge/documentation-ids.intranets.fr-aqua.svg)](https://ids.intranets.fr)

Système de design utilitaire pour intranets — classes atomiques composables, palette Material Design, theming CSS custom properties.

---

## Installation

### CDN

Ajouter dans le `<head>` de chaque page :

```html
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" rel="stylesheet">
<link rel="stylesheet" href="https://ids.intranets.fr/css/intranets-ds.min.css">
```

Ajouter avant `</body>` :

```html
<script src="https://ids.intranets.fr/js/intranets-ds.min.js"></script>
```

### npm

```bash
npm install intranets-design-system
```

#### Angular

Dans `angular.json` :

```json
"styles": [
  "node_modules/intranets-design-system/css/intranets-ds.min.css"
],
"scripts": [
  "node_modules/intranets-design-system/js/intranets-ds.min.js"
]
```

#### Webpack / Vite

```js
import 'intranets-design-system/css/intranets-ds.min.css';
```

---

## Contenu du package

```
intranets-design-system/
├── css/
│   └── intranets-ds.min.css   # Feuille de style compilée (palette, grid, space, texts, theming)
├── js/
│   └── intranets-ds.min.js    # Script compilé (sidenav, interactions)
└── docs/                      # Documentation Fractal générée (HTML statique)
```

---

## Composants disponibles

### Utilitaires

| Classe | Description | Exemple |
|---|---|---|
| `.ids-grid` / `.ids-cell--{n}-col` | Grille flexbox 12 colonnes | `.ids-cell--6-col` |
| `.ids-margin--{n}` | Margin (px) | `.ids-margin--16` |
| `.ids-padding--{n}` | Padding (px) | `.ids-padding--8` |
| `.ids-gap--{n}` | Gap flex/grid (px) | `.ids-gap--16` |
| `.ids-radius--{n}` | Border-radius (px) | `.ids-radius--8` |
| `.ids-fs--{n}` | Font-size (px) | `.ids-fs--14` |
| `.ids-color--{nom}-{teinte}` | Couleur de fond | `.ids-color--indigo-500` |
| `.ids-color-text--{nom}-{teinte}` | Couleur de texte | `.ids-color-text--red-700` |

Les classes margin, padding, gap et font-size acceptent les suffixes **`-phone`**, **`-tablet`**, **`-desktop`** pour le responsive.

### Theming (styles natifs)

Les éléments HTML suivants sont stylisés sans classes supplémentaires via les CSS custom properties :

`button` · `input` · `select` · `textarea` · `fieldset` · `table` · `a` · `h1`–`h6` · `code` · `blockquote`

### Composants JS

- **Sidenav** (`<sidenav>` + `<drawer>`) — panneau de navigation latérale animé CSS

---

## Personnalisation du thème

Surcharger les CSS custom properties dans `:root` pour adapter le thème :

```css
:root {
    /* Couleurs */
    --color-primary:   var(--ids-color--indigo-A700);
    --color-secondary: var(--ids-color--indigo-A100);
    --color-success:   var(--ids-color--green-500);
    --color-warning:   var(--ids-color--yellow-500);
    --color-error:     var(--ids-color--red-500);
    --color-info:      var(--ids-color--blue-500);

    /* Typographie */
    --font-family-base: 'Roboto', system-ui, sans-serif;

    /* Transitions */
    --transition-fast: 150ms ease;
    --transition-base: 300ms ease;
}
```

Toutes les teintes Material Design sont disponibles :

```css
var(--ids-color--{nom}-{teinte})
/* ex : var(--ids-color--teal-500), var(--ids-color--amber-A200) */
```

Noms de couleurs : `red` · `pink` · `purple` · `deep-purple` · `indigo` · `blue` · `light-blue` · `cyan` · `teal` · `green` · `light-green` · `lime` · `yellow` · `amber` · `orange` · `deep-orange` · `brown` · `grey` · `blue-grey`

---

## Breakpoints

| Breakpoint | Largeur min | Colonnes grille | Suffixe |
|---|---|---|---|
| Phone | — | 4 | `-phone` |
| Tablet | 480px | 8 | `-tablet` |
| Desktop | 840px | 12 | `-desktop` |

---

## Exemple rapide

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" rel="stylesheet">
  <link rel="stylesheet" href="https://ids.intranets.fr/css/intranets-ds.min.css">
  <style>
    :root {
      --color-primary:   var(--ids-color--indigo-A700);
      --color-secondary: var(--ids-color--indigo-A100);
    }
  </style>
</head>
<body>

  <div class="ids-grid ids-padding--16">
    <div class="ids-cell ids-cell--8-col ids-cell--12-col-phone">
      <h1 class="ids-fs--32 ids-fs--24-phone">Bienvenue</h1>
      <p class="ids-fs--16 ids-margin-top--8">
        Construit avec l'Intranets Design System.
      </p>
      <button class="ids-radius--8 ids-margin-top--16">
        <span class="material-symbols-outlined">rocket_launch</span>
        Démarrer
      </button>
    </div>
    <div class="ids-cell ids-cell--4-col ids-cell--hide-phone">
      <div class="ids-color--indigo-50 ids-radius--8 ids-padding--24">
        <span class="material-symbols-outlined ids-fs--64 ids-color-text--indigo-500">design_services</span>
      </div>
    </div>
  </div>

  <script src="https://ids.intranets.fr/js/intranets-ds.min.js"></script>
</body>
</html>
```

---

## Documentation

La documentation interactive complète (Fractal) est disponible sur **[ids.intranets.fr](https://ids.intranets.fr)**.

## Sources

Le code source du design system (composants, SCSS, Fractal) est maintenu dans le dépôt principal :
**[github.com/intranetsfr/intranets-design-system-src](https://github.com/intranetsfr/intranets-design-system)**

---

*Intranets Design System v2.0.0 — Licence ISC — ROTY Jeremy*
