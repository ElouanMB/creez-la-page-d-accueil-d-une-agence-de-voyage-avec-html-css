# 📐 Spécifications Techniques Complètes — Maquette Booki

> **Document généré automatiquement à partir de l'API Figma**
> **Projet** : Maquettes Booki (desktop, mobile, tablette)
> **Police globale** : `'Raleway', sans-serif`

---

## 🎨 1. Palette de Couleurs (Design Tokens)

| Token / Usage | Code HEX | Code RGBA | Aperçu |
| :--- | :--- | :--- | :--- |
| **Bleu principal (Action, icônes, liens)** | `#0065FC` | `rgba(0, 101, 252, 1)` | `var(--main-color)` |
| **Bleu clair (Filtres hover / actif)** | `#DEEBFF` | `rgba(222, 235, 255, 1)` | `var(--filter-bg-color)` |
| **Gris fond sections (Hébergements, footer)** | `#F2F2F2` | `rgba(242, 242, 242, 1)` | `var(--main-bg-color)` |
| **Gris bordures (Filtres, input search)** | `#D9D9D9` | `rgba(217, 217, 217, 1)` | `var(--border-color)` |
| **Blanc pur (Cartes, fond page)** | `#FFFFFF` | `rgba(255, 255, 255, 1)` | Cartes & Inputs |
| **Texte principal (Titres, corps)** | `#000000` | `rgba(0, 0, 0, 1)` | Titres & paragraphes |

---

## ✍️ 2. Typographie (`Raleway`)

- **Titres de section (`h2`)** : `22px`, `font-weight: 700` (Bold), `line-height: 26px`
- **Titres de carte (`h3`)** : `16px`, `font-weight: 700` (Bold), `line-height: 19px`
- **Texte filtres et boutons** : `16px` / `17px`, `font-weight: 700` (Bold)
- **Sous-titres de carte & prix** : `14px`, `font-weight: 400` (Regular)
- **Prix en gras (`.euro`)** : `14px`, `font-weight: 700` (Bold)
- **Texte d'information ("Plus de 500 logements...")** : `16px`, `font-weight: 400`
- **Lien "Afficher plus"** : `18px`, `font-weight: 700`

---

## 🏗️ 3. Structure globale & Conteneurs

- **Largeur max Desktop** : `1440px`
- **Padding conteneur Desktop / Tablette** : `padding: 0 50px;`
- **Padding conteneur Mobile** : `padding: 0;` (les sections gèrent leur propre padding)
- **Ombre des cartes** : `filter: drop-shadow(0px 3px 15px rgba(0, 0, 0, 0.1));` ou `box-shadow: 0px 3px 15px rgba(0, 0, 0, 0.1);`
- **Rayon de bordure cartes / sections** : `border-radius: 20px;`

---

## 🧩 4. Spécifications Détaillées par Composant

### 🔹 A. Header & Navigation
- **Desktop (1440px)** :
  - Hauteur : `79px`
  - Disposition : `display: flex; justify-content: space-between; align-items: center;`
  - Logo Booki : `width: 61px; height: 19px;`
  - Liens de navigation : "Hébergements" et "Activités"
  - Espacement entre liens : `gap: 68px;`
  - Au survol / actif : bordure supérieure bleue `border-top: 2px solid #0065FC; color: #0065FC; padding-top: 15px;`
- **Mobile (< 768px)** :
  - Disposition : colonne (`flex-direction: column;`)
  - Logo centré en haut avec du padding (`padding: 30px 0;`)
  - Les 2 liens de navigation se placent en dessous, chacun à **50% de largeur** (`width: 50%; text-align: center;`)
  - Bordure active en **bas** (`border-bottom: 2px solid #0065FC;`) au lieu du haut !

---

### 🔹 B. Groupe "Info" (Titre + Recherche + Filtres + Infobar)

#### 1. Titre et slogan (`Headline`)
- **Titre (h1)** : `Trouvez votre hébergement pour des vacances de rêve` (`22px`, bold)
- **Slogan (p)** : `En plein centre-ville ou en pleine nature` (`16px`, regular)
- Marge inférieure : `35px`

#### 2. Barre de recherche (`Search-bar`)
- **Hauteur** : `49px`
- **Formulaire flexbox** : `display: inline-flex;`
- **Icône localisation** :
  - Fond gris `#F2F2F2`, icône `fa-solid fa-location-dot` noire
  - Largeur : `50px`, centrée
  - Arrondi : `border-radius: 15px 0 0 15px;`
- **Champ de saisie (`input`)** :
  - Texte : `Marseille, France` (bold, 18px)
  - Bordures : `1px solid #F2F2F2` (haut et bas, pas de bordure gauche ni droite)
  - Padding intérieur : `0 24px;`
- **Bouton de soumission (`button`)** :
  - **Desktop** : texte "Rechercher" (`font-weight: 700`, blanc), fond `#0065FC`, arrondi `0 15px 15px 0;`, padding `0 16px;`
  - **Mobile** : le texte disparaît et est remplacé par une icône loupe (`fa-solid fa-magnifying-glass`), arrondi `15px`, ombre `0px 4px 4px rgba(0, 0, 0, 0.25);`

