---
title: Séance 2 - Jointures et cartographie thématique
nav_order: 4
---

# Séance 2 - Préparer, joindre et représenter des données dans QGIS

Lors de la première séance, nous avons appris à partir d'une **question cartographique**, à rechercher et comprendre des données, puis à réaliser une première carte dans QGIS.

Nous avons notamment vu qu'une donnée statistique et une donnée géographique ne sont pas nécessairement contenues dans le même fichier.

Un tableau peut contenir les valeurs que nous souhaitons représenter, tandis qu'une couche géographique contient les formes des territoires.

Cette deuxième séance consiste à apprendre à **relier ces informations**, puis à choisir une représentation cartographique adaptée.

La journée est organisée en deux temps :

- **Matin (9h-12h)** : préparer les données, comprendre et réaliser des jointures ;
- **Après-midi (13h-16h)** : transformer les données jointes en carte thématique et construire une mise en page.

> **Fil conducteur de la séance : disposer de données ne suffit pas. Il faut pouvoir les relier correctement à un territoire et choisir une représentation adaptée.**

Nous poursuivons ainsi la chaîne commencée pendant la séance 1 :

**Question → Données → Vérification → Jointure → Représentation → Carte**

---

# 🌅 Matin (9h-12h) - Préparer les données et réaliser des jointures

## 🎯 Objectifs de la matinée

À la fin de la matinée, vous devrez être capable de :

- comprendre pourquoi une jointure est nécessaire ;
- identifier une **clé de jointure** ;
- préparer un tableau avant son utilisation dans QGIS ;
- réaliser une **jointure attributaire** ;
- contrôler le résultat d'une jointure ;
- identifier les entités non appariées ;
- comprendre la différence entre **NULL et zéro** ;
- comprendre le principe d'une **jointure spatiale** ;
- distinguer jointure attributaire et jointure spatiale ;
- réfléchir aux jointures nécessaires pour votre projet personnel.

---

# 1. Du tableau statistique à la carte

Lors de la séance 1, nous avons vu qu'une donnée géographique associe :

> **géométrie + attributs**

Mais les informations nécessaires à une carte ne sont pas toujours contenues dans un même fichier.

Imaginons un tableau statistique :

| CODE | PAYS | PIB_HAB |
| --- | --- | ---: |
| FRA | France | 44 000 |
| ESP | Espagne | 35 000 |
| ITA | Italie | 38 000 |

Ce tableau contient les valeurs statistiques que nous souhaitons représenter.

Mais il ne contient pas nécessairement la **géométrie** permettant de dessiner les pays.

Nous pouvons parallèlement disposer d'une couche géographique :

| CODE | PAYS |
| --- | --- |
| FRA | France |
| ESP | Espagne |
| ITA | Italie |

Cette couche contient les polygones permettant de représenter les territoires.

Pour cartographier le PIB par habitant, nous devons donc **relier les deux tables**.

C'est le principe de la **jointure attributaire**.

---

# 2. La clé de jointure

Une jointure attributaire fonctionne grâce à une information présente dans les deux fichiers.

Cette information est appelée **clé de jointure**.

Dans notre exemple :

**FRA ↔ FRA**

**ESP ↔ ESP**

**ITA ↔ ITA**

QGIS utilise cette correspondance pour associer les informations du tableau statistique aux territoires de la couche géographique.

---

## 2.1. Pourquoi utiliser des identifiants ?

Lorsque cela est possible, il est préférable d'utiliser un **identifiant standardisé** plutôt que le nom du territoire.

Un même territoire peut apparaître sous différentes formes :

- Royaume-Uni ;
- United Kingdom ;
- UK.

Les noms peuvent également varier selon :

- la langue ;
- l'orthographe ;
- les accents ;
- les conventions utilisées par la source.

Les identifiants sont généralement plus stables.

On rencontre notamment :

- les **codes ISO** pour les pays ;
- les **codes NUTS** pour les territoires européens ;
- les **codes INSEE** pour les territoires français.

