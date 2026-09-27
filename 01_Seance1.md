---
title: Séance 1 - Données et premiers pas dans QGIS
nav_order: 3
---

# Séance 1 — Des données à la première carte sous QGIS

Cette première journée est organisée en deux temps : **le matin, rechercher et comprendre les données** ; **l’après-midi, découvrir QGIS, créer des données et réaliser une première carte**.

---

# Matin (9h–12h) — Rechercher et comprendre les données

## De la question de recherche aux données cartographiques

> **Fil conducteur : avant d'ouvrir QGIS, il faut savoir ce que l'on veut montrer et avec quelles données.**

## 🎯 Objectifs

À la fin de la matinée, vous devrez être capable de définir une question cartographique, reconnaître la nature d'une donnée, évaluer une source et commencer la recherche des données de votre projet final.

# 1. De la question à la carte

Une carte ne commence pas par le logiciel. Elle commence par une question : **quel phénomène veut-on montrer, sur quel territoire et à quelle date ?**

Exemples : répartition du chômage en Europe ; migrations internationales ; PIB par habitant ; implantation d'organisations internationales ; événements géopolitiques.

# 2. Qu'est-ce qu'une donnée géographique ?

Une donnée géographique associe une **localisation** à des **informations attributaires**. Les objets peuvent être ponctuels, linéaires ou surfaciques.

| Implantation | Exemple |
|---|---|
| Point | ville, ambassade, événement |
| Ligne | route, frontière, flux |
| Polygone | pays, région, commune |

# 3. Comprendre la nature des variables

Avant de représenter une variable, il faut l'identifier.

- **Qualitative** : type, catégorie, statut.
- **Quantitative absolue / stock** : population totale, nombre d'événements.
- **Quantitative relative / taux** : taux de chômage, part en %, PIB par habitant.

> **Règle essentielle : un stock et un taux ne se représentent pas de la même manière.**

# 4. Rechercher des données

Une donnée n'est utile que si l'on comprend sa source et sa construction. Pour chaque jeu de données, vérifiez : producteur, date, unité, territoire, échelle géographique, format et identifiant.

## 🔎 Exercice 1 — Recherche guidée

À partir d'une question proposée par l'enseignant, trouvez un jeu de données exploitable et complétez :

| Élément | Réponse |
|---|---|
| Source / producteur | |
| Variable | |
| Année | |
| Unité | |
| Échelle géographique | |
| Format | |
| Identifiant géographique | |
| Représentation envisagée | |

## 🧭 Exercice 2 — Lancer votre projet final

Commencez à définir votre propre carte :

- **Je souhaite représenter :** …
- **Territoire :** …
- **Période :** …
- **Question / message recherché :** …
- **Données nécessaires :** …
- **Sources possibles :** …

> Conservez cette fiche. Elle sera reprise en séance 2 puis utilisée pour le projet final de la séance 3.

## ✅ À retenir

**Question → territoire → données → source → nature de la variable → représentation.**


---

# Après-midi (13h–16h) — Premiers pas dans QGIS

## Découverte de QGIS, création de données et première carte

## 🎯 Objectifs

Découvrir l'environnement de QGIS, comprendre les couches et les tables attributaires, créer des objets géographiques et réaliser une première représentation.

# 1. Qu'est-ce qu'un SIG ?

Un système d'information géographique associe une **géométrie** (où ?) à des **attributs** (quoi ?). QGIS organise les informations sous forme de couches superposées.

# 2. L'interface de QGIS

Repérez : canevas cartographique, panneau des couches, explorateur, table attributaire, propriétés, symbologie, outils de navigation et projet QGIS.

## Manipulation

Ouvrir un projet, ajouter une couche, zoomer, sélectionner une entité et ouvrir sa table attributaire.

# 3. Formats courants

- GeoPackage ;
- GeoJSON ;
- Shapefile ;
- CSV.

# 4. Systèmes de coordonnées

Une couche possède un système de référence de coordonnées (SCR). À ce stade, l'objectif est de savoir reconnaître cette information et comprendre qu'elle conditionne la localisation et la superposition des couches.

# 5. Créer des données

Créer une couche, choisir sa géométrie, créer des champs, activer le mode édition, ajouter des entités et renseigner leurs attributs.

## 🛠️ Exercice pratique — Créer et représenter une couche

Créez une couche de points représentant plusieurs lieux. Ajoutez au minimum les champs : **nom**, **catégorie**, **valeur**, **année**.

Testez ensuite plusieurs représentations :

- symbole unique ;
- catégories ;
- graduation ;
- variation de taille ;
- étiquettes.

# 6. Premiers principes de sémiologie graphique

| Nature de l'information | Traduction visuelle privilégiée |
|---|---|
| Catégories sans ordre | teintes différentes |
| Valeurs ordonnées / taux | graduation du clair au foncé |
| Quantités / stocks | taille des symboles |

# 7. Première mise en page

Une carte destinée à être communiquée doit comporter les éléments nécessaires à son interprétation : titre, légende, source, date, auteur, et selon le contexte échelle et orientation.

## 🎯 Production attendue

Une première carte simple exportée depuis QGIS.

## ✅ À retenir

**Couche = géométrie + attributs.** La symbologie doit être choisie en fonction de la nature de l'information.
