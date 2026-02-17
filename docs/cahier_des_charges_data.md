# Cahier des Charges

## Projet Fil Rouge – Solution Data de bout en bout

### Analyse comparative du marché Airbnb : Madrid vs Barcelona

---

## 1. Contexte métier

Le marché de la location courte durée via Airbnb constitue un secteur stratégique dans les grandes métropoles européennes. Les décisions d’investissement immobilier dans ce domaine reposent sur l’analyse des prix, de la segmentation des logements et de la dynamique de l’offre et de la demande.

Madrid et Barcelona figurent parmi les principales destinations touristiques en Espagne. Toutefois, les différences structurelles entre ces deux marchés ne sont pas toujours clairement établies d’un point de vue analytique.

Dans ce contexte, il est nécessaire de concevoir une solution data complète permettant d’analyser et de comparer objectivement ces deux marchés afin de soutenir la prise de décision d’un investisseur ou d’un analyste marché.

---

## 2. Problématique analytique

La problématique centrale est la suivante :

Existe-t-il une différence significative entre les prix des logements Airbnb à Madrid et à Barcelona ?

Sous-questions :

* Quelle est la moyenne et la médiane des prix dans chaque ville ?
* Comment se distribuent les prix dans chaque marché ?
* Le type de logement influence-t-il significativement le prix ?
* La différence observée est-elle statistiquement significative ?

---

## 3. Objectifs du projet

### 3.1 Objectif principal

Concevoir une solution data complète permettant de collecter, nettoyer, modéliser, analyser et restituer les données Airbnb afin de comparer les marchés de Madrid et Barcelona.

### 3.2 Objectifs secondaires

* Automatiser l’import et la fusion des données.
* Nettoyer les valeurs manquantes et aberrantes.
* Structurer un dataset analytique exploitable.
* Concevoir une base de données analytique (SQLite).
* Construire des indicateurs métiers fiables.
* Valider les résultats par analyse statistique.
* Produire une restitution orientée décisionnel (dashboard).

---

## 4. Indicateurs clés (KPI)

Les indicateurs retenus sont :

* Prix moyen par ville.
* Prix médian par ville.
* Distribution des prix.
* Nombre total de logements par ville.
* Prix moyen par type de logement.
* Disponibilité annuelle moyenne.
* Test statistique de comparaison des moyennes (t-test).

---

## 5. Sources de données

### 5.1 Source principale

Plateforme : Inside Airbnb
Type : Fichiers CSV (Open Data)

### 5.2 Villes étudiées

* Madrid
* Barcelona

### 5.3 Fichiers utilisés par ville

* listings.csv
* calendar.csv
* reviews.csv
* neighbourhoods.csv

Date de téléchargement : 02/11/2026

Les datasets bruts sont stockés dans le dossier `data/raw/`.

---

## 6. Architecture Data et Pipeline

Le pipeline mis en place comprend les étapes suivantes :

1. Import des données brutes (CSV).
2. Fusion des datasets Madrid et Barcelona.
3. Nettoyage des valeurs manquantes (suppression des prix manquants).
4. Suppression des valeurs extrêmes via le 99e percentile.
5. Création d’un dataset nettoyé (`listings_clean.csv`).
6. Analyse exploratoire des données (EDA).
7. Validation statistique (t-test).
8. Création d’une base de données SQLite.
9. Modélisation en schéma en étoile :
   * fact\_listings
   * dim\_city
   * dim\_room\_type
10. Calcul des KPI en SQL.
11. Préparation des données pour la visualisation décisionnelle.

---

## 7. Nettoyage et préparation des données

Les actions réalisées sont les suivantes :

* Suppression des logements sans prix.
* Suppression de la colonne `license` fortement incomplète.
* Élimination des valeurs aberrantes via le 99e percentile afin de limiter l’impact des extrêmes sur les moyennes.
* Vérification et correction des types de données.
* Création d’une variable `city` pour distinguer les deux marchés.
* Export du dataset nettoyé vers `data/processed/listings_clean.csv`.

Ce traitement garantit la cohérence et la fiabilité des analyses réalisées.

---

## 8. Analyse statistique

### 8.1 Hypothèses testées

H0 : Il n’existe pas de différence significative entre les prix moyens des deux villes.
H1 : Il existe une différence significative entre les prix moyens des deux villes.

### 8.2 Méthode utilisée

Test t de Student pour échantillons indépendants (Welch).

### 8.3 Résultat

La p-value obtenue est inférieure au seuil de 0,05, ce qui conduit au rejet de l’hypothèse nulle.

Il existe donc une différence statistiquement significative entre les prix moyens à Madrid et à Barcelona.
Barcelona présente un niveau de prix moyen plus élevé.

---

## 9. Livrables du projet

### 9.1 Repository GitHub structuré

Le repository comprend :

* `data/raw/` – données brutes
* `data/processed/` – dataset nettoyé et exports KPI
* `notebooks/01_listings_merge_v2.ipynb` – fusion et préparation
* `notebooks/02_extraction_eda_v2.ipynb` – EDA et test statistique
* `notebooks/03_database_modeling.ipynb` – création base SQLite
* `notebooks/04_data_model_star_schema.ipynb` – schéma en étoile
* `notebooks/05_sql_kpis_star_schema.ipynb` – KPI SQL
* `docs/` – documentation projet
* `README.md` – description générale

### 9.2 Dataset nettoyé

Fichier :
`data/processed/listings_clean.csv`

Ce fichier constitue la base analytique principale du projet.

### 9.3 Dashboard décisionnel

Un dashboard interactif sera développé afin de présenter :

* Les KPI principaux.
* Les comparaisons entre villes.
* La segmentation par type de logement.
* Les recommandations métier.

---

## 10. Contraintes du projet

* Utilisation de données open source.
* Travail individuel.
* Délai de soumission : 30/03/2026.
* Objectif pédagogique : démontrer la maîtrise complète du cycle de vie de la donnée.
