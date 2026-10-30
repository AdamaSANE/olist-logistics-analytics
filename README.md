# 📦 olist-logistics-analytics

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Wrangling-150458?style=for-the-badge&logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-E97627?style=for-the-badge&logo=tableau)

Ce projet analyse les performances logistiques et l'impact des délais de livraison sur la satisfaction client, à partir du jeu de données public du e-commerçant brésilien Olist.

## 🎯 Méthodologie STAR

### 📍 Situation

Dans le secteur du e-commerce, la chaîne d'approvisionnement est un facteur critique de succès. Olist, une plateforme brésilienne, dispose de milliers de transactions réparties dans plusieurs bases de données relationnelles. Le défi métier est d'identifier comment les délais d'acheminement impactent directement les notes laissées par les clients, afin de formuler des recommandations d'optimisation claires pour les décideurs.

### 📋 Tâche (Task)

La première phase de ce projet consistait à construire un pipeline de préparation de données (ETL). L'objectif : extraire les données brutes de plusieurs tables, nettoyer les formats incohérents (notamment les dates), et modéliser une vue unifiée à 360° ("Gold Table") prête pour la visualisation.

### 🛠️ Action

Pour résoudre ce problème, le script Python (`1_exploration.ipynb`) exécute les opérations suivantes :

1. **Ingestion de Données :** Extraction des 3 tables majeures (Commandes, Clients, Avis) totalisant près de 100 000 lignes.
2. **Data Cleaning & Typage :** Conversion des jalons logistiques du format texte brut vers des formats temporels calculables (`datetime`).
3. **Feature Engineering :** Création du KPI `delivery_time_days` en calculant le delta entre la date d'achat et la date de livraison réelle.
4. **Modélisation Relationnelle :** Consolidation des données via des jointures (Inner et Left Joins via Pandas) pour lier le profil géographique du client, les données de la commande et le score de satisfaction final.
5. **Filtrage Opérationnel :** Exclusion du bruit statistique en ne conservant que les commandes au statut finalisé (`delivered`).

### 📈 Résultat (Result)

Création d'un jeu de données analytique propre et optimisé (`data/olist_master_dataset.csv`). Ce fichier centralisé garantit l'intégrité des calculs de performance logistique et sert de source unique pour la création du tableau de bord exécutif sur Tableau.

---

## 💻 Comment reproduire ce projet en local

Ce projet respecte les bonnes pratiques de développement en utilisant un environnement virtuel isolé.

1. **Cloner le dépôt :**
   ```bash
   git clone [https://github.com/AdamaSANE/olist-logistics-analytics.git](https://github.com/AdamaSANE/olist-logistics-analytics.git)
   cd olist-logistics-analytics
   ```
