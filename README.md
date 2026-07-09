# Walmart - Prédiction des Ventes Hebdomadaires

> *Construire et comparer plusieurs modèles de Machine Learning supervisé (linéaires et à base d'arbres) pour estimer les ventes hebdomadaires des magasins Walmart*

[![Python](https://img.shields.io/badge/Python-3.10-3776AB?logo=python)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn)](https://scikit-learn.org/)

---

##  Objectif

Le service marketing de Walmart souhaite un modèle capable de **prédire les ventes hebdomadaires** par magasin afin de mieux comprendre l'influence des indicateurs économiques (CPI, chômage, prix du carburant) et d'anticiper les pics de ventes.

---

##  Résultats

| Modèle | R² Test |
|---|---|
| **Régression Linéaire ** | **0.9322** |
| Lasso (α=1) | 0.9321 |
| Gradient Boosting | 0.9321 |
| Lasso (α=100, optimisé) | 0.9315 |
| Ridge (α=0.1, optimisé) | 0.9277 |
| Ridge (α=1) | 0.8678 |
| Random Forest | 0.8119 |

> **Résultat notable** : sur ce dataset (150 observations), la **régression linéaire** reste le meilleur modèle. Le **Random Forest** sur-apprend nettement (Train R²=0.945 vs Test R²=0.812) — trop de paramètres pour trop peu de données. Le **Gradient Boosting** s'en sort mieux mais n'apporte aucun gain par rapport aux modèles linéaires ici. **Leçon principale** : plus de complexité n'est pas toujours synonyme de meilleure performance.

---

##  Structure du projet

```
walmart-sales-prediction/
├── data/
│   └── Walmart_Store_sales.csv       # 150 observations, 45 magasins
├── notebooks/
│   └── Walmart_ML_Projet.ipynb       # EDA, prétraitement, modélisation (5 modèles comparés)
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Features utilisées

| Feature | Description |
|---|---|
| `Store` | Identifiant du magasin |
| `Date` | Semaine de vente (transformée en Year/Month/Day/DayOfWeek) |
| `Holiday_Flag` | Semaine de vacances / fêtes |
| `Temperature` | Température moyenne (°F) |
| `Fuel_Price` | Prix du carburant ($/gallon) |
| `CPI` | Indice des prix à la consommation |
| `Unemployment` | Taux de chômage local |

---

##  Insights clés

- **150 observations** réparties sur **45 magasins**
- Le **numéro du magasin** est la variable la plus influente sur les ventes prédites
- La régularisation (Ridge/Lasso) n'apporte pas de gain significatif sur ce dataset, déjà peu bruité
- Les modèles d'ensemble (Random Forest, Gradient Boosting) ne surpassent pas les modèles linéaires ici — le dataset est trop petit pour exploiter leur capacité à capturer des relations non-linéaires complexes sans sur-apprendre

---

##  Installation

```bash
git clone https://github.com/MartialBayom/walmart-sales-prediction.git
cd walmart-sales-prediction
pip install -r requirements.txt
jupyter notebook notebooks/Walmart_ML_Projet.ipynb
```

---

##  Auteur

| | Nom | Rôle |
|---|---|---|
|  | **Martial BAYOM** | Data Science |

Projet réalisé dans le cadre de la **certification Jedha AI School** (RNCP Niveau 6)

---

##  Sources

| Dataset | Lien |
|---|---|
| Walmart Store Sales | [Kaggle](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting) |
