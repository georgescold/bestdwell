# Bestdwell — Identité visuelle

> SaaS qui référence et classe les biens immobiliers les plus **rentables** de France,
> sourcés par scraping (Apify) et qualifiés par la donnée.

Le design vit dans [`index.html`](index.html) (à la racine du projet) ; ce document décrit le
système qui le sous-tend. Tous les tokens (couleurs, espacements) sont définis en variables CSS
dans le `:root` du fichier — c'est la source de vérité, ce document en est le mode d'emploi.

---

## 1. Positionnement

Bestdwell n'est pas un portail d'annonces de plus : c'est un **moteur d'intelligence du
rendement**. On capte la donnée brute du marché (via scraping Apify), on la qualifie (rendement
net réel, cashflow, vacance, fiscalité) et on publie un **classement vivant** des meilleures
opportunités, partout en France.

**Personnalité de marque :** rigoureux · affûté · premium (le luxe par la retenue) · limpide ·
français.

---

## 2. Langage visuel (les principes)

L'identité repose sur quelques principes simples et cohérents :

- **Mise en page centrée + preuve produit.** Hero centré (badge + titre + 2 boutons), suivi
  immédiatement d'un **aperçu de l'app** (dashboard) : on montre le produit, pas seulement un
  discours.
- **Typographie unique et affirmée.** Une seule police sans-serif, en graisse forte pour les
  titres (tracking serré), déclinée pour le texte et les labels. Ni serif, ni monospace.
- **Le bien présenté comme une fiche claire.** Grande photo → localisation · type, nom, prix
  (et €/m²), une liste de caractéristiques à icônes fines, une courte description en italique.
- **Boutons distinctifs.** Forme « pill » (coins entièrement arrondis) + un **badge rond
  contenant une flèche diagonale ↗** sur les actions principales.
- **Fond en relief discret.** Une fine trame quadrillée sur toute la page + une **grille en
  perspective** derrière le titre du hero, pour donner de la profondeur sans charger.
- **Photographie chaude.** Intérieurs lumineux, léger grade chaud — c'est la photo qui apporte la
  couleur et l'émotion.
- **Structure « blueprint ».** Un cadre à lignes-guides (bords du conteneur + filets entre
  sections + petits « + » aux intersections) pour un côté tech / éditorial, et beaucoup de blanc.

---

## 3. Couleur

**Monochrome chaud — aucun accent coloré.** Blanc pur + quasi-noir ; la couleur vient
**uniquement des photos**. La donnée ne ressort pas par une couleur mais par le **poids et le
contraste**.

| Rôle | Token | Hex |
|---|---|---|
| Fond (blanc pur) | `--paper` | `#FFFFFF` |
| Surfaces (blanc cassé chaud) | `--soft` | `#FAF8F4` |
| Surface 2 | `--soft-2` | `#F2EFE9` |
| Texte (quasi-noir) | `--ink` | `#181715` |
| Texte secondaire | `--mut` | `#6E6A62` |
| Texte tertiaire | `--mut-2` | `#A6A199` |
| Filet | `--rule` | `#ECE9E3` |
| Filet 2 | `--rule-2` | `#DEDAD2` |
| Accent (= encre, monochrome) | `--accent` | `#181715` |

**Règles d'usage**
- **Boutons = noir** (`--ink`) ; titres entièrement noirs (aucun mot coloré).
- **Hiérarchie de la donnée par le poids** : dans une fiche, les caractéristiques secondaires
  (surface, nombre de lots) sont en **gris** (`--mut`), tandis que le **rendement** et le
  **cashflow** sont en **noir gras** → l'information clé ressort par le contraste, pas par une
  couleur.
- La chaleur vient **des photos** (grade `sepia(.1) saturate(1.05)`), pas du fond.
- Le parti pris est volontairement monochrome. Si un accent de couleur devait être introduit un
  jour, il se centraliserait dans la variable `--accent` (un seul point à modifier).

---

## 4. Typographie

**Une seule famille : Manrope** (chargée via Google Fonts). Pas de serif, pas de monospace.

| Usage | Réglage |
|---|---|
| Titres (display) | Manrope **800**, tracking serré (-0.035 à -0.045em) |
| Sous-titres / texte | Manrope 400–500, interligne 1.55 |
| Labels / eyebrows | Manrope 600–700, **MAJUSCULES** trackées (+0.06 à +0.14em) |
| Chiffres / données | Manrope + `font-variant-numeric: tabular-nums` |

Échelle indicative (px) : `11 · 12 · 13.5 · 15 · 16 · 18 · 21 · 26`, et un H1 fluide
`clamp(44px → 90px)`.

---

## 5. Forme & espacement

- **Rayons** : boutons / chips = pill (100px) ; cartes & photos = 8–16px ; aperçu dashboard = 14px.
- **Boutons** : pill noir (primaire) + pill blanc bordé (secondaire), avec le **badge rond ↗** sur
  les actions principales.
- **Conteneur** : un cadre `.frame` (max 1240px) avec bords visibles (lignes-guides) ; les sections
  `.sec` sont séparées par un filet, avec un « + » à chaque intersection bord/filet.
- **Relief** : `.grid-bg` (trame plate, chaude, très discrète) sur toute la page + `.hero-relief`
  (grille en perspective) derrière le titre du hero.
- **Densité** : aéré, beaucoup de blanc.

---

## 6. Composants

1. **Nav flottante en pill** — logo, liens, « Connexion », bouton noir « Commencer ».
2. **Hero** — badge, titre (entièrement noir), sous-titre, 2 boutons, micro-ligne de réassurance.
3. **Showcase hero** — grande photo de bien + **carte de données flottante** (rendement net,
   cashflow, loyer estimé).
4. **Bandeau de preuve** — chiffres clés (biens/jour, rendement médian, départements, fraîcheur).
5. **La sélection** — fiches biens : un bloc « vedette » 2 colonnes + une grille 4 colonnes, avec
   un lien « Voir le bien → ».
6. **Le produit** — aperçu **dashboard** filtrable (onglets, chips de filtres, indicateurs,
   classement des biens).
7. **Méthode** — 3 étapes (Capter → Qualifier → Alerter).
8. **CTA** — bandeau photo plein cadre, dégradé sombre, bouton.
9. **Footer**.

---

## 7. Mouvement & accessibilité

Transitions 150–250ms, easing `cubic-bezier(.2,.7,.2,1)` ; au survol : légère élévation, léger
zoom sur les photos, décalage de la flèche des boutons. Contraste largement AA (texte quasi-noir
sur blanc). L'information clé ne dépend jamais de la seule couleur : elle est toujours portée par
un chiffre et par le poids typographique.

---

## 8. Pistes restantes

- **Photographie** : remplacer les images de stock par de vraies photos de biens (ou une curation
  d'intérieurs haut de gamme cohérents) pour atteindre le niveau « magazine ».
- **Logo / wordmark + favicon** définitifs (le monogramme carré actuel est un placeholder).
- **Build Next.js** pour passer du prototype HTML à un site déployable (ex. Vercel).
