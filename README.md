# Credit Card Fraud Detection – Data Preparation Pipeline

## Contexte et objectif
Ce projet s’inscrit dans le cadre du cours *IFM30542 – Initiation à l’intelligence artificielle* (Hiver 2026).
L’objectif est de concevoir un pipeline complet de préparation de données pour un problème réel de
détection de fraude par carte bancaire, en appliquant les bonnes pratiques de data science et de
machine learning.

Le projet met l’accent sur la compréhension des données, leur transformation, la gestion du
déséquilibre des classes et la livraison d’un jeu de données prêt pour l’apprentissage automatique.

---

## Données
- *Dataset* : Credit Card Fraud Detection (Kaggle)
- *Format* : CSV
- *Taille* : ~284 000 transactions, 31 variables
- *Description* :
  - Variables V1 à V28 : variables anonymisées issues d’une transformation PCA
  - Time : temps écoulé depuis la première transaction
  - Amount : montant de la transaction
  - Class : variable cible (0 = transaction normale, 1 = fraude)

⚠️ Le dataset n’est pas versionné dans ce dépôt conformément aux bonnes pratiques Git.
Seul le code permettant de le charger et de le traiter est fourni.

---

## Méthodologie
Le projet suit les étapes suivantes :

1. *Analyse initiale du problème*
   - Compréhension du contexte de fraude
   - Identification du type de tâche (classification supervisée)

2. *Exploration et diagnostic des données (EDA)*
   - Statistiques descriptives
   - Analyse des distributions et des asymétries
   - Visualisation du déséquilibre des classes
   - Identification des défis liés aux données

3. *Préparation et transformations*
   - Transformation logarithmique de la variable Amount
   - Feature engineering temporel à partir de la variable Time
   - Conservation des variables PCA sans modification

4. *Gestion du déséquilibre des classes*
   - Analyse de l’impact du déséquilibre
   - Préparation des données pour des techniques de rééquilibrage

5. *Validation du jeu de données final*
   - Dataset propre, transformé et prêt pour l’apprentissage automatique

---

## Résultats clés
- Mise en évidence d’un *déséquilibre extrême* de la variable cible
- Identification d’une *forte asymétrie* sur la variable Amount
- Justification des transformations appliquées
- Préparation d’un dataset robuste pour la modélisation

---

## Technologies utilisées
- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook
- Git & GitHub

---

## Auteur
- Nom : Cabrel
- GitHub : https://github.com/Cabrel1701
- Cours : IFM30542 – Initiation à l’intelligence artificielle