# 🏡 Pricing & Market Intelligence Immobilier — DVF 2025

> Transformer des données brutes en intelligence de marché : ETL, analyse exploratoire, modélisation prédictive et détection d’opportunités.

---

## 🎯 Objectif du projet

Dans ce projet, je construis une **chaîne de traitement data complète** à partir des données publiques DVF (Demandes de Valeurs Foncières).

Mon objectif est double :
- 📊 Comprendre les **dynamiques du marché immobilier français**
- 🤖 Construire un **modèle capable d’estimer le prix d’un bien**
- 🎯 Identifier des **opportunités d’investissement sous-évaluées**

---

## 📦 Dataset

- **Source** : data.gouv.fr (DVF 2025)
- **Périmètre** : France métropolitaine
- **Volume initial** : 500 000 lignes (échantillon)
- **Données finales exploitées** : ~140 000 transactions

### ⚠️ Particularités du dataset
- Forte présence de **dépendances** (garages, caves)
- ~40% de valeurs manquantes sur certaines colonnes
- Distribution des prix **très asymétrique**

---

## 🧱 Architecture du projet

Le projet suit une logique Data complète :


---

## ⚙️ Stack technique

- **Python**
- **Pandas / NumPy**
- **Matplotlib / Seaborn**
- **Scikit-learn**
- **Google Colab**
- **Joblib (sauvegarde modèle)**

---

## 🔍 Étapes du projet

### 1. 📥 Chargement & Setup

- Import des librairies
- Chargement du dataset DVF
- Nettoyage des noms de colonnes
- Conversion des types

---

### 2. 🔎 Data Profiling

Avant toute transformation, j’analyse :

- Les valeurs manquantes
- Les types de biens
- Les distributions
- Les anomalies

👉 Insight clé :
> Les dépendances représentent une part majoritaire du dataset → elles doivent être exclues.

---

### 3. 🧹 ETL & Nettoyage

Je construis un dataset propre avec des règles métier claires :

- Filtrage :
  - Maisons & Appartements uniquement
- Suppression des valeurs incohérentes :
  - Prix < 5 000 €
  - Surface < 5 m²
- Création de variables :
  - `prix_m2`
- Gestion des outliers :
  - Filtrage entre 200 et 30 000 €/m²

👉 Résultat :
- Dataset cohérent et exploitable
- ~28% de rétention (logique vu la structure DVF)

---

### 4. 🧱 Modélisation en Star Schema

Je restructure les données pour un usage BI :

- `fact_pricing`
- `dim_date`
- `dim_location`
- `dim_property`

👉 Objectif :
- Optimiser l’analyse
- Faciliter l’intégration dans Power BI / Tableau

---

### 5. 📊 Analyse Exploratoire (EDA)

#### 🔹 Distribution des prix

- Distribution asymétrique (queue à droite)
- Pic entre **1 500 et 3 500 €/m²**

#### 🔹 Maisons vs Appartements

- Appartements plus chers (~+66%)
- Effet principalement lié à la localisation

#### 🔹 Géographie

- Forte disparité selon les communes
- Marchés premium identifiés (Côte d’Azur, etc.)

👉 Insight global :
> Le prix dépend fortement de la localisation + surface + type de bien

---

### 6. 🤖 Modélisation Machine Learning

#### Modèle utilisé :
- **Random Forest Regressor**

#### Features principales :
- Surface
- Nombre de pièces
- Localisation
- Type de bien

#### Performance :
- **R² = 0.718**
- **RMSE ≈ 208 000 €**

👉 Interprétation :
> Le modèle explique ~72% de la variance des prix → performance solide pour un problème immobilier

---

### 7. 💰 Estimation de prix

Je développe une fonction permettant :

- D’estimer le prix d’un bien
- Avec fallback si certaines données sont absentes

👉 Utilisation possible :
- Simulation d’achat
- Outil d’aide à la décision

---

### 8. 🎯 Détection d’opportunités

Je mets en place un scoring basé sur un **z-score local** :

- Comparaison d’un bien avec son marché local
- Identification des biens sous-évalués

👉 Résultat :
- ~5 598 opportunités détectées
- ≈ 4% du marché

---

## 📈 Résultats clés

- ✔ Dataset propre et structuré
- ✔ Modèle prédictif performant
- ✔ Moteur d’estimation fonctionnel
- ✔ Détection d’opportunités réelle

---

## 🚀 Améliorations possibles

- Ajouter des données externes :
  - Revenus par commune
  - Données socio-économiques
- Utiliser des modèles avancés :
  - XGBoost / LightGBM
- Déployer une API (FastAPI)
- Créer un dashboard interactif (Streamlit)

---

## 🧠 Ce que j’ai appris

À travers ce projet, j’ai consolidé :

- La construction d’un pipeline data complet
- Le nettoyage de données réelles (et imparfaites)
- L’analyse exploratoire avancée
- La modélisation prédictive
- La logique métier immobilière

<br>

## Auteure

**Oumaima Cheour**
