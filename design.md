# Bestdwell — Identité visuelle (officielle)

> SaaS qui référence et classe les biens immobiliers les plus **rentables** de France,
> sourcés par scraping (Apify) et qualifiés par la donnée.

**Design de référence :** [`index.html`](index.html) (à la racine du projet).
C'est la direction retenue et officielle. Les autres pistes explorées (A/B et la variante
« Kastle ») ont été écartées et supprimées.

---

## 1. Positionnement

Bestdwell n'est pas un portail d'annonces de plus : c'est un **moteur d'intelligence du
rendement**. On capte la donnée brute du marché (Apify), on la qualifie (rendement net réel,
cashflow, vacance, fiscalité) et on publie un **classement vivant** des meilleures opportunités,
partout en France.

**Personnalité :** rigoureux · affûté · premium (luxe par la retenue) · limpide · français.

---

## 2. Synthèse de la direction

L'identité combine plusieurs sources, fusionnées intelligemment :

| Brique | Origine | Ce qu'on en garde |
|---|---|---|
| **Disposition** | Kastle | Hero centré (badge + titre + 2 boutons) + **dashboard produit** sous le hero |
| **Typographie** | Ray | Une seule police grasse (Manrope), titres serrés, pas de serif ni de mono |
| **Présentation des biens** | Rently | Fiches : photo → lieu·type, nom, prix·€/m², specs à icônes, description italique |
| **Boutons** | Hombox | Pill + **badge rond avec flèche diagonale ↗** |
| **Fond en relief** | ScaleTrace | Trame quadrillée discrète + **grille en perspective** dans le hero |
| **Photographie** | Ray | Intérieurs chauds, grade sépia léger |

Plus un **cadre à lignes-guides** (bords + filets entre sections + « + » aux intersections) pour
le côté « tech / blueprint », et beaucoup de blanc.

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
- **Boutons = noir** (`--ink`) ; titres entièrement noirs (pas de mot coloré).
- **Hiérarchie de la donnée par le poids** : dans une fiche bien, les specs secondaires (m², lots)
  sont en **gris** (`--mut`), le rendement + le cashflow en **noir gras** → ça ressort par le
  contraste, pas par une couleur.
- La chaleur vient **des photos** (grade `sepia(.1) saturate(1.05)`), pas du fond.
- ⚠️ Historique : les accents bruns/bronzes puis un bleu foncé ont été testés et **écartés** ; on
  reste monochrome. Si un accent est rouvert un jour, le centraliser dans `--accent`.

---

## 4. Typographie

**Une seule famille : Manrope** (pas de serif, pas de monospace).

| Usage | Réglage |
|---|---|
| Titres (display) | Manrope **800**, tracking serré (-0.035 à -0.045em) |
| Sous-titres / texte | Manrope 400–500, line-height 1.55 |
| Labels / eyebrows | Manrope 600–700, **MAJUSCULES** trackées (+0.06 à +0.14em) |
| Chiffres / données | Manrope + `font-variant-numeric: tabular-nums` |

Échelle indicative : `11 · 12 · 13.5 · 15 · 16 · 18 · 21 · 26 · clamp(44→90)` pour le H1.

---

## 5. Forme & espacement

- **Rayons** : boutons/chips = pill (100px) ; cartes/photos = 8–16px ; mock dashboard = 14px.
- **Boutons** : pill noir (primaire) + pill blanc bordé (secondaire), tous deux avec le **badge
  rond ↗** sur les actions principales.
- **Conteneur** : cadre `.frame` max 1240px avec bords (lignes-guides) ; sections `.sec` séparées
  par un filet + « + » aux intersections.
- **Relief** : `.grid-bg` (trame plate chaude, très discrète) sur toute la page + `.hero-relief`
  (grille en perspective) derrière le titre.
- **Densité** : aéré, beaucoup de blanc.

---

## 6. Composants

1. **Nav flottante en pill** (logo, liens, « Connexion », « Commencer » noir).
2. **Hero** : badge, titre (mot-clé en bleu), sous-titre, 2 boutons, micro-ligne de réassurance.
3. **Showcase hero** : grande photo de bien + **carte de données flottante** (rendement net, cashflow, loyer).
4. **Bandeau de preuve** : biens/jour, rendement médian, départements, fraîcheur.
5. **La sélection (Rently)** : fiches vedette 2 colonnes + grille 4 colonnes, lien « Voir le bien → ».
6. **Le produit** : mock **dashboard** filtrable (segments, chips de filtres, KPIs, classement).
7. **Méthode** : 3 étapes (Capter → Qualifier → Alerter).
8. **CTA** : bandeau photo plein cadre, dégradé sombre, bouton.
9. **Footer**.

---

## 7. Mouvement & accessibilité

Transitions 150–250ms, easing `cubic-bezier(.2,.7,.2,1)` ; survol : élévation légère, léger zoom
photo, décalage de la flèche des boutons. Contraste AA (le bleu `#26408C` ~7:1 sur blanc) ; la
donnée ne dépend jamais de la seule couleur (toujours un chiffre + un poids).

---

## 8. Pistes restantes

- **Photographie** : passer aux vraies photos de biens (ou une curation d'intérieurs haut de gamme)
  pour atteindre le niveau « magazine ».
- **Logo / wordmark + favicon** définitifs (le monogramme carré est un placeholder).
- **Build Next.js** pour passer du proto au site déployable (Vercel).
