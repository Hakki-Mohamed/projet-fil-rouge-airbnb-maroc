Projet Fil Rouge – Analyse Comparative du Marché Airbnb
Madrid vs Barcelona
Objectif du projet

Ce projet vise à concevoir une solution data complète de bout en bout afin de comparer le marché Airbnb entre Madrid et Barcelona.

L’analyse porte sur :

Les prix moyens et médians

La disponibilité annuelle

Les types de logements

Les différences statistiques entre les deux marchés

L’objectif final est d’aider à la prise de décision pour un investisseur ou un analyste marché.

Problématique métier

Existe-t-il une différence significative entre les prix Airbnb à Madrid et Barcelona ?

Quelle ville présente le positionnement le plus premium ?
Quelle ville offre le plus d’opportunités accessibles ?

Sources de données

Données issues de la plateforme Inside Airbnb :

listings.csv

calendar.csv

reviews.csv

neighbourhoods.csv

Villes étudiées :

Madrid

Barcelona

Date de téléchargement : 02/11/2026

Stack technique

Python

Pandas

NumPy

Matplotlib / Seaborn

SciPy (tests statistiques)

SQLite (base analytique)

Jupyter Notebook

Git / GitHub

Architecture Data
data/
 ├── raw/            → données brutes
 ├── processed/      → données nettoyées + base SQLite
notebooks/
 ├── 01_listings_merge.ipynb
 ├── 02_extraction_eda.ipynb
 ├── 03_database_modeling.ipynb
docs/
 ├── cadrage_metier.md
 ├── cahier_des_charges_data.md
 ├── sources.md

Pipeline Data

1️⃣ Fusion des listings Madrid & Barcelona
2️⃣ Nettoyage des valeurs manquantes
3️⃣ Suppression des outliers (99e percentile)
4️⃣ Analyse exploratoire (EDA)
5️⃣ Test statistique (T-test)
6️⃣ Création base SQLite
7️⃣ Calcul des KPI en SQL

KPI calculés

Prix moyen par ville

Médiane des prix

Nombre de logements

Prix moyen par type de logement

Corrélation simple prix vs disponibilité

Test statistique de comparaison des moyennes

Validation statistique

Un T-test a été réalisé afin de comparer les prix moyens.

Résultat :

p-value < 0.05

Différence statistiquement significative

Barcelona présente des prix moyens plus élevés que Madrid

Conclusion métier

Barcelona adopte un positionnement plus premium.
Madrid offre davantage d’opportunités pour un investissement à budget modéré.
