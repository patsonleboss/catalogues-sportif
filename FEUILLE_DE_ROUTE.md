# 🏀⚽🏈 Feuille de route adaptée : JP Jersey (Projet 1 - IFT1005)

Ce document compare **le site actuel sur GitHub** (`julienlsjean-cmd/catalogue-sportif`, branche `main`) aux exigences du guide officiel, et liste ce qu'il reste à faire, page par page.

**Légende :** ✅ déjà conforme · ⚠️ existe mais à corriger · ❌ manquant

> ⚠️ **Rappel important :** le guide interdit le **code généré par IA**. Ce document est un outil d'organisation. Le code HTML/CSS doit être écrit par Patrice et Julien.

---

## 🏟️ Choix des équipes (décision de l'équipe)

**3 univers sportifs, 1 équipe par sport, 2 maillots par équipe (6 au total).**

| Univers | Équipe | Image actuelle |
|---|---|---|
| ⚽ Soccer | **CF Montréal** | `soccer.png` : CF Montréal ✅ |
| 🏀 Basketball | **Raptors de Toronto** | `basketball.png` : Raptors ✅ (à compresser, 3 Mo) |
| 🏈 Football | **Alouettes de Montréal** | `football.png` : Alouettes ✅ |

👉 Il manque **1 photo de plus par équipe** (2ᵉ maillot, ex : domicile + extérieur). Noter la source de chaque photo pour le README.
👉 Le guide exige **au moins 6 maillots** : avec 2 maillots maximum par équipe, il en faut **exactement 2 par équipe**.

> ⚠️ **Écart avec le guide officiel, à faire valider par le professeur :**
> - Le guide demande **Hockey** comme 3ᵉ univers. Ici, c'est le **Football** qui le remplace.
> - Pour le soccer, le guide n'accepte que des clubs de **Ligue des Champions UEFA** ou les sélections **Canada / États-Unis / Mexique**. Le **CF Montréal** joue en MLS.
>
> Mieux vaut obtenir l'accord écrit du professeur (courriel) et le mentionner dans le README, pour ne pas perdre de points.

---

## 📊 État actuel du projet (résumé)

| Élément | État | Remarque |
|---|---|---|
| `index.html` | ⚠️ | Les 3 sports sont déjà les bons ✅, mais il manque l'ImageMap et Google Fonts |
| `catalogue.html` | ❌ | N'existe pas sur `main` (lien du menu en erreur 404) |
| `collection.html` | ⚠️ | Existe, mais aucun style (texte noir sur fond bleu foncé, illisible) |
| `boutique.html` | ❌ | N'existe pas (lien du menu en erreur 404) |
| `style.css` | ⚠️ | Unique pour tout le site ✅, mais les sections « catalogue » et « notre univers » sont vides |
| `README.md` | ❌ | Contient seulement 2 lignes, à remplacer par le modèle du guide |
| `charte_equipe.pdf` | ❌ | Manquant |
| Dossier `assets/` | ⚠️ | Les images sont dans `images/` : renommer le dossier en `assets/` et mettre à jour tous les chemins |
| JavaScript | ✅ | Aucun JS sur `main` (à garder ainsi) |
| Commentaires d'identification | ❌ | Absents de tous les fichiers |

---

## 🛠️ Technologies & Règles strictes (vérification)