> **QGIS ne devine pas les correspondances.**

Si une table contient `FRA` et l'autre `FR`, QGIS ne considérera pas automatiquement qu'il s'agit du même territoire.

---

# 3. Préparer les données avant une jointure

Une jointure correcte dépend en grande partie de la qualité des données utilisées.

Avant de commencer, il faut donc examiner le tableau.

Vérifiez notamment :

- les noms des colonnes ;
- le type des colonnes ;
- les valeurs manquantes ;
- les doublons ;
- le format des identifiants ;
- la présence éventuelle d'espaces ;
- la correspondance entre les codes ;
- la distinction entre texte et nombre.

---

## ⚠️ Exemple de problème

Deux fichiers peuvent sembler utiliser le même identifiant :

| Fichier statistique | Couche géographique |
| --- | --- |
| 01 | 1 |
| 02 | 2 |
| 03 | 3 |

Pour un utilisateur, `01` et `1` peuvent sembler désigner la même chose.

Pour QGIS, leur correspondance dépend notamment du **type et du format du champ**.

Il faut donc toujours examiner les données avant la jointure.

> **Une grande partie du travail cartographique consiste à préparer les données avant de les représenter.**

---

# 4. Réaliser une jointure attributaire dans QGIS

La démarche générale est la suivante :

1. importer la couche géographique ;
2. importer le tableau statistique ;
3. ouvrir les tables ;
4. identifier la clé commune ;
5. ouvrir les propriétés de la couche géographique ;
6. configurer la jointure ;
7. appliquer la jointure ;
8. examiner la nouvelle table attributaire.

Après la jointure, les informations provenant du tableau statistique doivent apparaître dans la table de la couche géographique.

---

# 5. Contrôler la jointure

Une jointure qui s'exécute sans message d'erreur n'est pas nécessairement correcte.

Il faut systématiquement vérifier le résultat.

Posez-vous les questions suivantes :

- Tous les territoires ont-ils reçu une valeur ?
- Certaines valeurs sont-elles `NULL` ?
- Les valeurs obtenues correspondent-elles au tableau d'origine ?
- Certains identifiants n'ont-ils pas trouvé de correspondance ?
- Existe-t-il des doublons ?

> **Une jointure n'est jamais terminée tant que son résultat n'a pas été vérifié.**

---

## ⚠️ NULL ne signifie pas zéro

Cette distinction est importante.

**0** est une valeur.

Elle signifie que la quantité observée est égale à zéro.

**NULL** signifie généralement que la valeur est absente ou qu'aucune correspondance n'a été trouvée.

Par exemple :

| Département | Nombre d'événements |
| --- | ---: |
| A | 0 |
| B | NULL |

Dans le département A, nous savons qu'aucun événement n'a été observé.

Pour le département B, nous ne disposons pas nécessairement de l'information.

> **Ne remplacez donc pas automatiquement les valeurs NULL par zéro.**

---

# 🛠️ Activité pratique 1 - Réaliser une jointure attributaire

À partir des fichiers fournis, réalisez une jointure entre :

- la **couche des départements** ;
- les **données CSP par département**.

Identifiez d'abord la clé commune utilisée dans les deux fichiers.

Réalisez ensuite la jointure dans QGIS.

---

## À vérifier

Répondez aux questions suivantes :

1. Quelle est la clé utilisée pour la jointure ?
2. Tous les départements ont-ils reçu une valeur ?
3. Existe-t-il des valeurs `NULL` ?
4. Les valeurs obtenues correspondent-elles aux données CSP d'origine ?
5. Certaines lignes n'ont-elles pas trouvé de correspondance ?

Si vous identifiez un problème, essayez d'en déterminer la cause avant de poursuivre.

---

# 6. La jointure spatiale

Toutes les jointures ne reposent pas sur un identifiant.

Dans certaines situations, deux couches peuvent être reliées grâce à leur **position dans l'espace**.

C'est le principe de la **jointure spatiale**.

---

## Exemple

