# Analyse de Rentabilité — Aide à la Décision d'Investissement

> Projet académique · Excel / VBA · Analyse financière prévisionnelle sur 5 ans

---

## Présentation du projet

Ce projet propose un outil complet d'aide à la décision pour l'ouverture d'un point de vente commercial. Il repose sur une modélisation financière structurée en Excel, enrichie de macros VBA pour l'automatisation des scénarios et l'export des rapports.

L'outil permet à un porteur de projet ou à un analyste financier de :

- évaluer la viabilité économique d'un investissement commercial ;
- projeter les résultats financiers sur 5 ans avec des hypothèses paramétrables ;
- calculer les indicateurs de rentabilité standards (VAN, TRI, Payback, IP) ;
- identifier le seuil de rentabilité et la marge de sécurité du projet ;
- analyser la sensibilité de la VAN selon différents taux d'actualisation ;
- générer des recommandations stratégiques fondées sur les données financières.

---

## Structure du projet

```
analyse-rentabilite-investissement/
│
├── README.md                        ← Ce document
├── .gitignore
│
├── src/
│   ├── Analyse_Rentabilite.xlsx     ← Modèle financier complet (Excel)
│   └── Module_VBA.bas               ← Code source VBA (macros)
│
└── docs/
    └── guide_utilisation.md         ← Guide d'utilisation détaillé
```

---

## Contenu du classeur Excel

Le fichier `Analyse_Rentabilite.xlsx` contient six feuilles de calcul interdépendantes.

**Accueil** — Tableau de bord synthétique affichant les KPI clés du projet (VAN, TRI, Payback Period, seuil de rentabilité, résultat net An 5) et une récapitulation prévisionnelle des 4 premières années.

**Hypotheses** — Feuille centrale de paramétrage. Toutes les données d'entrée sont regroupées ici : investissement initial, hypothèses de chiffre d'affaires et de croissance, charges fixes et variables, paramètres fiscaux et financiers. Les cellules modifiables sont identifiées en bleu.

**Compte_Resultat** — Compte de résultat prévisionnel sur 5 exercices, décomposé en chiffre d'affaires, coût des marchandises vendues, marge brute, charges d'exploitation, EBITDA, EBIT, charges financières, résultat avant impôt et résultat net. Les ratios de rentabilité (marge nette, marge EBITDA) sont calculés automatiquement.

**Analyse_Investissement** — Calcul des flux de trésorerie actualisés, de la Valeur Actuelle Nette (VAN), du Taux de Rentabilité Interne (TRI), de la période de récupération (Payback Period) et de l'indice de profitabilité. Une table de sensibilité de la VAN selon 6 niveaux de taux d'actualisation est incluse.

**Seuil_Rentabilite** — Analyse de la structure des coûts (fixes vs variables), calcul du seuil de rentabilité par la méthode du taux de marge sur coût variable, point mort en jours, marge de sécurité absolue et relative. Évolution de ces indicateurs projetée sur 5 ans.

**Recommandations** — Synthèse automatisée des résultats avec indicateur de décision dynamique, et recommandations stratégiques opérationnelles rédigées sur les axes : maîtrise des charges fixes, gestion du besoin en fonds de roulement, diversification, structure de financement, gestion des risques et plan de suivi KPI.

---

## Conventions de codage couleur

| Couleur | Signification |
|---|---|
| Texte bleu | Données d'entrée — paramètres modifiables par l'utilisateur |
| Texte noir | Formules calculées automatiquement |
| Texte vert | Liens entre feuilles du classeur |
| Fond jaune | Hypothèses clés nécessitant une attention particulière |

---

## Indicateurs financiers calculés

| Indicateur | Description |
|---|---|
| VAN (NPV) | Somme actualisée des flux de trésorerie nets, déduction faite de l'investissement initial |
| TRI (IRR) | Taux d'actualisation qui annule la VAN — comparé au WACC pour la décision |
| Payback Period | Nombre d'années nécessaires pour récupérer l'investissement initial |
| Indice de Profitabilité | Ratio (VAN + I₀) / I₀ — mesure la richesse créée par euro investi |
| Seuil de rentabilité | Chiffre d'affaires minimal pour couvrir l'ensemble des charges |
| Marge de sécurité | Écart entre le CA prévisionnel et le seuil de rentabilité |
| EBITDA | Résultat avant intérêts, impôts, dotations et amortissements |

---

## Macros VBA disponibles

Le fichier `Module_VBA.bas` contient les macros suivantes, à importer dans le Visual Basic Editor (Alt + F11).

| Macro | Rôle |
|---|---|
| `AppliquerScenarioBase` | Restaure les hypothèses du scénario de référence |
| `AppliquerScenarioOptimiste` | Applique les hypothèses hautes (+CA, +marge) |
| `AppliquerScenarioPessimiste` | Applique les hypothèses basses (–CA, –marge) |
| `ProtegerClasseur` | Verrouille toutes les feuilles sauf Hypotheses |
| `DeprotegerClasseur` | Lève la protection sur toutes les feuilles |
| `ExporterRapportPDF` | Génère un rapport PDF multi-feuilles |
| `ResetHypotheses` | Réinitialise les hypothèses aux valeurs de base |
| `AllerAccueil` / `AllerHypotheses` / ... | Navigation directe entre les feuilles |

### Importer les macros VBA

1. Ouvrir le fichier Excel
2. Appuyer sur `Alt + F11` pour ouvrir l'éditeur VBA
3. Dans le menu, aller dans `Fichier → Importer un fichier`
4. Sélectionner `Module_VBA.bas`
5. Fermer l'éditeur et enregistrer le fichier au format `.xlsm`

---

## Hypothèses de base du modèle

Les valeurs par défaut correspondent à un point de vente de commerce de détail spécialisé, situé en zone urbaine, avec un gérant et un employé.

| Paramètre | Valeur |
|---|---|
| Investissement total | 109 000 € |
| Chiffre d'affaires An 1 | 300 000 € |
| Taux de croissance An 2–5 | +12%, +10%, +7%, +5% |
| Taux de marge brute | 55% |
| Loyer annuel | 36 000 € |
| Masse salariale chargée | 52 000 € |
| Taux d'actualisation (WACC) | 8% |
| Emprunt bancaire | 40 000 € sur 5 ans à 4,5% |
| Taux d'imposition (IS) | 25% |

Toutes ces valeurs sont modifiables dans la feuille **Hypotheses**.

---

## Trois scénarios préconfigurés

| Scénario | CA An 1 | Taux de marge | Croissance |
|---|---|---|---|
| Base | 300 000 € | 55% | +12%, +10%, +7%, +5% |
| Optimiste | 210 000 € × 1,4 = ~350 K€ | 58% | +18%, +15%, +10%, +8% |
| Pessimiste | 150 000 € | 50% | +6%, +5%, +4%, +3% |

---

## Prérequis

- Microsoft Excel 2016 ou version ultérieure (pour les fonctions NPV, IRR, COUNTIF, IFERROR)
- Les macros VBA nécessitent l'activation des macros dans les options de sécurité Excel
- Compatible LibreOffice Calc (formules testées) — les macros VBA requièrent une adaptation

---

## Auteur et contexte académique

Projet réalisé dans le cadre d'un cours de finance d'entreprise ou de contrôle de gestion.

Thématiques couvertes : analyse financière prévisionnelle, critères de choix d'investissement, analyse des coûts, seuil de rentabilité, modélisation sous Excel, automatisation VBA.

---

## Licence

Ce projet est partagé à des fins académiques et pédagogiques.
