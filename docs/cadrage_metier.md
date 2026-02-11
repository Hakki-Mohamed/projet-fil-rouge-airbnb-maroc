# 🧠 Cadrage Métier – Projet Fil Rouge

# 📌 1. Contexte général

Le marché de la location courte durée via Airbnb connaît une forte croissance
dans les grandes destinations européennes.

Madrid et Barcelona sont deux villes majeures du tourisme en Espagne,
présentant des dynamiques économiques, touristiques et réglementaires différentes.

Comprendre les différences structurelles entre ces deux marchés permet
d’orienter les décisions d’investissement et de stratégie tarifaire.

---

# 🎯 2. Problématique métier

Comment comparer la structure du marché Airbnb entre Madrid et Barcelona
afin d’identifier :

- Les différences de niveau de prix
- Les écarts de segmentation (types de logements)
- La dispersion des prix
- La concentration de l’offre
- Les opportunités d’investissement

---

# 👤 3. Cible du projet

Ce projet s’adresse principalement à :

- Investisseurs immobiliers
- Analysts marché
- Consultants en stratégie touristique
- Propriétaires Airbnb souhaitant optimiser leur positionnement

---

# 🧩 4. Objectifs analytiques

Les objectifs sont les suivants :

1. Comparer le prix moyen et médian entre Madrid et Barcelona
2. Analyser la distribution des prix
3. Étudier la segmentation par type de logement :
   - Entire home / apartment
   - Private room
   - Hotel room
   - Shared room
4. Identifier la dispersion et la présence de logements premium
5. Comparer le volume d’offres par ville
6. Analyser les indicateurs d’activité :
   - Nombre de reviews
   - Disponibilité annuelle

---

# 📊 5. Indicateurs clés (KPI)

## Indicateurs prix

- Prix moyen par ville
- Prix médian par ville
- Prix moyen par type de logement
- 99e percentile des prix
- Écart-type des prix

## Indicateurs d’offre

- Nombre total de logements par ville
- Répartition par type de logement
- Part de marché par type

## Indicateurs d’activité

- Nombre moyen de reviews
- Disponibilité moyenne (availability_365)

---

# 📦 6. Sources de données

Les données proviennent de la plateforme :

Inside Airbnb
http://insideairbnb.com/get-the-data/

Villes étudiées :

- Madrid
- Barcelona

Fichiers utilisés :

- listings.csv
- reviews.csv
- calendar.csv.gz
- neighbourhoods.csv

Date de téléchargement :
02/11/2026

---

# 🏗 7. Architecture Data

Pipeline simplifié :

1. Téléchargement des données brutes
2. Stockage dans data/raw
3. Nettoyage :
   - Suppression des valeurs manquantes (price)
   - Suppression des outliers (99e percentile)
4. Fusion des datasets Madrid + Barcelona
5. Analyse exploratoire (EDA)
6. Calcul des KPI
7. Visualisation comparative

Outils utilisés :

- Python
- Pandas
- Numpy
- Seaborn
- Matplotlib
- Jupyter Notebook

---

# 📈 8. Hypothèses initiales

H1 : Barcelona présente un prix moyen supérieur à Madrid.
H2 : La dispersion des prix est plus élevée à Barcelona.
H3 : La proportion de logements premium est plus importante à Barcelona.
H4 : Madrid présente un volume d’offre plus important.

Ces hypothèses seront validées ou infirmées par l’analyse statistique.

---

# 🎯 9. Résultat attendu

À l’issue du projet, un dashboard décisionnel permettra :

- De comparer les deux marchés
- D’identifier les différences structurelles
- D’aider à la prise de décision stratégique
