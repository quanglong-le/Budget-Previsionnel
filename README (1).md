# Budget Prévisionnel & Analyse des Écarts
### Chaîne de Restauration Rapide — Style KFC / AmRest

---

## Présentation

Ce projet académique présente la construction complète d'un **budget prévisionnel** et une **analyse des écarts** pour une chaîne de cinq restaurants en France, opérant sous un modèle de restauration rapide (QSR) comparable à AmRest (franchisé KFC en Europe).

---

## Contenu du rapport

| Section | Description |
|---|---|
| **01 — Contexte & Méthodologie** | Périmètre, hypothèses, approche bottom-up |
| **02 — Budget Prévisionnel** | CA, coûts matières, masse salariale, EBITDA |
| **03 — Saisonnalité mensuelle** | Coefficients et répartition du budget par mois |
| **04 — P&L Budget vs Réel** | Compte de résultat synthétique consolidé |
| **05 — Analyse des Écarts** | Décomposition par nature et par restaurant |
| **06 — Tableau de Bord KPI** | Ticket moyen, food cost, prime cost, EBITDA% |
| **07 — Visualisations graphiques** | 7 graphiques interactifs (Chart.js) |
| **08 — Recommandations** | 8 actions prioritaires avec impact chiffré |
| **09 — Conclusion & Prévisions N+1** | Scénarios de redressement budgétaire |

---

## Données clés — Exercice 2024

| Indicateur | Budget | Réel | Écart |
|---|---|---|---|
| CA HT total | 4 701 608 € | 4 489 340 € | -4,5 % |
| Food Cost / CA | 28,0 % | 31,7 % | +3,7 pts |
| Masse salariale / CA | 31,0 % | 34,4 % | +3,4 pts |
| Prime Cost | 59,0 % | 66,1 % | +7,1 pts |
| EBITDA | 840 004 € | 294 773 € | -64,9 % |
| Marge EBITDA | 17,9 % | 6,6 % | -11,3 pts |

---

## Structure du projet

```
budget-previsionnel-amrest/
├── README.md
└── budget-previsionnel-amrest.html   # Rapport complet (standalone)
```

---

## Technologies utilisées

- **HTML5 / CSS3** — Mise en page et design responsive
- **Chart.js 4.4.1** — Visualisations graphiques interactives
- **Google Fonts** — Playfair Display + IBM Plex Sans + IBM Plex Mono

Le fichier HTML est **entièrement autonome** (single-file). Aucune installation requise.

---

## Utilisation

```bash
git clone https://github.com/<votre-username>/budget-previsionnel-amrest.git
cd budget-previsionnel-amrest
# Ouvrir dans un navigateur
open budget-previsionnel-amrest.html
```

---

## KPI couverts

- **Ticket moyen** (réel vs budget)
- **Food Cost / CA** (taux de matières premières)
- **Masse salariale / CA**
- **Prime Cost** (food + labor)
- **EBITDA et marge EBITDA**
- **CA par m²**
- **Couverts journaliers**

---

## Disclaimer

> Les données présentées dans ce rapport sont **entièrement simulées** à des fins pédagogiques. Elles ne reflètent pas les résultats réels d'AmRest, KFC ou de toute autre société. Ce projet est produit dans le cadre d'un cours de finance d'entreprise / contrôle de gestion.

---

## Auteur

Projet académique — Finance d'Entreprise — 2024-2025  
Licence : MIT — Réutilisation libre avec attribution
