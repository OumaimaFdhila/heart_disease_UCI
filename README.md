# 🩺 Heart Disease Diagnostic System

## 📝 Présentation du Projet

Les maladies cardiovasculaires sont la **première cause de mortalité dans le monde**. Ce projet vise à développer un système d'aide au diagnostic médical utilisant le Machine Learning pour prédire la présence d'une pathologie cardiaque chez un patient à partir de données cliniques.

L'objectif est de transformer des données brutes provenant de quatre centres hospitaliers mondiaux en un modèle de classification robuste capable d'identifier les patients à risque.

-----

## 📊 Jeu de Données

Les données proviennent du **UCI Machine Learning Repository** (Heart Disease Dataset).

  - **Nombre d'observations :** 920 patients.
  - **Nombre de variables :** 16 (14 prédictives).
  - **Sources :** Cleveland (USA), Budapest (Hongrie), Zurich (Suisse), Long Beach (USA).

### Variables Clés :

  * `age`, `sex`, `cp` (douleur thoracique), `trestbps` (tension), `chol` (cholestérol).
  * `thalch` (fréquence cardiaque max), `exang` (angine d'effort), `oldpeak`.
  * **Variable Cible (`num`) :** Diagnostic binaire (0 = Sain, 1 = Malade).

-----

## 🛠️ Pipeline de Data Science

### 1\. Prétraitement & Nettoyage

  * **Imputation :** Gestion des valeurs manquantes critiques (`ca`, `slope`, `thal`).
  * **Correction des anomalies :** Identification et traitement des valeurs aberrantes physiologiquement impossibles (`chol=0`, `trestbps=0`).
  * **Encodage :** Transformation des variables catégorielles (LabelEncoding).
  * **Standardisation :** Mise à l'échelle via `StandardScaler`.

### 2\. Analyse Exploratoire (EDA)

  * Détection des outliers via Boxplots.
  * Analyse des corrélations et matrices de chaleur.
  * Visualisation de la distribution des classes (malade vs sain).

### 3\. Sélection de Variables

  * Utilisation de la méthode **Backward Elimination** (Élimination descendante).
  * Test de significativité statistique ($\alpha = 0.05$) via des modèles Logit pour réduire le bruit et simplifier le protocole clinique.

### 4\. Modélisation & Optimisation

  * **Modèles testés :** Logistic Regression (L1/L2/ElasticNet), SVC, KNN, Decision Tree, Random Forest, XGBoost.
  * **Fine-Tuning :** Optimisation des hyperparamètres via `GridSearchCV` (5-fold Cross-Validation).

-----

## 🏆 Résultats Finaux

Le modèle final a été sélectionné pour sa robustesse et sa capacité à minimiser les faux négatifs.

| Métrique | Score |
| :--- | :--- |
| **Meilleur Modèle** | **XGBoost** |
| **ROC AUC Final** | **0.901** |
| **F1-Score** | **0.809** |
| **Amélioration ($\Delta$ AUC)** | **+0.021** |

-----

## 🚀 Installation et Utilisation

### Prérequis

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost statsmodels
```

### Exécution

1.  Clonez le dépôt :
    ```bash
    git clone https://github.com/OumaimaFdhila/heart_disease_UCI.git
    ```
2.  Lancez le notebook 

-----

## 📂 Structure du Dépôt

```text
├── data/               # Jeu de données brut et nettoyé
├── notebooks/          # Notebooks Jupyter (EDA, Modeling)
├── src/                # Scripts Python (Prepro, Utils)
├── README.md           # Documentation du projet
└── requirements.txt    # Liste des dépendances
```

-----

## 📌 Auteurs

  - **Fdhila Oumaima** *M1-ISI*

-----

*Ce projet a été réalisé dans le cadre d'un Master en Ingénierie des Systèmes Intelligents.*
