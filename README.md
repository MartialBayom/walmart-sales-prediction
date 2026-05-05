# 🛒 Walmart — Prédiction des Ventes Hebdomadaires

> *Construire un modèle de Machine Learning supervisé pour estimer les ventes hebdomadaires des magasins Walmart et comprendre l'influence des indicateurs économiques*

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org/)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-0194E2)](https://mlflow.org/)

---

## 🎯 Objectif

Le service marketing de Walmart souhaite un modèle capable de **prédire les ventes hebdomadaires** par magasin afin de mieux comprendre l'influence des indicateurs économiques (CPI, chômage, prix du carburant) et d'anticiper les pics de ventes.

---

## 📊 Résultats

| Modèle | RMSE | MAE | R² |
|---|---|---|---|
| Linear Regression | ~500k | ~350k | ~0.10 |
| Ridge / Lasso | ~490k | ~340k | ~0.12 |
| **Random Forest ⭐** | **~160k** | **~90k** | **~0.97** |
| Gradient Boosting | ~170k | ~100k | ~0.96 |

> Les semaines de fêtes (**IsHoliday**) augmentent les ventes de **+7%** en moyenne.

---

## 🗂️ Structure du projet

```
walmart/
├── data/
│   ├── train.csv                     # Données d'entraînement (421 570 lignes)
│   ├── test.csv
│   ├── stores.csv                    # Infos magasins (type, surface)
│   └── features.csv                  # Indicateurs économiques hebdomadaires
├── notebooks/
│   ├── 01_eda.ipynb                  # Analyse exploratoire
│   └── 02_modeling.ipynb             # Entraînement & évaluation
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🧠 Features utilisées

| Feature | Description |
|---|---|
| `Store` | Identifiant du magasin (1–45) |
| `Dept` | Département du magasin |
| `IsHoliday` | Semaine de vacances / fêtes |
| `Temperature` | Température moyenne (°F) |
| `Fuel_Price` | Prix du carburant ($/gallon) |
| `MarkDown1–5` | Promotions anonymisées |
| `CPI` | Indice des prix à la consommation |
| `Unemployment` | Taux de chômage local |
| `Type` | Type de magasin (A, B, C) |
| `Size` | Surface du magasin |

---

## 📈 Insights clés

- **45 magasins**, **99 départements**, données sur **143 semaines**
- Les magasins de **type A** génèrent **3× plus** de ventes que les types C
- Les semaines **Thanksgiving et Noël** représentent les pics les plus élevés
- Le **Random Forest** capture parfaitement les effets saisonniers

---

## ⚙️ Installation

```bash
git clone https://github.com/MartialBayom/walmart-sales-prediction.git
cd walmart-sales-prediction
pip install -r requirements.txt
jupyter notebook notebooks/01_eda.ipynb
```

---

## 👤 Auteur

| | Nom | Rôle |
|---|---|---|
| 🧑‍💻 | **Martial BAYOM** | Data Science |

Projet réalisé dans le cadre de la **certification Jedha AI School** (RNCP Niveau 6)

---

## 📂 Sources

| Dataset | Lien |
|---|---|
| Walmart Store Sales Forecasting | [Kaggle](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting) |