Nous disposons :

- d'une couche représentant les départements ;
- d'une couche contenant des points.

Nous souhaitons connaître le nombre de points présents dans chaque département.

Il n'est pas nécessaire que les points possèdent le code du département.

QGIS peut déterminer leur appartenance grâce à leur localisation.

---

## 6.1. Les relations spatiales

Une jointure spatiale peut reposer sur différentes relations :

- **dans** ;
- **contient** ;
- **intersecte** ;
- **touche** ;
- etc.

Par exemple :

> **Dans quel département se trouve ce point ?**

ou :

> **Combien de points sont contenus dans chaque département ?**

---

## 🔑 Deux types de jointures

| Type de jointure | Principe |
| --- | --- |
| **Jointure attributaire** | relation grâce à un identifiant commun |
| **Jointure spatiale** | relation grâce à la position géographique |

---

# 🛠️ Activité pratique 2 - Réaliser une jointure spatiale

À partir de la couche des départements et de la couche de points fournie, réalisez une jointure spatiale afin de déterminer :

> **Combien de points sont présents dans chaque département ?**

Observez le résultat.

---

## Questions

- Avez-vous utilisé un identifiant commun ?
- Quelle relation spatiale avez-vous utilisée ?
- Combien de points trouve-t-on dans chaque département ?
- Quelle différence observez-vous avec la jointure attributaire ?

---

# 🧭 Application à votre projet personnel

Reprenez maintenant les données identifiées pendant la séance 1.

Posez-vous les questions suivantes :

| Question | Votre projet |
| --- | --- |
| Quel est mon territoire d'étude ? | |
| Quel est mon niveau géographique ? | |
| Quelle est ma donnée statistique ? | |
| Quel est mon fond géographique ? | |
| Existe-t-il un identifiant commun ? | |
| Quelle pourrait être ma clé de jointure ? | |
| Dois-je réaliser une jointure attributaire ou spatiale ? | |

---

# ✅ Bilan de la matinée

À retenir :

1. Une jointure permet de **relier des informations provenant de plusieurs sources**.
2. Une jointure attributaire nécessite une **clé commune**.
3. Les identifiants standardisés sont généralement plus fiables que les noms.
4. Les données doivent être préparées avant la jointure.
5. Une jointure doit toujours être contrôlée.
6. **NULL ne signifie pas zéro.**
7. Une jointure spatiale utilise la **position géographique** plutôt qu'un identifiant.

**Données statistiques + fond géographique → Jointure → Couche enrichie**

---

# 🌇 Après-midi (13h-16h) - De la jointure à la carte thématique

# 7. Choisir une représentation adaptée

## 🎯 Objectifs de l'après-midi

À la fin de l'après-midi, vous devrez être capable de :

- identifier la nature de la variable à cartographier ;
- choisir une représentation adaptée ;
- réaliser une carte choroplèthe ;
- comprendre le principe de discrétisation ;
- comparer plusieurs méthodes de classification ;
- utiliser des symboles proportionnels ;
- construire une mise en page complète ;
- exporter une carte ;
- justifier vos choix cartographiques.

---

# 8. Quelle représentation pour quelle donnée ?

Une fois les données jointes, une nouvelle question apparaît :

> **Comment représenter la variable ?**

Le choix dépend d'abord de la **nature de la donnée**.

| Nature de la donnée | Exemple | Représentation possible |
| --- | --- | --- |
| **Valeur relative** | taux de chômage | carte choroplèthe |
| **Densité** | habitants/km² | carte choroplèthe |
| **Valeur absolue** | population totale | symboles proportionnels |
| **Catégorie** | parti arrivé en tête | couleurs distinctes |
| **Flux** | migrations | lignes / flèches |

> **Avant d'ouvrir la symbologie, demandez-vous : quelle est la nature de ma donnée ?**

---

# 9. La carte choroplèthe

Une **carte choroplèthe** représente une variable quantitative en faisant varier la couleur des unités territoriales.

Elle est particulièrement adaptée aux **valeurs relatives** :

