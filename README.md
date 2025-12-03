# 🌍 Analyse et Prédiction du Bonheur Mondial (World Happiness Report 2016)

## 📌 Contexte du Projet

Ce projet a été réalisé dans le cadre du module **"Data Science & Machine Learning"** et vise à évaluer la capacité à gérer le cycle de vie complet d'un projet de Machine Learning.

* **Thématique :** Société & Politique (Transformations Sociétales).
* **Problématique :** Tâche de **Régression**. Prédire le `Happiness Score` des pays en 2016.

## 💾 Dataset et Variables Clés

| Nom de la variable | Type | Description | Rôle |
| :--- | :--- | :--- | :--- |
| **Happiness Score** | Numérique | Score composite de bonheur pour le pays. | **TARGET (CIBLE)** |
| Economy (GDP) | Numérique | Contribution du PIB par habitant. | Feature |
| Health (Life Expectancy) | Numérique | Contribution de l'espérance de vie en bonne santé. | Feature |
| Family | Numérique | Contribution du soutien social. | Feature |

---

## 🛠️ Méthodologie Technique

Le projet a été implémenté en Python via un **Notebook Jupyter** (`CC_K.ipynb`), en respectant les étapes de Pré-traitement, EDA, et Modélisation.

### 1. Pré-traitement et Nettoyage

* **Sélection :** 6 features clés (GDP, Family, Health, Freedom, Generosity, Trust) ont été sélectionnées.
* **Normalisation :** Les features ont été **Standardisées** (`StandardScaler`) pour assurer l'équité des échelles avant la modélisation.
* **Split :** Division en ensembles d'entraînement (80%) et de test (20%).

### 2. Analyse Exploratoire des Données (EDA)

L'EDA a confirmé les relations clés, justifiant le choix des modèles.

#### A. Corrélation

La Matrice de Corrélation révèle l'influence des facteurs économiques et sanitaires.

[Image of Carte de chaleur des corrélations entre le Score de Bonheur et les facteurs socio-économiques]

> **Observation :** Les facteurs **Economy (GDP)** ($\approx 0.79$) et **Health (Life Expectancy)** ($\approx 0.76$) présentent la corrélation la plus forte avec le Score de Bonheur.

#### B. Distribution et Relations

L'analyse des distributions et des nuages de points confirme une relation positive et linéaire marquée entre le PIB et le Score de Bonheur.

[Image of Nuage de points illustrant la relation positive entre le PIB par habitant et le Score de Bonheur]

---

## 🚀 Modélisation et Résultats

### 1. Comparaison des Modèles

| Modèle | Score $R^2$ Moyen (Cross-Validation) |
| :--- | :--- |
| Régression Linéaire | 0.7364 |
| Forêt Aléatoire (Random Forest) | 0.7328 |
| SVR (Régresseur à Vecteur de Support) | 0.7322 |

> **Justification :** Le **Random Forest** a été choisi pour l'optimisation en raison de sa capacité à capturer les **relations non linéaires** complexes.

### 2. Évaluation Finale

Le modèle de **Random Forest** optimisé via `GridSearchCV` a été évalué sur l'ensemble de test.

| Métrique | Résultat Final (Test Set) | Interprétation |
| :--- | :--- | :--- |
| **Score $R^2$** | **0.8194** | Le modèle explique 82\% de la variance du Score de Bonheur. |
| **RMSE** | **0.4844** | L'erreur moyenne de prédiction est de seulement
