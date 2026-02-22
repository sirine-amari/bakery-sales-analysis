# bakery-sales-analysis
Ce projet consiste à analyser, modéliser et surveiller les ventes journalières d’une boulangerie française à l’aide d’une pipeline complète de data science.

Pipeline mise en place :
Exploratory Data Analysis → Feature Engineering → Forecasting → Anomaly Detection

---

## 1. Objectif du projet

L’objectif est de :

- Comprendre la dynamique des ventes journalières
- Construire un modèle de prévision
- Mesurer l’écart entre les ventes réelles et prédites
- Détecter automatiquement des anomalies

Ce type d’approche est utilisé en entreprise pour le monitoring de performance, la détection d’incidents opérationnels et l’optimisation des décisions.

---

## 2. Structure du projet
```
bakery-sales-analysis/
│
├── data/
│ ├── raw/
│ │ └── daily_sales_french_bakery.csv
│ │
│ └── processed/
│ ├── features_daily_sales.csv
│ ├── forecast_results.csv
│ └── anomalies_detected.csv (optionnel)
│
├── notebooks/
│ ├── 01_eda.ipynb
│ ├── 02_feature_engineering.ipynb
│ ├── 03_forecasting.ipynb
│ └── 04_anomaly_detection.ipynb
│
├── README.md
└── LICENSE
```

---

## 3. Exploratory Data Analysis (EDA)

Analyse des ventes journalières :

- Distribution des ventes
- Identification de la tendance
- Analyse de la saisonnalité hebdomadaire
- Moyennes mobiles pour visualiser la tendance long terme

Notebook : `01_eda.ipynb`

---

## 4. Feature Engineering

Création de variables explicatives :

- Jour de la semaine
- Mois
- Jour du mois
- Numéro de semaine
- Indicateur weekend
- Lags (1, 7, 14 jours)
- Moyennes mobiles (7 et 30 jours)
- Écart-type mobile

Les features sont sauvegardées dans :

`data/processed/features_daily_sales.csv`

Notebook : `02_feature_engineering.ipynb`

---

## 5. Forecasting

Modélisation des ventes à l’aide d’un modèle supervisé.

Étapes :
- Séparation temporelle train/test
- Entraînement du modèle
- Prédictions sur la période test
- Calcul des résidus

Sortie :

`data/processed/forecast_results.csv`

Colonnes principales :
- ds
- y_true
- y_pred
- residual

Notebook : `03_forecasting.ipynb`

---

## 6. Détection d’anomalies

Méthode :

- Calcul du Z-score des résidus
- Détection des observations telles que |Z| > 3

Cette approche permet d’identifier des variations non expliquées par la saisonnalité ou la tendance.

Notebook : `04_anomaly_detection.ipynb`

---

## 7. Méthodologie

1. Nettoyage et structuration des données
2. Création de variables temporelles
3. Modélisation supervisée
4. Analyse des résidus
5. Détection statistique d’événements atypiques

Pipeline cohérente et reproductible.

---

## 8. Technologies utilisées

- Python 3
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Git / GitHub

---

## 9. Reproduire le projet

Créer un environnement virtuel :

python -m venv .venv
source .venv/bin/activate


Installer les dépendances :

pip install pandas numpy matplotlib scikit-learn


Exécuter les notebooks dans l’ordre :

1. 01_eda.ipynb  
2. 02_feature_engineering.ipynb  
3. 03_forecasting.ipynb  
4. 04_anomaly_detection.ipynb  

---

## 10. Résultats

- Modèle capable de prédire la dynamique des ventes journalières
- Identification automatique de journées atypiques
- Base exploitable pour un système de monitoring opérationnel

---

## Auteur

Sirine Amari  