- taux ;
- pourcentages ;
- proportions ;
- densités ;
- ratios.

Par exemple, à partir des données CSP, nous pouvons représenter :

- la part des cadres ;
- la part des professions intermédiaires ;
- la part des employés ;
- la part des ouvriers.

---

## 9.1. Réaliser une carte choroplèthe dans QGIS

Dans les propriétés de la couche :

1. ouvrez **Symbologie** ;
2. choisissez **Gradué** ;
3. sélectionnez la variable ;
4. choisissez un nombre de classes ;
5. sélectionnez une méthode de classification ;
6. appliquez un dégradé adapté ;
7. observez le résultat.

La carte obtenue dépend alors directement des choix effectués.

---

# 10. La discrétisation

Pour représenter une série statistique sur une carte choroplèthe, les valeurs sont généralement regroupées en **classes**.

Cette opération est appelée **discrétisation**.

QGIS propose plusieurs méthodes.

---

## 10.1. Intervalles égaux

Les classes possèdent la même amplitude.

Cette méthode est simple à comprendre, mais peut produire des classes contenant très peu de territoires lorsque les données sont très inégalement distribuées.

---

## 10.2. Quantiles

Les classes contiennent approximativement le même nombre de territoires.

Cette méthode répartit donc les observations entre les différentes classes.

---

## 10.3. Ruptures naturelles - Jenks

Cette méthode recherche les regroupements et les ruptures présentes dans la distribution statistique.

Elle tente de constituer des classes relativement homogènes.

---

## ⚠️ Une classification n'est jamais neutre

Une même série statistique peut produire des cartes visuellement très différentes selon la méthode utilisée.

La classification influence donc directement la lecture du phénomène.

> **Le bouton "Classer" de QGIS ne remplace pas le raisonnement du cartographe.**

---

# 🛠️ Activité pratique 3 - Une donnée, trois cartes

À partir de la jointure réalisée précédemment, choisissez une même variable.

Réalisez successivement :

- **Carte A : intervalles égaux**
- **Carte B : quantiles**
- **Carte C : ruptures naturelles (Jenks)**

Conservez le **même nombre de classes** pour les trois cartes.

---

## Comparez les résultats

- Les mêmes territoires apparaissent-ils toujours dans les classes les plus élevées ?
- Les contrastes sont-ils identiques ?
- Quelle méthode fait apparaître le mieux les différences ?
- Quelle méthode choisiriez-vous ?
- Pourquoi ?

> **À retenir : la classification proposée par QGIS ne doit jamais être acceptée automatiquement sans réflexion.**

---

# 11. Les symboles proportionnels

Une carte choroplèthe n'est pas adaptée à toutes les variables.

Pour représenter une **quantité absolue**, il est généralement préférable d'utiliser des symboles dont la taille varie avec la valeur.

Exemples :

- population totale ;
- nombre de médecins ;
- nombre d'entreprises ;
- nombre de migrants ;
- nombre d'établissements.

> **Plus la quantité est importante, plus le symbole est grand.**

---

## 💡 Valeur absolue ou valeur relative ?

Retenez la distinction suivante :

| Type de donnée | Représentation généralement adaptée |
| --- | --- |
| **Taux / part / ratio / densité** | choroplèthe |
| **Effectif / stock / quantité totale** | symboles proportionnels |

Ce principe doit cependant toujours être mis en relation avec la **question cartographique**.

---

# 🛠️ Manipulation - Comparer deux représentations

Choisissez une valeur absolue, par exemple la population totale.

Représentez-la :

1. par aplats de couleurs ;
2. par symboles proportionnels.

Comparez les deux cartes.

Quelle représentation vous semble la plus cohérente ?

Pourquoi ?

---

# 12. Réaliser la carte finale

Une carte visible dans le canevas de QGIS n'est pas encore une carte terminée.

Pour pouvoir être communiquée, elle doit être placée dans une **mise en page**.

