# Dashboard CA vs Rentabilité — Pilotage Financier PME | Excel + Power BI

> **40% des entrepreneurs font du CA mais ne gagnent pas d'argent.**  
> 24 mois · 233 lignes · 9 mesures DAX · Alertes automatiques · Tutoriel YouTube 43 min

![Dashboard Preview](Dashboard_CA_vs_Rentabilité.png)

🇬🇧 [English version available here](README.md)

---

## Problème Business

La confusion entre **Chiffre d'Affaires** et **Rentabilité** coûte des milliers
de dirhams aux entrepreneurs chaque année.

```
CA (ce qui entre) − Coûts Variables − Coûts Fixes = Bénéfice Net (ce qui reste)
```

Ce projet démontre comment construire un système de pilotage financier complet
pour détecter automatiquement les mois problématiques avant qu'ils deviennent
des crises, et prendre des décisions basées sur la data.

---

## Résultats sur 24 Mois (Jan 2023 – Déc 2024)

| Indicateur | Valeur |
|---|---|
| CA Total | 2 079 000 MAD |
| Bénéfice Net | 1 590 717 MAD |
| Marge Nette Moyenne | **76,5%** |
| Coûts Variables | 109 083 MAD — 5,3% du CA |
| Coûts Fixes | 379 200 MAD — maîtrisés |

---

## Cas d'Étude — Juillet 2024 : Le Mois Catastrophe

| Indicateur | Janvier 2024 | Juillet 2024 | Écart |
|---|---|---|---|
| CA | 105 000 MAD | 48 000 MAD | -54% |
| Coûts Variables | 2 300 MAD | 40 000 MAD | +1 639% |
| Bénéfice Net | 86 900 MAD | -7 800 MAD | -109% |
| Marge Nette | 82,8% | **-16,2%** | -99 pts |

**Cause identifiée :** Campagne marketing — 40 000 MAD investis pour 48 000 MAD de CA.  
ROI réel : -16,2%. Ratio Coûts/CA : 83% (seuil critique > 50%).

**Décision business déclenchée par le dashboard :**
- Arrêt immédiat de ce type de campagne
- Budget marketing plafonné à 5% du CA prévisionnel
- Test A/B obligatoire avant tout investissement > 5 000 MAD

**Alertes dashboard activées automatiquement :**
🔴 Statut Marge : Fragile · 🔴 Alerte Coûts : Trop élevés

---

## Dashboard — Composants

![Dashboard](Dashboard_CA_vs_Rentabilité.png)

| Composant | Description |
|---|---|
| 4 cartes KPI | CA · Marge Brute % · Bénéfice Net · Marge Nette % |
| 2 alertes conditionnelles | Statut Marge · Alerte Coûts Variables |
| Graphique Waterfall | CA → Marge Brute → Bénéfice Net (gains/pertes colorés) |
| Évolution mensuelle | CA et Bénéfice Net sur 24 mois — détecte Juillet 2024 |
| Analyse par service | Marge Nette % par type de prestation (barres horizontales) |
| Filtres interactifs | Slicers Année + Mois — mise à jour dynamique |

---

## Mesures DAX — 9 Mesures

```dax
// KPIs principaux
CA_Total = SUM(Ventes[Montant_HT])

Coûts_Variables =
CALCULATE(SUM(Depenses[Montant]), Depenses[Type_Cout] = "Variable")

Coûts_Fixes =
CALCULATE(SUM(Depenses[Montant]), Depenses[Type_Cout] = "Fixe")

Marge_Brute        = [CA_Total] - [Coûts_Variables]
Marge_Brute_%      = DIVIDE([Marge_Brute], [CA_Total], 0)
Bénéfice_Net       = [Marge_Brute] - [Coûts_Fixes]
Marge_Nette_%      = DIVIDE([Bénéfice_Net], [CA_Total], 0)

// Alertes conditionnelles
Statut_Marge =
VAR Marge = [Marge_Nette_%]
RETURN SWITCH(TRUE(),
    Marge < 0.10, "Fragile",
    Marge < 0.20, "Correct",
    Marge < 0.30, "Bon",
    Marge < 0.40, "Très Bon",
    "Excellent"
)

Alerte_Couts =
VAR Ratio = DIVIDE([Coûts_Variables], [CA_Total], 0)
RETURN SWITCH(TRUE(),
    Ratio > 0.50, "Coûts trop élevés",
    Ratio > 0.30, "Surveiller",
    "Sous contrôle"
)
```