* [x] HTML5 + CSS3 uniquement, aucun JavaScript sur `main`.
* [ ] **Google Fonts** : à ajouter (le site utilise Arial pour l'instant).
* [ ] **SVG** : aucun pour l'instant (requis sur `boutique.html`).
* [x] Pas de framework CSS.
* [x] Chemins relatifs (`style.css`, `images/...`) : à conserver après le passage à `assets/`.
* [ ] Tester dans **Google Chrome** (ordinateur + mode mobile avec F12).

---

## 📁 Structure cible vs structure actuelle

```text
Actuel                          Cible (JP_Jersey_Projet1.zip)
├── index.html          ⚠️      ├── index.html
├── collection.html     ⚠️      ├── catalogue.html        ❌ à créer
├── style.css           ⚠️      ├── collection.html
├── README.md           ⚠️      ├── boutique.html         ❌ à créer
├── .gitattributes              ├── style.css
└── images/             ⚠️      ├── README.md
    ├── basketball.png          ├── charte_equipe.pdf     ❌ à ajouter
    ├── football.png            └── assets/               (renommer images/)
    └── soccer.png
```

**Fichiers à exclure du ZIP :** `.gitattributes`, `.git/`, `.claude/`, et ce fichier `FEUILLE_DE_ROUTE.md`.

> ⚠️ **Identification :** ajouter en commentaire, en haut de `index.html`, `catalogue.html`, `collection.html`, `boutique.html`, `style.css` et dans le `README.md` :
> **Patrice Yerkobo Doume (20358613)** et **Julien Luis-Jean (20275728)**.

---

## ✅ Checklist adaptée, page par page

### 1. Éléments communs aux 4 pages
* [ ] **Navigation** : renommer « Produits » en **« Catalogue »**. Les liens existent déjà, mais `catalogue.html` et `boutique.html` sont à créer.
  * ✅ Effet `:hover` déjà présent (`nav a:hover`). ⚠️ La couleur au survol (`#0e3e6e`) est presque invisible sur le fond noir/bleu : choisir une couleur plus claire.
  * ✅ La classe `active` est déjà utilisée pour la page courante.
* [ ] **Footer** : existe sur 2 pages. Ajouter la mention **« boutique éphémère »** (ex : « JP Jersey – Boutique éphémère © 2026 »), puis le copier à l'identique sur les 4 pages.
* [x] **HTML sémantique** : `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>` déjà utilisés. ⚠️ Vérifier la hiérarchie des titres (pas de saut de `<h1>` à `<h3>`).
* [ ] **Accessibilité** :
  * ⚠️ `collection.html` : texte noir sur fond bleu foncé, contraste illisible.
  * ⚠️ `.sport h2` (couleur `#000913`) sur fond bleu foncé : peu lisible.
  * ⚠️ Rendre les `alt` plus descriptifs (ex : « Maillot rouge des Raptors de Toronto » au lieu de « Basketball »).
* [x] **Responsive** : une `@media (max-width: 768px)` existe déjà. ⚠️ Vérifier l'absence de débordement horizontal : le zoom `scale(1.5)` au survol des cartes peut dépasser sur petit écran.

### 2. Page d'accueil (`index.html`)
* [ ] **Google Fonts** : ajouter une police sportive (ex : Oswald, Bebas Neue) pour le titre « JP JERSEY ».
* [x] **Bannière promotionnelle** : la section `.hero` existe. ⚠️ Mentionner explicitement le **pop-up store / boutique éphémère**. Le commentaire `<!-- À retravailler -->` est encore là.
* [ ] **Présentation** : préciser que JP Jersey est spécialiste des **maillots officiels**. Le bouton « Découvrir nos produits » mènera au catalogue une fois la page créée.
* [ ] **ImageMap (obligatoire)** : ❌ absente. Remplacer (ou compléter) les 3 cartes actuelles par **une seule image vitrine** montrant les 3 sports, avec `<map>` + 3 `<area>` qui pointent vers `catalogue.html#soccer`, `catalogue.html#basketball` et `catalogue.html#football`.
* [ ] **Liens textuels de secours** : 3 liens texte vers les mêmes ancres que l'ImageMap.
* [ ] Corriger : « CHOISI TON SPORT » → « CHOISIS TON SPORT ».

### 3. Page Catalogue (`catalogue.html`) ❌ à créer
* [ ] Même `<header>`, `<nav>` et `<footer>` que les autres pages.
* [ ] **3 sections avec `id`** : `id="soccer"`, `id="basketball"`, `id="football"`, pour que l'ImageMap et les liens de l'accueil fonctionnent **sans JavaScript**.
* [ ] **6 maillots** sous forme de cartes, regroupés par sport :
  * ⚽ Soccer : **CF Montréal** (2 maillots).
  * 🏀 Basketball : **Raptors de Toronto** (2 maillots).
  * 🏈 Football : **Alouettes de Montréal** (2 maillots).
* [ ] **Sur chaque carte** : image (`alt` descriptif), équipe/joueur, **Genre** (Homme / Femme / Enfant), **Tailles** (S, M, L, XL…), courte description, prix fictif.
* [ ] **CSS Grid** : au moins **3 colonnes** sur grand écran (`grid-template-columns: repeat(3, 1fr)`) + `gap`.
* [ ] **Mobile** : `@media` → **1 colonne**.
* [ ] **`:hover`** sur les cartes (ombre, bordure ou léger zoom).
* [ ] Pas de vrai panier (aucun bouton « Ajouter au panier » fonctionnel).

### 4. Page Collections / Notre univers (`collection.html`) ⚠️
* [x] Le fichier s'appelle bien `collection.html`, et son titre dans le menu est « Notre univers ».
* [x] Texte de présentation déjà présent. ⚠️ Ajouter l'**histoire** et la **passion pour les maillots authentiques**. Corriger « fannatique » → « fanatiques » et « club favorite » → « club favori ».
* [ ] **3 sections distinctes** (actuellement les 3 collections sont dans une seule section) :
  1. **Collection Soccer** : CF Montréal
  2. **Collection Basketball** : Raptors de Toronto
  3. **Collection Football** : Alouettes de Montréal
  * Chacune doit avoir : un titre, une description des **coupes et tailles**, et **au moins un visuel** (les `<!-- <img> -->` sont encore vides).
* [ ] **Flexbox** : la classe `.collection-container` existe, mais elle n'a aucun style. Mettre les collections en colonnes sur ordinateur, empilées sur mobile.
* [ ] **Listes** :
  * ❌ `<ul>` : à ajouter (ex : genres et tailles disponibles, ou critères de qualité).
  * ✅ `<ol>` : déjà présente (« Étapes pour choisir son jersey »). Corriger « JERSY » → « JERSEY ».
* [ ] **Animation `@keyframes`** : ❌ à ajouter (ex : apparition des titres, badge « Édition limitée »).
* [ ] **Tout le style de la page** est à écrire (section `/* Page notre univers */` vide dans `style.css`).

### 5. Page Notre boutique (`boutique.html`) ❌ à créer
* [ ] **Infos pratiques** : adresse fictive (Montréal), dates d'ouverture, horaires.
* [ ] **Contact** : téléphone fictif + lien `mailto:`.
* [ ] **2 icônes SVG cliquables** vers des sites externes pertinents (ex : Instagram, site du CF Montréal, des Raptors ou des Alouettes). Citer la source des icônes dans le README.
* [ ] **1 SVG original fait à la main** (`<rect>`, `<circle>`, `<path>`, `<polygon>`…) : un **maillot** ou une **étiquette de taille**.
* [ ] **Animation continue de ce SVG** : **déplacement horizontal** + **changement de couleur périodique** (`@keyframes`).

---

## 📄 Livrables à préparer

* [ ] **README.md** : remplacer le contenu actuel par le modèle du guide (équipe, lien vidéo, choix de conception, palette, sources des polices, images et icônes).
  * Thème à indiquer : maillots **CF Montréal (soccer)**, **Raptors de Toronto (basketball)** et **Alouettes de Montréal (football)**, ainsi que l'accord du professeur pour ce choix.
  * Palette actuelle du site, à reporter : `#001f3f` (bleu marine), `#004489` (bleu), `#9bdcf2` (bleu ciel), `#00ddff` (cyan, lien actif), `#000000` (noir), `#ffffff` (blanc).
* [ ] **charte_equipe.pdf** : rédiger et signer.
* [ ] **Vidéo YouTube** (3 min max, « Non répertoriée ») : navigation des 4 pages, test responsive, explication de l'ImageMap, de la Grid, de la Flexbox, des animations et du SVG, choix graphiques et répartition du travail.
* [ ] **ZIP final** `JP_Jersey_Projet1.zip` avec uniquement les fichiers de la structure cible.

---

## 🗂️ Ordre de travail suggéré

1. Faire valider le choix des équipes par le professeur.
2. Renommer `images/` en `assets/` et ajouter les 3 photos manquantes (2ᵉ maillot de chaque équipe).
3. Ajouter les commentaires d'identification, Google Fonts, le footer et la nav « Catalogue » communs.
4. Créer `catalogue.html` (Grid + ancres `#soccer`, `#basketball`, `#football`).
5. Ajouter l'ImageMap et les liens de secours sur `index.html`.
6. Refaire `collection.html` (3 sections, Flexbox, `<ul>`, `@keyframes`) et son style.
7. Créer `boutique.html` (infos, `mailto:`, 2 icônes SVG, SVG original animé).
8. Corriger les contrastes et les fautes, puis tester dans Chrome (ordinateur + mobile).
9. README, charte d'équipe, vidéo, ZIP.

**Répartition à décider entre Patrice et Julien** (à noter pour la vidéo) :

| Tâche | Responsable |
|---|---|
| Accueil + ImageMap | |
| Catalogue | |
| Collections | |
| Boutique + SVG | |
| README, charte, vidéo | |
