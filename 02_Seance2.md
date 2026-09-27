---
title: Séance 2 - Jointures et cartographie thématique
nav_order: 4
---

# Séance 2 — Jointures et cartographie thématique dans QGIS

Cette deuxième journée est organisée en deux temps : **le matin, préparer les données et maîtriser les jointures** ; **l’après-midi, transformer les données jointes en carte thématique**.

---

# Matin (9h–12h) — Préparer les données et réaliser des jointures

## Des données statistiques à la carte : les jointures

## 🎯 Objectifs

Savoir préparer un tableau, identifier une clé commune, réaliser une jointure attributaire dans QGIS, contrôler le résultat et comprendre le principe d'une jointure spatiale.

# 1. Pourquoi une jointure ?

Un CSV contient souvent les valeurs statistiques mais aucune géométrie. Une couche géographique contient les pays, régions ou communes. La jointure permet de réunir les deux.

# 2. La clé de jointure

Une jointure attributaire nécessite un identifiant commun. Il est préférable d'utiliser des codes normalisés plutôt que les noms des territoires.

Exemple : **FRA**, **ESP**, **ITA** plutôt que des noms susceptibles de varier selon les sources.

# 3. Préparer le tableau

Avant la jointure, contrôler :

- noms et types des colonnes ;
- valeurs manquantes ;
- doublons ;
- format des identifiants ;
- correspondance des codes ;
- distinction texte / nombre.

# 4. Réaliser la jointure dans QGIS

Démarche : importer la couche, importer le CSV, identifier les clés, configurer la jointure puis examiner la table résultante.

> **Une jointure n'est jamais terminée tant que son résultat n'a pas été vérifié.**

## 🛠️ Exercice — Première jointure

À partir d'un fond de carte et d'un CSV fournis :

1. importer les deux fichiers ;
2. identifier l'identifiant commun ;
3. réaliser la jointure ;
4. compter / repérer les entités non appariées ;
5. diagnostiquer les erreurs ;
6. corriger et recommencer.

# 5. Introduction à la jointure spatiale

La jointure spatiale ne repose pas sur un code commun mais sur une relation géographique : **dans**, **intersecte**, **contient**, etc.

Exemples : attribuer un pays à chaque ambassade ; compter les événements présents dans chaque région.

## 🧭 Lien avec votre projet final

Vérifiez maintenant si vos propres données nécessitent une jointure et si elles possèdent un identifiant compatible avec le fond géographique envisagé.

## ✅ À retenir

**Jointure attributaire = identifiant commun. Jointure spatiale = relation de position. Contrôler systématiquement le résultat.**


---

# Après-midi (13h–16h) — De la jointure à la carte thématique

## De la jointure à la carte thématique

## 🎯 Objectifs

Transformer les données jointes en une carte thématique lisible, choisir une représentation cohérente et réaliser une mise en page complète.

# 1. Quelle représentation pour quelle donnée ?

- **Taux / part / ratio** → souvent carte choroplèthe.
- **Effectif / stock** → symboles proportionnels.
- **Catégorie** → teintes différentes.
- **Relation entre lieux** → flux.

# 2. Carte choroplèthe

Une carte choroplèthe colore des unités territoriales selon une variable quantitative relative. Travail sur le nombre de classes, les bornes, la méthode de classification et le dégradé.

# 3. Discrétisation

Une même série statistique peut produire des cartes différentes selon la méthode de découpage en classes. Le choix doit donc être observé, testé et justifié.

# 4. Symboles proportionnels

Pour une quantité absolue, la taille du symbole permet généralement une lecture plus cohérente que le remplissage des surfaces administratives.

# 5. Mise en page

La carte finale doit être autonome et compréhensible : titre précis, légende, source, date, auteur et éléments d'habillage pertinents.

## 🛠️ Exercice — Du CSV à la carte finale

À partir des fichiers fournis :

1. réaliser et contrôler la jointure ;
2. identifier la nature de la variable ;
3. choisir le type de représentation ;
4. tester une classification ;
5. construire la symbologie ;
6. réaliser une mise en page ;
7. exporter la carte.

## 🔄 Correction collective

Comparer plusieurs cartes réalisées à partir des mêmes données. Qu'est-ce qui change lorsque l'on modifie la classification, la taille des symboles, le nombre de classes ou le choix graphique ?

# 6. Point d'étape sur le projet personnel

Avant de quitter la séance, chaque étudiant·e doit pouvoir présenter : sujet, territoire, données, source, type de variable, fond géographique envisagé et éventuelle clé de jointure.

> **Pour la séance 3, venez avec vos données aussi préparées que possible.**

## ✅ À retenir

La technique ne décide pas à votre place : le type de données et le message recherché doivent guider la représentation.
