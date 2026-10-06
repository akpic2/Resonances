# Conventions de nommage — Festival Résonances

Mis à jour à chaque étape.

## Règles

- Noms de classes en **anglais**, en minuscules, mots séparés par des tirets (`ghost-light`).
- Syntaxe **BEM** : `.bloc`, `.bloc__element`, `.bloc--modificateur`.
- Un composant ne dépend jamais de son contexte : une variation passe par un modificateur.
- Le JavaScript cible uniquement des attributs `data-*`, jamais des classes.

## Préfixes

| Catégorie    | Dossier    | Préfixe        | Exemple       |
| ------------ | ---------- | -------------- | ------------- |
| Mise en page | `layout/`  | `l-`           | `.l-header`   |
| Composants   | `modules/` | *aucun*        | `.button`     |
| États        | `state/`   | `is-` / `has-` | `.is-active`  |
| Thèmes       | `theme/`   | `theme-`       | `.theme-lake` |

---

## Mise en page (layout)

### `l-container`
Centre le contenu (1200px max).

### `l-header`
En-tête du site.
- Éléments : `__inner`, `__logo`, `__mark`, `__name`, `__tagline`, `__nav`, `__link`, `__actions`
- États : `.is-active` (lien de la page courante)

### `l-footer`
Pied de page.
- Éléments : `__grid`, `__column`, `__brand`, `__title`, `__link`, `__input`, `__bottom`

### `l-docs`
Page des composants (composants.html).
- Éléments :
  - `__intro`, `__breadcrumb`, `__title`, `__lead`
  - `__nav`, `__link`
  - `__section`, `__section-title`, `__section-text`
  - `__row`, `__label`, `__examples`, `__block`, `__caption`
  - `__grid`, `__item`, `__dark`
  - `__dot`, `__scene`, `__font`, `__square`
- Modificateurs :
  - `__examples--center`
  - `__grid--small`, `--medium`, `--large`, `--variants`, `--single`
  - `__dot--{couleur}` (un par couleur : `--primary`, `--error`…)
  - `__scene--lake`, `--forest`, `--kiosk`
  - `__font--display`, `--heading`, `--subheading`, `--lead`, `--body`, `--small`
  - `__square--xs`, `--sm`, `--md`, `--lg`, `--xl`

---

## Composants (modules)

### `button`
Bouton ou lien d'action.
- Éléments : `__icon`, `__count`
- Modificateurs :
  - couleurs : `--primary`, `--secondary`, `--outline`, `--ghost-light`
  - tailles : `--small`, `--large`
  - forme : `--icon-only`
- États : `:hover` (ou `.is-hover`), `:focus-visible` (ou `.is-focused`), `.is-disabled`, `.is-loading`

### `badge`
Étiquette : scène, statut ou nombre.
- Modificateurs :
  - scènes : `--lake`, `--forest`, `--kiosk`
  - statuts : `--new`, `--last-seats`, `--sold-out`
  - tailles : `--small`, `--large`
  - styles : `--outline`, `--square`

### `card`
Carte d'artiste (la couleur de scène vient d'une classe `theme-*`).
- Éléments : `__media`, `__body`, `__title`, `__meta`, `__text`, `__link`, `__actions`
- Modificateurs : `--headliner`, `--compact`, `--horizontal`

### `pass`
Formule de pass de la billetterie.
- Éléments : `__ribbon`, `__title`, `__price`, `__features`, `__feature`, `__action`
- Modificateurs : `--featured`

### `scene-banner`
Bandeau d'accès à une scène (classe `theme-*`).
- Éléments : `__title`, `__genre`, `__link`

### `info-block`
Bloc d'information numéroté.
- Éléments : `__number`, `__title`, `__text`

### `field`
Champ de formulaire.
- Éléments : `__label`, `__input`, `__select`, `__message`
- Modificateurs : `__message--error`
- États : `:focus` (ou `.is-focused`), `.is-error`, `:disabled`

### `checkbox`
Case à cocher.
- Éléments : `__input`, `__label`
- États : `:checked`

### `filter`
Filtre le programme par scène.
- Éléments : `__button`
- États : `.is-active` (un seul à la fois)

### `faq`
Questions fréquentes (accordéon).
- Éléments : `__item`, `__question`, `__icon`, `__answer`
- États : `.is-open` sur `__item`

### À venir
`hero`, `page-title`, `stat`, `artist` (étape 7, assemblage des pages).

---

## États

- Génériques (dans `state/`) : `.is-disabled`, `.is-focused`, `.is-loading`
- Propres à un composant (dans son partial) : `.is-hover`, `.is-active`, `.is-open`, `.is-error`

## Thèmes

- `theme-lake` : Scène du Lac
- `theme-forest` : Scène de la Forêt
- `theme-kiosk` : Le Kiosque
- `theme-dark` : mode sombre (étape 8)

Un thème de scène définit `--scene-color` et `--scene-contrast` pour le bloc qui le porte.

## Historique

- Étape 1 : conventions et inventaire
- Étape 2 : jetons en variables Sass, page des composants (`l-docs`), noms simplifiés
- Page des composants complétée : boutons, badges, cartes, formulaires, filtres, FAQ, en-tête et pied de page