La carte doit pouvoir être comprise sans avoir besoin d'ouvrir QGIS ou d'interroger son auteur.

---

# 13. Créer une mise en page dans QGIS

Dans la fenêtre principale de QGIS :

**Projet → Nouvelle mise en page…**

Donnez un nom à votre mise en page.

Par exemple :

`Carte_CSP_France`

Une nouvelle fenêtre s'ouvre.

---

## 13.1. Ajouter la carte

Dans la fenêtre de mise en page :

**Ajouter un objet → Ajouter une carte**

Dessinez ensuite le cadre dans lequel la carte doit apparaître.

> **Attention : ajouter une carte dans la mise en page ne crée pas une nouvelle carte. La mise en page affiche la carte du projet QGIS.**

---

## 13.2. Ajuster le cadrage

Sélectionnez la carte.

Dans les **Propriétés de l'objet**, vous pouvez notamment :

- modifier l'échelle ;
- ajuster le cadrage ;
- modifier la position du contenu.

L'objectif est d'obtenir une composition équilibrée et d'éviter les espaces inutiles.

---

# 14. Les éléments indispensables d'une carte

Votre mise en page doit comporter au minimum :

- **un titre** ;
- **la carte** ;
- **une légende** ;
- **l'unité** ;
- **la source** ;
- **la date des données** ;
- **le nom de l'auteur**.

Selon les besoins, vous pourrez également ajouter :

- une échelle graphique ;
- une orientation ;
- un logo ;
- un cadre ;
- d'autres éléments graphiques utiles.

---

# 15. Vérifier la carte avant l'export

Avant d'exporter votre travail, posez-vous les questions suivantes :

- Le titre indique-t-il clairement le phénomène représenté ?
- Le territoire est-il identifiable ?
- La légende est-elle compréhensible ?
- L'unité est-elle indiquée ?
- Les classes sont-elles lisibles ?
- Les couleurs sont-elles cohérentes ?
- La source est-elle indiquée ?
- La date des données est-elle indiquée ?
- Le nom de l'auteur est-il présent ?
- La carte est-elle correctement cadrée ?

---

# 📤 Exporter la carte

Lorsque la mise en page est terminée, exportez votre travail :

- au format **PDF** ;
- ou au format **PNG**.

Vous obtenez ainsi une carte indépendante de l'interface QGIS pouvant être utilisée dans :

- un rapport ;
- un mémoire ;
- une présentation ;
- un dossier ;
- une publication en ligne.

---

# 🛠️ Activité pratique 4 - De la donnée CSP à la carte finale

À partir de la couche des départements enrichie avec les données CSP, réalisez une **carte thématique complète**.

## 1. Réaliser la carte

Choisissez une variable CSP.

Déterminez :

- la nature de la variable ;
- la représentation adaptée ;
- le nombre de classes ;
- la méthode de classification ;
- les couleurs ;
- la symbologie.

Vérifiez que la carte permet de comparer correctement les départements.

## 2. Réaliser la mise en page

Votre carte devra comporter au minimum :

**titre + carte + légende + unité + source + date des données + auteur**

Exportez ensuite votre travail en **PDF ou PNG**.

---

# 🔄 Comparaison collective

Comparez plusieurs cartes réalisées à partir des mêmes données.

Posez-vous notamment les questions suivantes :

- Quelle carte est la plus lisible ?
- Les cartes donnent-elles toutes la même impression ?
- Quel est l'effet du nombre de classes ?
- Quel est l'effet de la méthode de discrétisation ?
- Quel est l'effet des couleurs ?
- Quel est l'effet de la taille des symboles ?
- Quels choix cartographiques expliquent les différences observées ?

> **Une carte thématique n'est pas produite automatiquement par QGIS : les choix du cartographe influencent la lecture du phénomène représenté.**

---

# 🎯 Production attendue en fin de séance

À la fin de cette deuxième journée, vous devez être capable de réaliser une chaîne de traitement complète :

**Tableau statistique**

↓

**Vérification des données**

↓

**Identification de la clé**

