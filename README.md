# Data Quality & Data Pipeline Monitoring (Finance)

## Installation et setup

1. Cloner le projet :
```bash
git clone https://github.com/CarnageM-10/data-quality-finance.git


Projet Data Engineering — Novembre 2025 / Janvier 2026

## Objectif

Structurer et fiabiliser des flux de données financières et RH :
collecter des données multi-sources, modéliser une base relationnelle,
appliquer des règles de qualité, et produire des indicateurs de pilotage.

---

## Arborescence
```
data_quality_finance/
├── data/
│   ├── transactions.csv       # 6,3M transactions bancaires (PaySim dataset)
│   └── employes.csv           # 49 653 lignes historique RH (MFG10 dataset)
├── notebooks/
│   ├── 01_generate_data.ipynb # Chargement et exploration initiale des datasets
│   ├── 02_nettoyage.ipynb     # Nettoyage et traitement qualité (Pandas)
│   ├── 03_modélisation.ipynb  # Modélisation BDD relationnelle (SQLite + DBeaver)
│   ├── 04_sql.ipynb           # Transformations et requêtes SQL avancées
│   └── 05_qualite_kpi.ipynb   # Règles qualité, indicateurs et documentation
├── outputs/
│   └── rapport_qualite.csv    # Rapport automatique généré en étape 5
└── README.md
```

---

## Datasets

### transactions.csv — PaySim (simulation fraude bancaire)
- Source : Kaggle / PaySim Synthetic Dataset
- Lignes : 6 362 620
- Colonnes clés : `step`, `type`, `amount`, `nameOrig`, `nameDest`, `isFraud`
- Usage : simulation de transactions financières avec détection de fraude

### employes.csv — MFG10 (historique RH)
- Source : Kaggle / MFG10YoungPeopleDataset
- Lignes : 49 653 (historique annuel par employé)
- Colonnes clés : `EmployeeID`, `department_name`, `STATUS`, `termreason_desc`
- Usage : analyse des départs, masse salariale, pilotage RH

---

## Stack technique

- Python 3.x — Pandas, NumPy
- SQL — SQLite
- DBeaver — modélisation et exécution de requêtes
- Git — versioning du projet

---

## Étapes du projet

1. **Chargement** — exploration initiale des deux sources (`01_generate_data.ipynb`)
2. **Nettoyage** — gestion des doublons, valeurs nulles, types, outliers (`02_nettoyage.ipynb`)
3. **Modélisation** — schéma étoile, tables faits/dimensions, clés étrangères (`03_modélisation.ipynb`)
4. **Transformation SQL** — agrégations, jointures, vues (`04_sql.ipynb`)
5. **Qualité & KPI** — règles de contrôle, rapport automatique, indicateurs de pilotage (`05_qualite_kpi.ipynb`)
