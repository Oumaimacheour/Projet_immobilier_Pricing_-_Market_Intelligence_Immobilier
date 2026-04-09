# 🏡 Pricing & Market Intelligence Immobilier (DVF 2025)

## 🎯 Objectif

Ce projet vise à transformer les données brutes des Demandes de Valeurs Foncières (DVF 2025) en un outil d’analyse et d’aide à la décision pour le marché immobilier.

Il couvre l’ensemble de la chaîne de valeur de la donnée :
- nettoyage et transformation (ETL)
- structuration en schéma en étoile
- analyse exploratoire (EDA)
- modélisation prédictive (Machine Learning)
- détection d’opportunités d’investissement

---

## 📊 Données

Les données proviennent du jeu DVF (Demandes de Valeurs Foncières), qui recense les transactions immobilières en France.

Principales variables utilisées :
- `valeur_fonciere` (prix de vente)
- `surface_reelle_bati`
- `nombre_pieces_principales`
- `commune`
- `code_postal`
- `date_mutation`

---

## 🧹 ETL & Préparation des données

- Nettoyage et harmonisation des données
- Gestion des valeurs manquantes et aberrantes
- Conversion des types
- Création de la variable clé : **prix au m² (`prix_m2`)**

---

## 🧱 Modélisation des données (Star Schema)

Les données sont organisées selon un schéma en étoile :

- **Table de faits** : `fact_pricing`
- **Dimensions** :
  - `dim_date`
  - `dim_location`
  - `dim_property`

---

## 📊 Analyse exploratoire (EDA)

- Distribution des prix au m²
- Identification des communes les plus chères
- Analyse des corrélations
- Comparaison Maison vs Appartement
- Analyse géographique
- Évolution des prix

---

## 🤖 Modélisation prédictive

- Random Forest Regressor
- Variables : surface, pièces, commune
- Évaluation : R², RMSE

---

## 📦 Livrables

- `fact_pricing.csv`
- `dim_date.csv`
- `dim_location.csv`
- `dim_property.csv`
- `real_estate_model.joblib`
- `commune_encoder.joblib`
---

## 👩‍💻 Auteur

**Oumaima Cheour**
