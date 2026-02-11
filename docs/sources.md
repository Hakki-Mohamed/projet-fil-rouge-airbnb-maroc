# 📊 Sources de données – Projet Fil Rouge

## 🎯 Contexte

Ce projet analyse et compare le marché Airbnb entre Madrid et Barcelona
afin d’identifier les différences de structure de prix, de segmentation
et de dynamique du marché.

---

## 🌍 Source principale

**Plateforme :** Inside Airbnb
**Site officiel :** http://insideairbnb.com/get-the-data/

Inside Airbnb fournit des datasets publics permettant d’analyser
l’activité Airbnb dans différentes villes du monde.

---

## 🏙 Villes étudiées

- Madrid (Espagne)
- Barcelona (Espagne)

---

## 📁 Fichiers utilisés

Pour chaque ville, les fichiers suivants ont été téléchargés :

### 1️⃣ listings.csv

Contient les informations principales des logements :

- id
- nom du logement
- host_id
- type de logement
- quartier
- latitude / longitude
- prix
- disponibilité
- nombre de reviews
- etc.

### 2️⃣ reviews.csv

Contient les avis laissés par les clients :

- listing_id
- date
- commentaire
- reviewer_id

### 3️⃣ calendar.csv.gz

Contient les données de disponibilité journalière :

- listing_id
- date
- disponible ou non
- prix journalier

### 4️⃣ neighbourhoods.csv

Contient la liste des quartiers de la ville.

---

## 📅 Date d’accès aux données

Les données ont été téléchargées le :
**02/11/2026**

---

## ⚠ Remarques

- Les données sont publiques et destinées à des fins d’analyse pédagogique.
- Aucun traitement de données personnelles sensibles n’est effectué.
- Les datasets bruts ne sont pas versionnés dans le repository GitHub
  (conformément aux bonnes pratiques de gestion des données volumineuses).
