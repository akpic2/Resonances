# Conventions de nommage — Festival Résonances

Ce fichier fixe les règles de nommage des classes CSS du projet
et recense tous les blocs avec leurs éléments, modificateurs et états.
Il est mis à jour à chaque étape.

**Sommaire**
1. [Règles générales](#1-règles-générales)
2. [Préfixes par catégorie SMACSS](#2-préfixes-par-catégorie-smacss)
3. [Comment lire les fiches](#3-comment-lire-les-fiches)
4. [Mise en page (layout)](#4-mise-en-page-layout)
5. [Composants (modules)](#5-composants-modules)
6. [Thèmes](#6-thèmes)
7. [Historique](#7-historique)

<br>

---

## 1. Règles générales

### Langue
- Les noms de classes sont en **anglais**, comme les calques de la maquette.
- Tout en **minuscules**, mots séparés par des **tirets** : `ghost-light`, jamais `ghostLight`.

### Syntaxe BEM

| Rôle                   | Syntaxe                     | Exemple                |
| ---------------------- | --------------------------- | ---------------------- |
| Bloc                   | `.block`                    | `.card`                |
| Élément                | `.block__element`           | `.card__title`         |
| Modificateur           | `.block--modifier`          | `.card--headliner`     |
| Modificateur d'élément | `.block__element--modifier` | `.filter__button--all` |

### Principes
- Un composant **ne dépend jamais de son contexte** : toute variation passe par un modificateur.
- Le JavaScript cible uniquement des attributs **`data-*`** (ex. `data-filter`, `data-faq-toggle`), jamais des classes.

<br>

---

## 2. Préfixes par catégorie SMACSS

| Catégorie    | Dossier    | Préfixe        | Exemple       |
| ------------ | ---------- | -------------- | ------------- |
| Mise en page | `layout/`  | `l-`           | `.l-header`   |
| Modules      | `modules/` | *aucun*        | `.button`     |
| États        | `state/`   | `is-` / `has-` | `.is-active`  |
| Thèmes       | `theme/`   | `theme-`       | `.theme-lake` |

<br>

---

## 3. Comment lire les fiches

Chaque bloc (mise en page ou composant) est décrit par **une fiche identique** de six lignes.
Une ligne sans objet contient « — ».

| Ligne             | Contenu                                                    |
| ----------------- | ---------------------------------------------------------- |
| **Rôle**          | À quoi sert le bloc                                        |
| **Pages**         | Pages de la maquette où il apparaît                        |
| **Éléments**      | Parties du bloc (`__element`)                              |
| **Modificateurs** | Variantes du bloc (`--modifier`), regroupées par type      |
| **États**         | Pseudo-classes (`:hover`…) et classes d'état (`.is-…`)     |
| **Thème**         | Si la couleur de scène est donnée par une classe `theme-*` |

<br>

---

## 4. Mise en page (layout)

Grandes zones de la page : elles placent les composants mais n'en sont pas.

| Bloc          | Pages                       |
| ------------- | --------------------------- |
| `l-container` | toutes                      |
| `l-header`    | toutes                      |
| `l-footer`    | toutes                      |
| `l-grid`      | accueil, programme, artiste |
| `l-docs`      | composants                  |

<br>

### `l-container`

|                   |                                                 |
| ----------------- | ----------------------------------------------- |
| **Rôle**          | Centre le contenu sur une largeur max de 1200px |
| **Pages**         | toutes                                          |
| **Éléments**      | —                                               |
| **Modificateurs** | —                                               |
| **États**         | —                                               |
| **Thème**         | —                                               |

### `l-header`

|                   |                                         |
| ----------------- | --------------------------------------- |
| **Rôle**          | En-tête du site                         |
| **Pages**         | toutes                                  |
| **Éléments**      | `__logo`, `__nav`, `__actions`          |
| **Modificateurs** | —                                       |
| **États**         | lien de navigation actif : `.is-active` |
| **Thème**         | —                                       |

### `l-footer`

|                   |                                                               |
| ----------------- | ------------------------------------------------------------- |
| **Rôle**          | Pied de page du site                                          |
| **Pages**         | toutes                                                        |
| **Éléments**      | `__about`, `__links`, `__contact`, `__newsletter`, `__bottom` |
| **Modificateurs** | —                                                             |
| **États**         | —                                                             |
| **Thème**         | —                                                             |

### `l-grid`

|                   |                                                                       |
| ----------------- | --------------------------------------------------------------------- |
| **Rôle**          | Grille de cartes (programme par jour, têtes d'affiche, artistes liés) |
| **Pages**         | accueil, programme, artiste                                           |
| **Éléments**      | —                                                                     |
| **Modificateurs** | —                                                                     |
| **États**         | —                                                                     |
| **Thème**         | —                                                                     |

### `l-docs`

|                   |                                                                                                                         |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Rôle**          | Mise en forme de la page des composants                                                                                 |
| **Pages**         | composants                                                                                                              |
| **Éléments**      | intro : `__intro`, `__breadcrumb`, `__title`, `__lead`                                                                  |
|                   | sommaire : `__toc`, `__toc-link`                                                                                        |
|                   | sections : `__section`, `__section-title`, `__section-text`                                                             |
|                   | lignes : `__row`, `__label`, `__examples`                                                                               |
|                   | jetons : `__swatch`, `__swatch-color`, `__swatch-value`, `__scene`, `__scene-color`, `__type`, `__space`, `__space-box` |
| **Modificateurs** | `__swatch--{couleur}` : un par jeton de couleur (`--primary`, `--error`…)                                               |
|                   | `__scene--lake`, `__scene--forest`, `__scene--kiosk`                                                                    |
|                   | `__type--display`, `--heading`, `--subheading`, `--lead`, `--body`, `--small`                                           |
|                   | `__space--xs`, `--sm`, `--md`, `--lg`, `--xl`                                                                           |
| **États**         | `:hover` sur `__toc-link`                                                                                               |
| **Thème**         | —                                                                                                                       |

<br>

---

## 5. Composants (modules)

14 composants, regroupés par famille.

| Famille     | Bloc           | Pages                                     |
| ----------- | -------------- | ----------------------------------------- |
| Actions     | `button`       | toutes                                    |
| Actions     | `filter`       | programme                                 |
| Étiquettes  | `badge`        | accueil, programme, artiste               |
| Contenus    | `card`         | accueil, programme, artiste               |
| Contenus    | `pass`         | billetterie                               |
| Contenus    | `stat`         | accueil                                   |
| Contenus    | `info-block`   | infos                                     |
| Contenus    | `artist`       | artiste                                   |
| Bandeaux    | `hero`         | accueil                                   |
| Bandeaux    | `page-title`   | programme, billetterie, infos, composants |
| Bandeaux    | `scene-banner` | accueil, artiste                          |
| Formulaires | `field`        | billetterie                               |
| Formulaires | `checkbox`     | billetterie                               |
| Interaction | `faq`          | infos                                     |

<br>

### 5.1 Actions

### `button`

|                   |                                                                     |
| ----------------- | ------------------------------------------------------------------- |
| **Rôle**          | Bouton ou lien d'action                                             |
| **Pages**         | toutes                                                              |
| **Éléments**      | `__icon`, `__count`                                                 |
| **Modificateurs** | couleurs : `--primary`, `--secondary`, `--outline`, `--ghost-light` |
|                   | tailles : `--small`, `--large`                                      |
|                   | forme : `--icon-only`                                               |
| **États**         | `:hover`, `:focus-visible`, `.is-disabled`, `.is-loading`           |
| **Thème**         | oui : bouton principal de la fiche artiste aux couleurs de la scène |

### `filter`

|                   |                                                     |
| ----------------- | --------------------------------------------------- |
| **Rôle**          | Groupe de boutons qui filtre le programme par scène |
| **Pages**         | programme                                           |
| **Éléments**      | `__button`                                          |
| **Modificateurs** | —                                                   |
| **États**         | `.is-active` (un seul filtre sélectionné à la fois) |
| **Thème**         | —                                                   |

<br>

### 5.2 Étiquettes

### `badge`

|                   |                                                 |
| ----------------- | ----------------------------------------------- |
| **Rôle**          | Petite étiquette : scène, statut ou nombre      |
| **Pages**         | accueil, programme, artiste                     |
| **Éléments**      | —                                               |
| **Modificateurs** | scènes : `--lake`, `--forest`, `--kiosk`        |
|                   | statuts : `--new`, `--last-seats`, `--sold-out` |
|                   | tailles : `--small`, `--large`                  |
|                   | styles : `--outline`, `--square`                |
| **États**         | —                                               |
| **Thème**         | — (la scène est donnée par le modificateur)     |

<br>

### 5.3 Contenus

### `card`

|                   |                                                                           |
| ----------------- | ------------------------------------------------------------------------- |
| **Rôle**          | Carte d'artiste                                                           |
| **Pages**         | accueil, programme, artiste                                               |
| **Éléments**      | `__media`, `__body`, `__title`, `__meta`, `__text`, `__link`, `__actions` |
| **Modificateurs** | variantes : `--headliner`, `--compact`, `--horizontal`, `--no-media`      |
| **États**         | `:hover`                                                                  |
| **Thème**         | oui : liseré et badge aux couleurs de la scène                            |

### `pass`

|                   |                                                                         |
| ----------------- | ----------------------------------------------------------------------- |
| **Rôle**          | Formule de pass de la billetterie                                       |
| **Pages**         | billetterie                                                             |
| **Éléments**      | `__ribbon`, `__title`, `__price`, `__features`, `__feature`, `__action` |
| **Modificateurs** | variantes : `--featured`                                                |
| **États**         | —                                                                       |
| **Thème**         | —                                                                       |

### `stat`

|                   |                         |
| ----------------- | ----------------------- |
| **Rôle**          | Chiffre clé du festival |
| **Pages**         | accueil                 |
| **Éléments**      | `__value`, `__label`    |
| **Modificateurs** | —                       |
| **États**         | —                       |
| **Thème**         | —                       |

### `info-block`

|                   |                                                |
| ----------------- | ---------------------------------------------- |
| **Rôle**          | Bloc d'information numéroté (accès, horaires…) |
| **Pages**         | infos                                          |
| **Éléments**      | `__number`, `__title`, `__text`                |
| **Modificateurs** | —                                              |
| **États**         | —                                              |
| **Thème**         | —                                              |

### `artist`

|                   |                                        |
| ----------------- | -------------------------------------- |
| **Rôle**          | Présentation d'un artiste sur sa fiche |
| **Pages**         | artiste                                |
| **Éléments**      | `__media`, `__infos`, `__bio`          |
| **Modificateurs** | —                                      |
| **États**         | —                                      |
| **Thème**         | —                                      |

<br>

### 5.4 Bandeaux

### `hero`

|                   |                                                                       |
| ----------------- | --------------------------------------------------------------------- |
| **Rôle**          | Grande bannière d'accueil avec photo                                  |
| **Pages**         | accueil                                                               |
| **Éléments**      | `__media`, `__content`, `__eyebrow`, `__title`, `__text`, `__actions` |
| **Modificateurs** | —                                                                     |
| **États**         | —                                                                     |
| **Thème**         | —                                                                     |

### `page-title`

|                   |                                                |
| ----------------- | ---------------------------------------------- |
| **Rôle**          | Bandeau de titre en haut des pages intérieures |
| **Pages**         | programme, billetterie, infos, composants      |
| **Éléments**      | `__breadcrumb`, `__title`, `__text`            |
| **Modificateurs** | —                                              |
| **États**         | —                                              |
| **Thème**         | —                                              |

### `scene-banner`

|                   |                                     |
| ----------------- | ----------------------------------- |
| **Rôle**          | Bandeau d'accès à une scène         |
| **Pages**         | accueil, artiste                    |
| **Éléments**      | `__title`, `__genre`, `__link`      |
| **Modificateurs** | —                                   |
| **États**         | —                                   |
| **Thème**         | oui : fond aux couleurs de la scène |

<br>

### 5.5 Formulaires

### `field`

|                   |                                                     |
| ----------------- | --------------------------------------------------- |
| **Rôle**          | Champ de formulaire avec son libellé et son message |
| **Pages**         | billetterie                                         |
| **Éléments**      | `__label`, `__input`, `__select`, `__message`       |
| **Modificateurs** | —                                                   |
| **États**         | `.is-focused`, `.is-error`, `.is-disabled`          |
| **Thème**         | —                                                   |

### `checkbox`

|                   |                                |
| ----------------- | ------------------------------ |
| **Rôle**          | Case à cocher avec son libellé |
| **Pages**         | billetterie                    |
| **Éléments**      | `__input`, `__label`           |
| **Modificateurs** | —                              |
| **États**         | `:checked`                     |
| **Thème**         | —                              |

<br>

### 5.6 Interaction

### `faq`

|                   |                                                     |
| ----------------- | --------------------------------------------------- |
| **Rôle**          | Liste de questions fréquentes en accordéon          |
| **Pages**         | infos                                               |
| **Éléments**      | `__item`, `__question`, `__answer`, `__icon`        |
| **Modificateurs** | —                                                   |
| **États**         | `.is-open` (chaque question s'ouvre indépendamment) |
| **Thème**         | —                                                   |

<br>

---

## 6. Thèmes

| Classe         | Scène                 | Couleur   | Texte posé dessus |
| -------------- | --------------------- | --------- | ----------------- |
| `theme-lake`   | Scène du Lac          | `#1F4E8C` | `#FFFFFF`         |
| `theme-forest` | Scène de la Forêt     | `#2F6B3A` | `#FFFFFF`         |
| `theme-kiosk`  | Le Kiosque            | `#B87A1E` | `#1C1B2E`         |
| `theme-dark`   | Mode sombre (étape 8) | —         | —                 |

<br>

---

## 7. Historique

| Étape | Modification                                                                                             |
| ----- | -------------------------------------------------------------------------------------------------------- |
| 1     | Création des conventions et de l'inventaire (14 composants)                                              |
| 2     | Jetons (`abstracts/_variables.scss`, `base/_tokens.scss`), page des composants (`l-docs`, `l-container`) |