#### 3. Filtres (`Filter`)
- **Titre** : `Filtres` (bold, 18px)
- **4 Boutons filtres** :
  1. `Économique` (Icône Font Awesome : `fa-solid fa-money-bill-wave`)
  2. `Familial` (Icône Font Awesome : `fa-solid fa-person`)
  3. `Romantique` (Icône Font Awesome : `fa-solid fa-heart`)
  4. `Nos pépites` (Icône Font Awesome : `fa-solid fa-fire`)
- **Style des filtres** :
  - Forme pilule : `border-radius: 25px;`
  - Hauteur : `50px`
  - Bordure : `2px solid #D9D9D9;`
  - Padding : `0 19px;`
  - Gap intérieur (icône / texte) : `10px`
  - Couleur icône : `#0065FC`
  - **Au survol (`:hover`)** : `background-color: #DEEBFF;`

#### 4. Barre d'information (`Infobar`)
- Disposition : flex, `align-items: center;`, `gap: 10px;`
- **Icône "i"** : cercle de `24px × 24px`, bordure `1px solid #D9D9D9`, `border-radius: 50%`, icône bleue `#0065FC`
- **Texte** : `Plus de 500 logements sont disponibles dans cette ville` (16px, regular)

---

### 🔹 C. Section Hébergements & Populaires (`hebergements-and-populaires`)

#### 1. Organisation globale
- **Desktop (> 1024px)** :
  - Disposition côte à côte : `display: flex; justify-content: space-between; gap: 40px;`
  - Hébergements : largeur `65%`
  - Populaires : largeur `32%`
- **Tablette (768px – 1024px)** :
  - Empilés en colonne : `flex-direction: column; gap: 50px;`
  - Hébergements et Populaires prennent chacun `100%`
  - Les 3 cartes populaires passent sur une seule ligne horizontale (`30%` de largeur chacune).
- **Mobile (< 768px)** :
  - **INVERSION DE L'ORDRE** : Populaires s'affiche **AVANT** Hébergements !
  - Populaires : fond gris `#F2F2F2`, `border-radius: 0;` (pleine largeur écran)
  - Hébergements : fond blanc transparent, `padding: 20px 20px 0 20px;`, pas de fond gris.

#### 2. Cartes "Hébergements à Marseille" (6 cartes en grille)
- **Titre** : `Hébergements à Marseille` (h2, 22px)
- **Grille Desktop** : 2 lignes de 3 cartes (`display: grid; grid-template-columns: repeat(3, 1fr); gap: 30px;`) ou Flexbox.
- **Détails de chaque carte** :
  - Fond blanc, `border-radius: 20px;`, `padding: 5px;`
  - Image : `width: 100%; height: 124px; object-fit: cover; border-radius: 20px 20px 0 0;`
  - Contenu texte : `padding: 0 15px;`
  - Titre h3 : 16px bold
  - Sous-titre : 14px regular ("Nuit à partir de XX€")
  - Étoiles de notation : 5 étoiles (`fa-solid fa-star`), les étoiles inactives ont la classe `.neutral-star` (`#F2F2F2`).
- **Lien en bas** : `Afficher plus` (18px, bold)

#### 3. Cartes "Les plus populaires" (3 cartes)
- Titre : `Les plus populaires` + icône `fa-solid fa-chart-line`
- Carte horizontale :
  - `display: flex;`
  - Image à gauche : `width: 33%; height: 136px; border-radius: 20px 0 0 20px;`
  - Contenu à droite : `width: 67%; padding-left: 15px; display: flex; flex-direction: column; justify-content: space-between;`

---

### 🔹 D. Section Activités à Marseille
- **Titre** : `Activités à Marseille` (h2, 22px, marge 30px)
- **Desktop** : 4 cartes sur une même ligne (`display: flex; gap: 30px;` ou `grid-template-columns: repeat(4, 1fr);`)
- **Dimensions d'une carte Desktop** :
  - Hauteur totale : `439px`
  - Image : `height: 380px; object-fit: cover; border-radius: 20px 20px 0 0;`
  - Titre (h3) : `padding: 20px 19px;`, 16px bold
  - Arrondi carte : `border-radius: 20px;`
  - Ombre : `box-shadow: 0px 3px 15px rgba(0, 0, 0, 0.1);`
- **Tablette** : Hauteur totale réduite à `270px` (Image ~`200px`).
- **Mobile** : 4 cartes empilées verticalement (`flex-direction: column; gap: 15px;`), hauteur totale `200px` par carte (Image ~`140px`).

---

### 🔹 E. Footer (Pied de page)
- **Fond** : `background-color: #F2F2F2;`
- **Desktop & Tablette** :
  - `display: flex; justify-content: space-between;`
  - 3 colonnes de largeur égale (`width: 30%;`)
  - Padding : `padding: 20px 0;`
- **Mobile** :
  - `flex-direction: column; gap: 50px;`
  - Padding : `padding: 30px;`
- **Colonnes & Liens** :
  1. **À propos** : Fonctionnement du site, Conditions générales, Données et confidentialité
  2. **Nos hébergements** : Charte qualité, Proposer votre hébergement
  3. **Assistance** : Centre d'aide, Nous contacter
  - Titres de colonne : 18px bold
  - Liens : 16px regular, `line-height: 2`
