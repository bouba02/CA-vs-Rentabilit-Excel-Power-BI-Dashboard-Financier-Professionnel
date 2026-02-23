# 📊 Dashboard CA vs Rentabilité | Excel + Power BI

**Analyse financière complète avec visualisations professionnelles**

> Vous faites du chiffre d'affaires... mais gagnez-vous vraiment de l'argent ? 🤔

---

## 📋 Vue d'ensemble

Ce projet présente un **dashboard financier professionnel** qui analyse 24 mois de données réelles (2 079 000 MAD de CA) pour identifier où va chaque dirham et prendre des décisions basées sur la data.

**[Regarder la vidéo complète sur YouTube →](https://youtu.be/AUYo3agdDWY)**

### 🎯 Objectif

Transformer des données brutes en **insights business actionnables** en distinguant clairement:
- **Chiffre d'Affaires** (l'argent qui ENTRE)
- **Rentabilité** (l'argent qui RESTE)

### 🔴 Cas d'Étude Principal

**Juillet 2024 — Mois Catastrophe**
- CA: 48 000 MAD (-54% vs Janvier)
- Coûts Variables: 40 000 MAD (campagne marketing massive)
- Bénéfice Net: **-7 800 MAD** (PERTE)
- Marge Nette: **-16.2%** 🚨

**vs Janvier 2024 — Excellent Mois**
- CA: 105 000 MAD
- Coûts Variables: 2 300 MAD
- Bénéfice Net: 86 900 MAD
- Marge Nette: **82.8%** ⭐

---

## 📊 Données Analysées

| Métrique | Valeur |
|----------|--------|
| **CA Total** | 2 079 000 MAD |
| **Bénéfice Net** | 1 590 717 MAD |
| **Marge Globale** | 76.5% |
| **Période** | 24 mois (Jan 2023 - Déc 2024) |
| **Lignes de données** | 233 (126 ventes + 107 dépenses) |
| **Services** | 4 (Shooting Photo, Montage Vidéo, Production, Design) |

---

## 🎓 Compétences Acquises

✅ Modélisation financière Excel  
✅ ETL Power BI (Extract, Transform, Load)  
✅ DAX avancé (CALCULATE, DIVIDE, SWITCH, VAR)  
✅ Data visualization (Waterfall, KPIs, alertes conditionnelles)  
✅ Business Intelligence orientée décision  
✅ Analyse financière professionnelle  

---

## 📁 Structure des Fichiers

Copy
CA-vs-Rentabilite-Excel-Power-BI-Dashboard/ │ ├── Pilotage_Financier_Ngroup.xlsx # Fichier Excel complet │ ├── Onglet "Parametres" # Configuration globale │ ├── Onglet "Ventes" # 126 lignes de ventes │ ├── Onglet "Depenses" # 107 lignes de dépenses │ ├── Onglet "Dashboard_Excel" # Synthèse rapide │ └── Onglet "Cash_Flow" # Préparation Thème 3 │ ├── Dashboard CA vs Rentabilite.pbix # Dashboard Power BI complet │ ├── Dashboard CA vs Rentabilite.pdf # Export PDF du dashboard │ ├── Dashboard CA vs Rentabilite.png # Screenshot du dashboard │ ├── FORMULES_DAX_DOCUMENTEES.txt # Toutes les mesures DAX │ └── README.md # Ce fichier


---

## 🗂️ Contenu Excel Détaillé

### **Onglet 1 : PARAMETRES**
Configuration centralisée pour réutilisation

Devise: MAD
Année d'analyse: 2024
Seuil d'alerte cash: 20 000 MAD
TVA: 20%
Objectifs CA: 2 500 000 MAD
Objectifs Cash: 1 000 000 MAD

### **Onglet 2 : VENTES** (126 lignes)
Transactions réelles avec calculs automatiques

| Colonne | Exemple | Type |
|---------|---------|------|
| Date_Facture | 01/01/2024 | Date |
| Invoice_ID | INV-001 | Texte |
| Client | Client A | Texte |
| Produit | Shooting Photo | Texte |
| Quantité | 1 | Nombre |
| Prix_Unitaire | 5 000 | Nombre |
| Montant_HT | =E×F | **Formule** |
| TVA (20%) | =G×0.2 | **Formule** |
| Montant_TTC | =G+H | **Formule** |
| Date_Paiement_Prévue | 31/01/2024 | Date |
| Date_Paiement_Réelle | 28/01/2024 | Date |
| Statut_Paiement | Payé | Texte |

### **Onglet 3 : DEPENSES** (107 lignes)
Expenses avec classification fixe/variable

| Colonne | Exemple | Type |
|---------|---------|------|
| Date_Depense | 01/01/2024 | Date |
| Expense_ID | EXP-001 | Texte |
| Fournisseur | Fournisseur X | Texte |
| **Type_Cout** | **FIXE ou VARIABLE** | **Texte** |
| Catégorie | Loyer | Texte |
| Montant | 3 000 | Nombre |
| Date_Paiement | 05/01/2024 | Date |

**Coûts Fixes** (tombent chaque mois):
- Loyer: 3 000 MAD
- Salaires: 12 000 MAD
- Assurance: 800 MAD

**Coûts Variables** (dépendent de l'activité):
- Marketing: varie
- Matériel: varie
- Freelances: varie

### **Onglet 4 : DASHBOARD_EXCEL**
Synthèse rapide avec formules

CA Total = SUMIF(Ventes!G:G,">0") Coûts Variables = SUMIFS(Depenses!G:G, Depenses!D:D, "Variable") Coûts Fixes = SUMIFS(Depenses!G:G, Depenses!D:D, "Fixe") Marge Brute = CA Total - Coûts Variables Marge Brute % = Marge Brute / CA Total Bénéfice Net = Marge Brute - Coûts Fixes Marge Nette % = Bénéfice Net / CA Total


### **Onglet 5 : CASH_FLOW**
Préparé pour la vidéo Thème 3 (Cash Flow Management)

---

## 📊 Dashboard Power BI — Visuels Inclus

### **Haut de Page: 4 KPI Cards**
Vue immédiate des métriques clés

| Card | Valeur | Couleur |
|------|--------|---------|
| CA Total | 2 079 000 MAD | Bleu #4472C4 |
| Marge Brute % | 94.8% | Orange #EB601B |
| Bénéfice Net | 1 590 717 MAD | Vert #70AD47 |
| Marge Nette % | 76.5% | Gris foncé |

### **Deuxième Ligne: 2 Alertes Conditionnelles**

#### Alerte 1: Statut Marge
Marge Nette < 10% → 🔴 Fragile Marge Nette < 20% → 🟠 Correct Marge Nette < 30% → 🟡 Bon Marge Nette < 40% → 🟢 Très Bon Marge Nette ≥ 40% → ⭐ Excellent


#### Alerte 2: Coûts Variables
Ratio > 50% → 🔴 Coûts trop élevés Ratio > 30% → 🟠 À surveiller Ratio ≤ 30% → 🟢 Sous contrôle


### **Graphique 1: Évolution Temporelle (Ligne)**
Montre CA et Bénéfice mois par mois
- **Révèle**: Juillet 2024 en creux (anomalie identifiée)
- **Axe X**: Mois-Année (24 points)
- **Axe Y**: CA Total vs Bénéfice Net
- **Insight**: Corrélation CA ≠ Bénéfice

### **Graphique 2: Waterfall (Cascade Financière)**
Montre visuellement où part l'argent — **Le plus important**

📊 WATERFALL - Comme une rivière qui diminue

CA Total (2M) ↓ [-] Coûts Variables (71K) ↓ = Marge Brute (2M) ↓ [-] Coûts Fixes (379K) ↓ = Bénéfice Net (1.59M)


En 3 secondes, tu vois:
- Combien tu gagnes (CA)
- Combien tu dépenses (Coûts)
- Ce qui te reste (Bénéfice)

### **Graphique 3: Performance par Service (Barres)**
Classement des 4 services par rentabilité

Production Événementielle 858K ████████████████ Shooting Photo 668K ███████████ Montage Vidéo 257K █████ Design Graphique 256K █████


Permet de décider:
- ✅ Quel service développer
- ⚠️ Quel service optimiser
- ❌ Quel service arrêter

### **Filtres Interactifs (Slicers)**
Exploration dynamique du dashboard

- **Filtre Année**: 2023 | 2024
- **Filtre Mois**: Jan → Déc
- **Tous les visuels se mettent à jour instantanément**

**Exemple d'interaction**:
Clic sur Juillet
Toutes les cartes changent
Alertes s'affichent: 🔴 Fragile | 🔴 Coûts trop élevés
Waterfall révèle la catastrophe marketing
Décision: "Ne plus investir 40K en marketing"

---

## 🔧 Mesures DAX — Détaillées

### **7 KPIs Fondamentaux**

#### 1️⃣ CA_Total
```dax
CA_Total = SUM(Ventes[Montant_HT])
Signification: Somme de tous les montants hors taxes des ventes
Format: Nombre entier
Résultat: 2 079 000 MAD

2️⃣ Coûts_Variables
Coûts_Variables = 
CALCULATE(
    SUM(Depenses[Montant]),
    Depenses[Type_Cout] = "Variable"
)
Signification: Somme uniquement des dépenses marquées "Variable"
Exemple: Marketing, Matériel, Freelances
Résultat: 71 380 MAD

3️⃣ Coûts_Fixes
Coûts_Fixes = 
CALCULATE(
    SUM(Depenses[Montant]),
    Depenses[Type_Cout] = "Fixe"
)
Signification: Somme uniquement des dépenses marquées "Fixe"
Exemple: Loyer, Salaires, Assurance
Résultat: 379 200 MAD

4️⃣ Marge_Brute
Marge_Brute = [CA_Total] - [Coûts_Variables]
Signification: CA après avoir payé les coûts variables
Formule: CA - Coûts Variables
Résultat: 2 007 620 MAD

5️⃣ Marge_Brute_%
Marge_Brute_% = 
DIVIDE(
    [Marge_Brute], 
    [CA_Total], 
    0
)
Signification: Pourcentage de marge brute
Formule: Marge Brute / CA
Résultat: 94.8%
Note: DIVIDE évite erreurs si CA=0

6️⃣ Bénéfice_Net
Bénéfice_Net = [Marge_Brute] - [Coûts_Fixes]
Signification: Ce qui reste après TOUS les coûts
Formule: Marge Brute - Coûts Fixes
Résultat: 1 590 717 MAD
Critique: C'est le vrai profit

7️⃣ Marge_Nette_%
Marge_Nette_% = 
DIVIDE(
    [Bénéfice_Net], 
    [CA_Total], 
    0
)
Signification: Pourcentage de profit réel
Formule: Bénéfice Net / CA
Résultat: 76.5%
Interprétation: Pour 100 MAD gagnés, 76,50 MAD restent

2 Alertes Conditionnelles Avancées
🎯 Alerte 1: Statut_Marge
Statut_Marge = 
VAR Marge = [Marge_Nette_%]
RETURN
SWITCH(
    TRUE(),
    Marge < 0.10, "🔴 Fragile",
    Marge < 0.20, "🟠 Correct",
    Marge < 0.30, "🟡 Bon",
    Marge < 0.40, "🟢 Très Bon",
    "⭐ Excellent"
)
Logique:

Si Marge Nette < 10% → 🔴 DANGER (perte possible)
Si Marge Nette < 20% → 🟠 ATTENTION (fragile)
Si Marge Nette < 30% → 🟡 BON (acceptable)
Si Marge Nette < 40% → 🟢 TRÈS BON (solide)
Sinon → ⭐ EXCELLENT (optimal)
Exemple Juillet 2024: Marge = -16.2% → 🔴 Fragile

⚠️ Alerte 2: Alerte_Couts
Alerte_Couts = 
VAR Ratio = DIVIDE([Coûts_Variables], [CA_Total], 0)
RETURN
SWITCH(
    TRUE(),
    Ratio > 0.50, "🔴 Coûts trop élevés",
    Ratio > 0.30, "🟠 À surveiller",
    "🟢 Sous contrôle"
)
Logique:

Si Coûts Variables > 50% du CA → 🔴 DANGER
Si Coûts Variables > 30% du CA → 🟠 ATTENTION
Sinon → 🟢 OK
Exemple Juillet 2024: Coûts Variables = 83% du CA → 🔴 Trop élevés

💡 Key Insights & Analyses
Découverte 1: Juillet 2024 — Catastrophe Identifiée 🔴
Le Problème:

Campagne marketing massive lancée: 40 000 MAD
CA généré: 48 000 MAD seulement
Résultat: Perte de 7 800 MAD
Analyse Waterfall:

CA: 48K
  ├─ Coûts Variables: -40K (83% du CA!)
  ├─ Marge Brute: 8K
  ├─ Coûts Fixes: -15.8K
  └─ Bénéfice: -7.8K ❌
Alertes Levées:

Statut Marge: 🔴 Fragile (-16.2%)
Alerte Coûts: 🔴 Trop élevés (83%)
Action Recommandée:

❌ NE JAMAIS relancer une campagne similaire
✅ Analyser pourquoi le ROI était si mauvais
✅ Tester à petite échelle avant gros investissements
Découverte 2: Janvier 2024 — Modèle Idéal ⭐
Le Succès:

CA: 105 000 MAD
Coûts Variables: 2 300 MAD (2% du CA)
Bénéfice: 86 900 MAD
Analyse Waterfall:

CA: 105K
  ├─ Coûts Variables: -2.3K (2% du CA)
  ├─ Marge Brute: 102.7K
  ├─ Coûts Fixes: -15.8K
  └─ Bénéfice: 86.9K ✅
Alertes Levées:

Statut Marge: ⭐ Excellent (82.8%)
Alerte Coûts: 🟢 Sous contrôle (2%)
Action Recommandée:

✅ C'est la structure idéale à répliquer
✅ Maintenir CA autour de 100K/mois
✅ Garder marketing sous 3K sauf si ROI prouvé
Découverte 3: Business Solide Globalement 💚
Performance 24 mois:

Marge nette moyenne: 76.5%
Bénéfice: 1 590 717 MAD
Juillet est l'exception (pas la tendance)
Si on enlève Juillet:

23 mois sans juillet: Marge moyenne ≈ 80%
Business est TRÈS rentable
Conclusion:

✅ Système de base très sain
✅ Juste éviter les erreurs marketing comme juillet
✅ Peu d'optimisations nécessaires (déjà excellent)
🚀 Comment Utiliser Ce Projet
Option 1: Adapter à Votre Business ⭐ RECOMMANDÉ
Téléchargez Pilotage_Financier_Ngroup.xlsx
Supprimez les données exemple (conservez la structure)
Insérez vos propres données:
Onglet Ventes: Vos 12+ derniers mois de ventes
Onglet Depenses: Vos 12+ derniers mois de dépenses
Les formules Excel s'actualisent automatiquement
Importez dans Power BI
Visualisez votre rentabilité réelle
Option 2: Utiliser le Dashboard Power BI
Téléchargez Dashboard CA vs Rentabilite.pbix
Ouvrez dans Power BI Desktop
Accueil → Transformer les données
Remplacez les sources de données
Les visuels se mettent à jour instantanément
Option 3: Ajouter à Votre Portfolio
✅ Utilisez comme template pour entretiens
✅ Présentez en mission consulting
✅ Démontrez vos compétences Power BI + DAX
✅ Montrez la capacité à créer dashboards métier
📈 Cas d'Usage
✓ Entrepreneurs & PME: Piloter la rentabilité du business
✓ Data Analysts: Template professionnel pour portfolio
✓ Consultants BI: Dashboard client prêt à l'emploi
✓ Étudiants Finance: Comprendre P&L et rentabilité
✓ Freelance BI: Proposer dashboards financiers sur mesure
✓ Managers: Suivre la performance financière mensuelle

🎥 Vidéo Complète — YouTube
Regarder sur YouTube →

Durée: 43 minutes
Contenu: Étape par étape du concept au dashboard

Timestamps Détaillés
Timestamp	Sujet	Durée
00:00	Introduction: Le Problème des Entrepreneurs	1 min
01:00	PARTIE 1: Théorie (CA vs Rentabilité)	2 min
03:00	PARTIE 2: Présentation Fichier Excel	3 min
06:00	PARTIE 3: Import Power BI + Modèle	3 min 50s
09:50	PARTIE 4: Mesures DAX + Alertes	5 min 10s
15:00	PARTIE 5: Création Dashboard	23 min
38:00	PARTIE 6: Analyse & Interprétation	4 min 20s
42:20	Conclusion + Fichiers Gratuits	2 min 40s
🔜 Série "3 Dashboards Business"
Thème 1: CA vs Rentabilité (CETTE VIDÉO)
→ Identifier où va chaque euro
→ Détecter les mois déficitaires
→ Améliorer la rentabilité

Thème 2: Valorisation d'Entreprise
→ 4 méthodes de valorisation
→ Simulateur Excel interactif
→ Préparer une levée de fonds

Thème 3: Cash Flow Management
→ Trésorerie temps réel
→ Prévisions de cash
→ Gestion du working capital

🔧 Requirements
Outil	Version	Coût
Excel	2016+ ou Office 365	Gratuit/Abonnement
Power BI Desktop	Latest	GRATUIT
Windows ou Mac	10+ / 10.12+	-
Pas de dépendances externes
Aucune licence payante requise

📚 Ressources Complémentaires
Apprendre DAX
DAX Function Reference — Réference complète
DAX Studio — Debugger DAX
Microsoft Learn - DAX
Power BI
Power BI Documentation
Power BI Community Forums
Power BI Desktop Download
Excel
Excel Functions Guide
Excel Online Tutorials
Financial Analysis
Financial Statements Basics
P&L Analysis Guide
📄 License
Ce projet est libre d'utilisation pour:

✅ Projets personnels
✅ Projets professionnels
✅ Portfolios et démonstrations
✅ Adaptations et modifications
Attribution appréciée (mention du lien GitHub)

📞 Contact & Support
📧 Email: nikiemaboubacar@gmail.com
💼 LinkedIn: Boubacar Nikiema
🌐 Site: data.ngroupmediadigital.com
🐙 GitHub: github.com/bouba02

Besoin d'Aide?
❓ Questions: Ouvrez une Issue
💡 Suggestions: Fork le repo et proposez des améliorations
🐛 Bugs: Reportez avec description détaillée
📧 Collaborations: Contactez par email
🙏 Merci!
Merci d'utiliser ce dashboard!

Si ça vous aide:

⭐ Star ce repo
🍴 Fork pour vos adaptations
💬 Partagez vos résultats en commentaire YouTube
📢 Recommandez à votre réseau
📊 Statistiques du Projet
Métrique	Valeur
Lignes de données	233
Mesures DAX	9
Visuels Power BI	6+
Mois analysés	24
Services	4
Durée vidéo	43 min
Niveau complexité	Intermédiaire-Avancé


Ngroup Media & Digital | Data Analytics & Business Intelligence

Dernière mise à jour: Décembre 2024
Repository: github.com/bouba02/CA-vs-Rentabilite-Excel-Power-BI-Dashboard

🎓 Citation
Si vous utilisez ce projet dans un article ou projet professionnel, citez:

Nikiema, B. (2024). Dashboard CA vs Rentabilité - Excel + Power BI.
GitHub: github.com/bouba02/CA-vs-Rentabilite-Excel-Power-BI-Dashboard

Questions? Consultez la vidéo complète → https://youtu.be/AUYo3agdDWY 🎥
