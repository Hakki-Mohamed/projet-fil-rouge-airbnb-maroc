# Projet Fil Rouge – Analyse Comparative du Marché Airbnb

### Madrid vs Barcelona

---

## 🎯 Objectif du projet

Concevoir une solution data complète de bout en bout permettant de comparer le marché Airbnb entre Madrid et Barcelona, dans une logique d’aide à la décision pour un investisseur immobilier.

Le projet couvre l’intégralité du cycle de vie de la donnée :

Collecte → Nettoyage → Modélisation → Analyse → KPI → Base analytique → Dashboard

---

## 📌 Problématique métier

Existe-t-il une différence significative entre les prix Airbnb à Madrid et Barcelona ?

* Quelle ville présente un positionnement premium ?
* Quelle ville offre davantage d’opportunités accessibles ?
* Le type de logement influence-t-il significativement le prix ?

---

## 📊 Indicateurs analysés (KPI)

* Prix moyen par ville
* Médiane des prix
* Nombre de logements
* Prix moyen par type de logement
* Disponibilité annuelle moyenne
* Corrélation prix vs disponibilité
* Test statistique de comparaison des moyennes

---

## 📂 Sources de données

Données issues de **Inside Airbnb** :

* listings.csv
* calendar.csv
* reviews.csv
* neighbourhoods.csv

Villes étudiées :

* Madrid
* Barcelona

Date de téléchargement : 02/11/2026

---

## 🏗 Architecture Data

<pre class="overflow-visible! px-0!" data-start="1672" data-end="1790"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(var(--sticky-padding-top)+9*var(--spacing))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>data/
├── raw/            → données brutes
├── processed/      → données nettoyées + exports KPI + </span><span>base</span><span> SQLite
</span></span></code></div></div></pre>

<pre class="overflow-visible! px-0!" data-start="1792" data-end="1973"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(var(--sticky-padding-top)+9*var(--spacing))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>notebooks/
├── 01_listings_merge_v2.ipynb
├── 02_extraction_eda_v2.ipynb
├── 03_database_modeling.ipynb
├── 04_data_model_star_schema.ipynb
├── 05_sql_kpis_star_schema.ipynb
</span></span></code></div></div></pre>

<pre class="overflow-visible! px-0!" data-start="1975" data-end="2056"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(var(--sticky-padding-top)+9*var(--spacing))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>docs/
├── cadrage_metier.md
├── cahier_des_charges_data.md
├── sources.md
</span></span></code></div></div></pre>

---

## 🔄 Pipeline Data

### 1️⃣ Fusion

Fusion des listings Madrid & Barcelona avec création d’une variable `city`.

### 2️⃣ Nettoyage & Préparation

* Suppression des valeurs manquantes critiques
* Suppression des outliers via 99e percentile
  (choix méthodologique pour limiter l’impact des valeurs extrêmes sur la moyenne)
* Harmonisation des colonnes
* Export vers `listings_clean.csv`

### 3️⃣ Analyse Exploratoire (EDA)

* Statistiques descriptives
* Distribution des prix
* Segmentation par type de logement
* Analyse comparative par ville

### 4️⃣ Validation Statistique

T-test indépendant (Welch) :

* p-value < 0.05
* Différence statistiquement significative
* Barcelona présente des prix moyens supérieurs à Madrid

### 5️⃣ Modélisation Analytique

Création d’une base SQLite structurée en **schéma en étoile (Star Schema)** :

* `fact_listings`
* `dim_city`
* `dim_room_type`

Objectif : préparer les données pour exploitation BI (Power BI).

### 6️⃣ KPI en SQL

Calcul des indicateurs directement dans la base analytique et export vers :

<pre class="overflow-visible! px-0!" data-start="3115" data-end="3138"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="sticky top-[calc(var(--sticky-padding-top)+9*var(--spacing))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>data/processed/
</span></span></code></div></div></pre>

---

## 📈 Résultats clés

* Barcelona = marché plus premium
* Madrid = plus accessible
* Les logements "Entire home/apt" tirent les prix vers le haut
* Corrélation faible entre prix et disponibilité

---

## 💼 Conclusion Métier

Pour un investisseur :

* Barcelona convient à une stratégie haut de gamme.
* Madrid offre davantage d’opportunités avec un ticket d’entrée plus modéré.
* La segmentation par type de logement est déterminante.

---

## ⚙️ Stack Technique

* Python
* Pandas / NumPy
* Matplotlib / Seaborn
* SciPy (tests statistiques)
* SQLite (base analytique)
* SQL (KPI)
* Jupyter Notebook
* Git / GitHub


---
