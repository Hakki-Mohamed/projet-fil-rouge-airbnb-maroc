# 📘 Cahier des Charges Data

## Projet Fil Rouge – Analyse Comparative Airbnb

---

# 1. Contexte général

Le marché de la location courte durée via Airbnb constitue un segment majeur de l’économie touristique européenne.
Madrid et Barcelona figurent parmi les destinations les plus attractives d’Espagne, avec des dynamiques économiques et réglementaires distinctes.

Dans ce contexte, une analyse comparative structurée des deux marchés permet :

* D’évaluer leur positionnement tarifaire
* D’identifier les différences de segmentation
* D’analyser la dispersion et la structure des prix
* D’orienter une stratégie d’investissement immobilier

---

# 2. Problématique analytique

Comment comparer quantitativement la structure du marché Airbnb entre Madrid et Barcelona afin d’identifier les différences de positionnement prix, de segmentation et d’opportunité d’investissement ?

---

# 3. Objectifs du projet

## 3.1 Objectif principal

Construire une solution data complète permettant de comparer les marchés Airbnb de Madrid et Barcelona à travers une analyse exploratoire, statistique et décisionnelle.

## 3.2 Objectifs secondaires

* Mesurer et comparer les niveaux de prix
* Analyser la dispersion et la concentration
* Étudier la segmentation par type de logement
* Identifier les écarts structurels entre les deux villes
* Construire un dashboard décisionnel

---

# 4. Indicateurs clés de performance (KPI)

## 4.1 Indicateurs tarifaires

* Prix moyen par ville
* Prix médian par ville
* Prix moyen par type de logement
* 99e percentile des prix
* Écart-type des prix

## 4.2 Indicateurs structurels

* Nombre total de logements par ville
* Répartition par type de logement
* Part relative de chaque segment

## 4.3 Indicateurs d’activité

* Nombre moyen de reviews
* Disponibilité moyenne annuelle (availability\_365)
* Fréquence des avis (reviews\_per\_month)

---

# 5. Sources de données

## 5.1 Source principale

Plateforme : Inside Airbnb
URL : [http://insideairbnb.com/get-the-data/](http://insideairbnb.com/get-the-data/)

## 5.2 Villes étudiées

* Madrid
* Barcelona

## 5.3 Fichiers utilisés

* listings.csv
* reviews.csv
* calendar.csv.gz
* neighbourhoods.csv

Date de téléchargement : 02/11/2026

---

# 6. Architecture Data

## 6.1 Pipeline global

1. Collecte des données (téléchargement manuel)
2. Stockage des données brutes (data/raw)
3. Nettoyage :
   * Suppression des valeurs manquantes critiques (price)
   * Suppression des colonnes inutiles (license)
   * Suppression des valeurs extrêmes (99e percentile)
4. Fusion des datasets (Madrid + Barcelona)
5. Calcul des KPI
6. Visualisation
7. Dashboard final

## 6.2 Organisation du repository

<pre class="overflow-visible! px-0!" data-start="2857" data-end="2928"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(var(--sticky-padding-top)+9*var(--spacing))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>data/
    raw/
    processed/
notebooks/
</span><span>src</span><span>/
docs/
dashboards/
</span></span></code></div></div></pre>

---

# 7. Modèle de données simplifié

Table principale : listings\_clean

Champs principaux :

* id (clé primaire)
* host\_id
* city
* neighbourhood
* latitude
* longitude
* room\_type
* price
* minimum\_nights
* number\_of\_reviews
* reviews\_per\_month
* availability\_365

Relation possible avec reviews et calendar pour analyses avancées.

---

# 8. Contraintes techniques

* Volume important du fichier calendar
* Gestion mémoire lors du chargement
* Données hétérogènes entre villes
* Présence de valeurs extrêmes

---

# 9. Hypothèses à tester

H1 : Barcelona présente un prix moyen supérieur à Madrid
H2 : La dispersion des prix est plus élevée à Barcelona
H3 : La proportion de logements premium est plus importante à Barcelona
H4 : Madrid présente un volume d’offre plus élevé

---

# 10. Livrables attendus

* Repository GitHub structuré
* Scripts de nettoyage reproductibles
* Notebook d’analyse exploratoire
* Dashboard décisionnel
* Rapport final en data storytelling
* Soutenance orale structurée

---

# 11. Valeur ajoutée du projet

Ce projet permet :

* Une analyse comparative rigoureuse
* Une application complète du cycle de vie de la donnée
* Une démonstration des compétences Data Analyst
* Une restitution orientée décisionnel

---

# 12. Conclusion

Ce cahier des charges formalise la traduction technique d un besoin métier en solution analytique structurée, reproductible et orientée prise de décision.