---

## Données du Projet

| Paramètre | Valeur |
|---|---|
| Volume | 233 lignes (126 ventes + 107 dépenses) |
| Période | 24 mois — Jan 2023 → Déc 2024 |
| Tables Power BI | 3 (Ventes · Dépenses · Calendrier) |
| Devise | MAD — Dirham marocain |
| Source | Excel 5 onglets (Parametres · Ventes · Dépenses · Cash Flow · Dashboard) |

**Colonne critique :** `Type_Cout` (FIXE / VARIABLE) — pilote toutes les mesures DAX de rentabilité.

---

## Tutoriel YouTube — 43 Minutes

[![YouTube](https://img.shields.io/badge/YouTube-Voir%20le%20tutoriel%20complet%2043%20min-red?logo=youtube)](https://youtu.be/AUYo3agdDWY)

| Timestamp | Contenu |
|---|---|
| 00:00 | Problématique : CA ≠ Rentabilité |
| 01:00 | Théorie — Schéma P&L |
| 03:00 | Structure Excel — 5 onglets |
| 06:00 | Import Power BI + modèle relationnel |
| 09:50 | 9 mesures DAX + alertes conditionnelles |
| 15:00 | Design dashboard complet |
| 38:00 | Analyse business — Janvier vs Juillet 2024 |

---

## Stack Technique

- **Excel 365** — structuration des données (233 lignes)
- **Power BI Desktop** — dashboard interactif
- **DAX** — 9 mesures calculées
- **Power Query / M** — import et nettoyage

---

## Installation

```bash
# 1. Cloner le repository
git clone https://github.com/bouba02/Dashboard-CA-Rentabilite.git

# 2. Ouvrir Excel
# Excel/Pilotage_Financier_Ngroup.xlsx

# 3. Ouvrir Power BI
# PowerBI/Dashboard_CA_Rentabilite.pbix
# → Les données sont déjà importées
```

---

## Structure du Repository

```
Dashboard-CA-Rentabilite/
├── README.md
├── README_FR.md
├── Dashboard_CA_vs_Rentabilité.png
├── Excel/
│   └── Pilotage_Financier_Ngroup.xlsx
├── PowerBI/
│   └── Dashboard_CA_Rentabilite.pbix
└── Documentation/
    ├── Guide_Complet.pdf
    ├── Formules_DAX.txt
    └── Analyses_Business.md
```

---

## Auteur

**Boubacar Nikiema** — Data Analyst & Consultant BI

Spécialisé en dashboards financiers, analytics Sales & Supply Chain et pilotage PME
avec Power BI, SQL, Python et Excel. Basé au Maroc, j'interviens auprès d'entreprises
en Afrique et en Europe francophone.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-boubacar--nikiema-blue?logo=linkedin)](https://linkedin.com/in/boubacar-nikiema)
[![YouTube](https://img.shields.io/badge/YouTube-BoubacarDataAnalyst-red?logo=youtube)](https://youtube.com/@BoubacarDataAnalyst)
[![Email](https://img.shields.io/badge/Email-nikiemaboubacar%40gmail.com-gray?logo=gmail)](mailto:nikiemaboubacar@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-data.ngroupmediadigital.com-green)](https://data.ngroupmediadigital.com)

---

*Données simulées à des fins pédagogiques · Code : MIT License*