↓

**Jointure**

↓

**Contrôle**

↓

**Choix de la représentation**

↓

**Symbologie**

↓

**Mise en page**

↓

**Carte thématique**

---

# 🧭 Point d'étape sur votre projet personnel

Votre projet cartographique doit maintenant devenir plus concret.

À la fin de la séance, essayez de compléter cette fiche :

| Élément | Votre projet |
| --- | --- |
| **Sujet / phénomène** | |
| **Question cartographique** | |
| **Territoire** | |
| **Échelle géographique** | |
| **Période** | |
| **Données statistiques** | |
| **Source** | |
| **Fond géographique** | |
| **Identifiant / clé de jointure** | |
| **Type de variable** | |
| **Représentation envisagée** | |

---

# 📄 Support de cours

Le support de cours de la séance 2 est disponible au format PDF.

👉 [**Télécharger le support de cours - Séance 2 : Préparer, joindre et représenter des données dans QGIS (PDF)**](documents/Seance_2_Preparer_joindre_et_representer_des_donnees_dans_QGIS.pdf)

---

# 💻 Logiciel

Le logiciel utilisé pendant la séance est **QGIS**.

👉 [**Accéder au site officiel de QGIS**](https://qgis.org/)

👉 [**Télécharger QGIS**](https://qgis.org/download/)

---

# ✅ À retenir - Séance 2

À la fin de cette deuxième séance, retenez principalement que :

1. Une jointure attributaire nécessite une **clé commune fiable**.

2. Les identifiants standardisés sont généralement préférables aux noms des territoires.

3. Une jointure doit toujours être **contrôlée**.

4. **NULL ne signifie pas zéro.**

5. Une jointure spatiale repose sur une **relation de position**.

6. La nature de la variable détermine en grande partie la représentation cartographique.

7. Une **valeur relative** se prête généralement à une carte choroplèthe.

8. Une **valeur absolue** se prête généralement à des symboles proportionnels.

9. Le choix de la méthode de **discrétisation** influence la lecture de la carte.

10. Une carte finale doit être correctement **mise en page, documentée et sourcée**.

11. QGIS fournit des outils, mais les **choix cartographiques appartiennent au cartographe**.

---

## 🧭 Le chemin parcouru

**Question**

↓

**Recherche des données**

↓

**Compréhension et vérification**

↓

**Fond géographique**

↓

**Clé de jointure**

↓

**Jointure**

↓

**Contrôle**

↓

**Choix de la représentation**

↓

**Classification et symbologie**

↓

**Mise en page**

↓

**Carte thématique**

---

# ➡️ Pour préparer la séance 3

La troisième et dernière séance sera consacrée à la **réalisation de votre projet cartographique personnel**.

Nous ne travaillerons plus uniquement à partir des données d'exercice : vous appliquerez progressivement la démarche étudiée pendant les deux premières séances à **vos propres données**.

Avant la séance 3, essayez donc d'arriver avec :

- un **sujet** clairement identifié ;
- une **question cartographique** ;
- un **territoire d'étude** ;
- une **période** ;
- une ou plusieurs **sources de données** ;
- les **données statistiques** que vous souhaitez représenter ;
- un **fond géographique adapté** ;
- un éventuel **identifiant ou une clé de jointure** ;
- une première réflexion sur la **représentation cartographique** à utiliser.

Vérifiez autant que possible vos données avant la séance :

- les identifiants correspondent-ils ?
- les valeurs sont-elles exploitables ?
- connaissez-vous leur unité ?
- connaissez-vous leur date ?
- votre fond géographique correspond-il au même niveau territorial ?
- la jointure fonctionne-t-elle ?

> **Objectif pour la séance 3 : ne plus apprendre séparément les outils, mais les mobiliser ensemble pour construire une carte répondant à votre propre question.**

La dernière séance permettra ainsi de passer de :

**« Je sais utiliser les principaux outils de QGIS »**

à :

**« Je sais construire et justifier une démarche cartographique complète. »**
