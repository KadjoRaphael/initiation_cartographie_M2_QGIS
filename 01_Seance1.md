---
title: Séance 1 - Données et premiers pas dans QGIS
nav_order: 3
---

# Séance 1 - De la question de recherche à la première carte sous QGIS

Cette première séance est consacrée aux bases nécessaires pour commencer un projet cartographique.

La journée est organisée en deux temps :

- **Matin (9h-12h)** : comprendre la démarche cartographique, rechercher et évaluer des données ;
- **Après-midi (13h-16h)** : découvrir QGIS, manipuler et créer des données, puis réaliser une première carte.

> **Fil conducteur de la séance : une carte ne commence pas par un logiciel. Elle commence par une question.**

Avant d'ouvrir QGIS, quatre interrogations doivent guider la démarche :

1. **Qu'est-ce que je veux représenter ?**
2. **Sur quel territoire et à quelle échelle ?**
3. **Avec quelles données ?**
4. **Qu'est-ce que je souhaite montrer grâce à cette carte ?**

---

# 🌅 Matin (9h-12h) - De la question de recherche aux données cartographiques

## 🎯 Objectifs de la matinée

À la fin de la matinée, vous devrez être capable de :

- comprendre pourquoi la cartographie est utilisée pour étudier un phénomène spatial ;
- formuler une question pouvant être représentée sur une carte ;
- comprendre qu'une carte est une représentation construite de la réalité ;
- distinguer une donnée statistique d'une donnée géographique ;
- reconnaître les géométries **point, ligne et polygone** ;
- comprendre le rôle d'une table attributaire ;
- identifier la nature d'une variable ;
- distinguer une valeur absolue d'une valeur relative ;
- identifier l'échelle géographique d'une donnée ;
- repérer un identifiant géographique ;
- rechercher des données auprès de sources fiables ;
- évaluer un jeu de données avant de l'utiliser ;
- commencer à rechercher les données de votre projet cartographique personnel.

---

# 1. Pourquoi apprendre la cartographie ?

La cartographie est à la fois un **outil de représentation**, un **outil d'analyse** et un **outil de communication**.

Elle permet de rendre visible la dimension spatiale d'un phénomène.

De nombreuses questions étudiées en économie, en relations internationales, en sciences politiques, en études européennes ou en géographie possèdent une dimension spatiale.

Par exemple :

- Où se concentre la population ?
- Quels territoires connaissent les taux de chômage les plus élevés ?
- Comment les richesses sont-elles réparties ?
- Où se situent certains conflits ?
- Quels sont les principaux flux migratoires ?
- Comment les résultats électoraux varient-ils selon les territoires ?
- Où sont implantées certaines infrastructures ?
- Comment un phénomène évolue-t-il dans l'espace et dans le temps ?

La carte permet donc de répondre à une question fondamentale :

> **Où se trouve le phénomène étudié et comment varie-t-il dans l'espace ?**

---

## 💡 Du tableau à la carte

Imaginons un tableau contenant le taux de chômage de 200 régions européennes.

La lecture du tableau permet de connaître la valeur de chaque région, mais il est difficile d'identifier immédiatement une organisation spatiale.

Une carte peut faire apparaître plus facilement :

- des concentrations ;
- des oppositions ;
- des gradients ;
- des périphéries ;
- des regroupements régionaux ;
- des exceptions.

La cartographie constitue donc également un **outil d'exploration des données**.

---

# 2. Une carte n'est jamais une simple copie de la réalité

Une carte est une **représentation construite et simplifiée de la réalité**.

Pour réaliser une carte, il faut effectuer de nombreux choix :

- le territoire représenté ;
- l'échelle ;
- les données utilisées ;
- la période ;
- les catégories ;
- les couleurs ;
- les symboles ;
- les informations conservées ;
- les informations supprimées.

Deux personnes utilisant les mêmes données peuvent donc produire des cartes différentes.

Cela ne signifie pas nécessairement qu'une carte est fausse.

Une carte implique toujours une sélection et une simplification de l'information.

Cette opération est notamment liée au principe de **généralisation cartographique**.

> **À retenir : une carte est toujours le résultat de choix méthodologiques.**

---

# 3. Votre projet cartographique individuel

Tout au long du module, vous préparerez progressivement un **projet cartographique personnel**.

Le projet doit partir d'une **question simple comportant une dimension spatiale**.

L'objectif est de construire progressivement une démarche cohérente :

**Question → Données → Traitement → Représentation → Carte finale**

---

## 🧭 Quelques thèmes possibles

Votre projet peut notamment porter sur :

- la répartition de la population ;
- la densité de population ;
- le vieillissement démographique ;
- les migrations internationales ;
- le chômage ;
- le PIB par habitant ;
- la pauvreté ;
- les inégalités ;
- le développement humain ;
- le commerce international ;
- la dépendance énergétique ;
- les émissions de CO₂ ;
- les infrastructures de transport ;
- les équipements publics ;
- l'accès aux soins ;
- les établissements universitaires ;
- les indicateurs environnementaux ;
- les risques naturels ;
- ou une question directement liée à votre mémoire.

Ces exemples sont uniquement indicatifs.

---

## ✏️ Première consigne pour votre projet

À ce stade, vous ne devez pas nécessairement choisir définitivement votre sujet.

Commencez par identifier trois éléments :

> **un phénomène + un territoire + une période**

Par exemple :

**« Le chômage »**

est trop général.

En revanche :

**« Le taux de chômage dans les régions de l'Union européenne en 2025 »**

constitue déjà un sujet cartographiable.

Commencez à compléter cette fiche :

| Élément | Votre projet |
| --- | --- |
| Phénomène étudié | |
| Territoire | |
| Échelle géographique | |
| Période / année | |
| Question cartographique | |
| Données nécessaires | |
| Source(s) possible(s) | |
| Identifiant géographique possible | |

> **Conservez cette réflexion : votre projet sera construit progressivement pendant les trois séances.**

---

# 4. Qu'est-ce qu'une carte ?

Une carte est une **représentation graphique simplifiée et conventionnelle d'un espace géographique**.

Elle permet notamment :

- de localiser des objets ;
- de représenter la distribution spatiale d'un phénomène ;
- de comparer des territoires ;
- de faire apparaître des structures spatiales.

---

## 4.1. La carte topographique

Une carte topographique représente principalement les caractéristiques physiques et matérielles d'un territoire :

- relief ;
- hydrographie ;
- routes ;
- bâtiments ;
- végétation ;
- limites administratives.

Elle répond principalement à une logique de **localisation et d'orientation**.

---

## 4.2. La carte thématique

Une carte thématique représente la distribution spatiale d'un **phénomène particulier**.

Exemples :

- taux de chômage ;
- densité de population ;
- nombre de médecins ;
- migrations ;
- PIB par habitant ;
- émissions de CO₂.

> **Dans ce module, nous travaillerons principalement sur la cartographie thématique.**

---

# 5. De l'information à la donnée géographique

## 5.1. Qu'est-ce qu'une donnée ?

Une donnée est une **information structurée susceptible d'être enregistrée, comparée ou traitée**.

Par exemple :

| Pays | Population |
| --- | ---: |
| France | 68 000 000 |
| Allemagne | 84 000 000 |
| Espagne | 49 000 000 |

Ce tableau contient une information statistique.

Mais pour réaliser une carte, QGIS doit également savoir **où se trouvent** la France, l'Allemagne et l'Espagne.

Il faut donc relier l'information statistique à une information géographique.

---

## 5.2. Qu'est-ce qu'une donnée géographique ?

Une donnée géographique contient directement ou indirectement une information permettant de **localiser un objet dans l'espace**.

Elle associe généralement deux dimensions :

> **Géométrie : où se trouve l'objet ?**  
> **Attributs : que savons-nous de cet objet ?**

Par exemple, pour un pays :

- **géométrie** : le contour du territoire ;
- **attributs** : nom, population, PIB, code ISO, superficie, etc.

Cette association constitue l'un des principes fondamentaux d'un **système d'information géographique (SIG)**.

---

# 6. Les objets géographiques : point, ligne et polygone

Dans QGIS, les données vectorielles sont principalement représentées à l'aide de trois types de géométrie.

| Géométrie | Utilisation | Exemples |
| --- | --- | --- |
| **Point** | Localiser un objet | ville, capitale, ambassade, université, hôpital, port |
| **Ligne** | Représenter un tracé | route, voie ferrée, fleuve, frontière |
| **Polygone** | Représenter une surface | pays, région, département, commune |

---

## 📍 Le point

Un point représente un objet dont on souhaite principalement connaître la **position**.

Un objet réel n'est pas nécessairement ponctuel.

Paris possède évidemment une superficie. Mais sur une carte du monde, Paris peut raisonnablement être représentée par un point.

> **La géométrie dépend donc également de l'échelle de représentation.**

---

## ➖ La ligne

Une ligne représente un objet organisé selon un **tracé**.

Exemples :

- route ;
- voie ferrée ;
- fleuve ;
- frontière.

---

## 🔷 Le polygone

Un polygone représente une **surface délimitée**.

Exemples :

- pays ;
- région ;
- département ;
- commune ;
- circonscription ;
- parc naturel ;
- bassin hydrographique.

Les polygones sont particulièrement importants en cartographie statistique, car de nombreuses données sont publiées selon des découpages administratifs.

---

# 7. La table attributaire

À chaque couche géographique peut être associée une **table attributaire**.

Elle peut être comparée à un tableau :

- chaque **ligne** correspond généralement à un objet géographique ;
- chaque **colonne** correspond à une information concernant cet objet.

Exemple :

| CODE | PAYS | POPULATION | PIB_HAB |
| --- | --- | ---: | ---: |
| FR | France | 68 000 000 | … |
| DE | Allemagne | 84 000 000 | … |
| ES | Espagne | 49 000 000 | … |

Sur la carte, nous voyons des **formes**.

Dans la table attributaire, nous retrouvons les **informations associées à ces formes**.

> **Couche géographique = géométrie + attributs**

Cette relation est fondamentale pour comprendre le fonctionnement de QGIS.

---

# 8. La notion de variable

Une **variable** est une caractéristique observée pour différents objets ou territoires.

Exemples :

- population ;
- revenu ;
- taux de chômage ;
- nombre d'habitants ;
- année d'adhésion à une organisation.

Toutes les variables ne sont pas de même nature.

La nature de la variable influence directement la manière dont elle pourra être représentée.

---

# 9. Données quantitatives et qualitatives

## 9.1. Données quantitatives

Une donnée quantitative correspond à une **quantité mesurable**.

Exemples :

- 68 millions d'habitants ;
- 7,4 % de chômage ;
- 32 000 € par habitant ;
- 120 hôpitaux ;
- 14 tonnes de CO₂.

---

## 9.2. Données qualitatives

Une donnée qualitative décrit une **catégorie ou une caractéristique**.

Exemples :

- membre / non-membre d'une organisation ;
- monarchie / république ;
- langue officielle ;
- type d'équipement.

Il n'existe pas nécessairement de hiérarchie numérique entre ces catégories.

On cherchera donc principalement à les **différencier visuellement**.

---

# 10. Valeurs absolues et valeurs relatives

Cette distinction constitue l'un des points méthodologiques les plus importants du cours.

---

## 10.1. Valeur absolue

Une valeur absolue exprime une **quantité totale**.

Exemples :

- population totale ;
- nombre de chômeurs ;
- nombre de médecins ;
- nombre de migrants ;
- PIB total ;
- nombre d'entreprises.

Une valeur absolue dépend souvent fortement de la taille ou de la population du territoire.

---

## 10.2. Valeur relative

Une valeur relative met une quantité **en relation avec une autre**.

Exemples :

- taux de chômage ;
- PIB par habitant ;
- médecins pour 100 000 habitants ;
- densité de population ;
- part des personnes âgées ;
- pourcentage.

Les valeurs relatives facilitent généralement la comparaison entre des territoires de tailles différentes.

---

## 💡 Stock ou taux ?

Prenons deux territoires :

| Territoire | Nombre de chômeurs | Population active | Taux |
| --- | ---: | ---: | ---: |
| A | 1 000 | 10 000 | 10 % |
| B | 5 000 | 100 000 | 5 % |

Le territoire B possède davantage de chômeurs en **valeur absolue**.

Mais proportionnellement, le chômage est plus important dans le territoire A.

La question posée détermine donc la donnée à utiliser :

> **Où se trouve le plus grand nombre de chômeurs ? → stock**

> **Où le chômage touche-t-il proportionnellement le plus la population active ? → taux**

---

# 11. Échelle géographique et niveau d'analyse

Une donnée n'existe jamais indépendamment de son **niveau géographique**.

On peut travailler à différentes échelles :

- mondiale ;
- nationale ;
- régionale ;
- départementale ;
- communale.

Le même phénomène peut apparaître très différent selon l'échelle choisie.

Une moyenne nationale peut, par exemple, masquer d'importantes disparités régionales.

> **L'échelle est donc un choix analytique et pas seulement un niveau de zoom.**

---

# 12. L'identifiant géographique : une notion fondamentale

Pour associer une donnée statistique à un fond de carte, il faut pouvoir reconnaître les mêmes territoires dans les deux fichiers.

Exemple :

### Table statistique

| CODE | CHOMAGE |
| --- | ---: |
| FR | 7,5 |
| DE | 6,2 |

### Fond géographique

| CODE | PAYS |
| --- | --- |
| FR | France |
| DE | Allemagne |

Le champ **CODE** permet d'établir la correspondance.

On parle d'**identifiant géographique** ou de **clé de jointure**.

Exemples fréquents :

- codes ISO pour les pays ;
- codes administratifs ;
- codes INSEE ;
- codes NUTS pour les territoires européens.

---

## ⚠️ Pourquoi éviter les noms lorsque c'est possible ?

Les noms peuvent varier entre les sources :

- Czechia / Czech Republic ;
- United States / United States of America ;
- différences d'orthographe ;
- différences de langue ;
- différences d'accentuation.

> **Les identifiants standardisés sont généralement plus fiables que les noms des territoires.**

---

# 13. Où trouver des données ?

La recherche de données constitue une compétence à part entière.

Une grande partie du travail cartographique peut être consacrée à la **recherche, au nettoyage et à la préparation des données**.

Voici quelques sources utiles.

---

## 🇫🇷 INSEE

L'**Institut national de la statistique et des études économiques (INSEE)** produit de nombreuses données démographiques, économiques et sociales sur la France.

On peut notamment y trouver des données sur :

- la population ;
- l'emploi ;
- le chômage ;
- le logement ;
- les revenus ;
- les entreprises.

👉 [**Accéder au site de l'INSEE**](https://www.insee.fr/)

---

## 🇪🇺 Eurostat

**Eurostat** est l'office statistique de l'Union européenne.

Il propose des données harmonisées permettant notamment de comparer les États et les régions européennes.

👉 [**Accéder à Eurostat**](https://ec.europa.eu/eurostat/)

---

## 🌍 World Bank Open Data

La **Banque mondiale** met à disposition de nombreux indicateurs internationaux.

On peut notamment y rechercher des données sur :

- l'économie ;
- le développement ;
- la population ;
- la santé ;
- l'environnement.

👉 [**Accéder à World Bank Open Data**](https://data.worldbank.org/)

---

## 🌐 Nations Unies — World Statistics Pocketbook

Les Nations Unies proposent également des statistiques permettant d'étudier de nombreux phénomènes à l'échelle internationale.

👉 [**Accéder aux statistiques des Nations Unies**](https://unstats.un.org/)

---

## 🏛️ data.gouv.fr

**data.gouv.fr** est la plateforme française de données publiques ouvertes.

Elle regroupe des jeux de données produits par des administrations, des collectivités territoriales et différents organismes publics.

👉 [**Accéder à data.gouv.fr**](https://www.data.gouv.fr/)

---

## 🏙️ Paris Data

Certaines collectivités territoriales disposent également de leurs propres portails de données ouvertes.

Le portail **Paris Data** permet, par exemple, d'accéder à des données concernant la ville de Paris.

👉 [**Accéder à Paris Data**](https://opendata.paris.fr/)

---

## 🔬 Organismes de recherche

Des organismes de recherche peuvent également mettre à disposition des données spécialisées.

👉 [**Accéder au site de l'INRAE**](https://www.inrae.fr/)

👉 [**Accéder au site du CNRS**](https://www.cnrs.fr/)

---

# 14. Comment évaluer une source ?

Trouver un fichier téléchargeable ne signifie pas que la recherche est terminée.

Avant d'utiliser une donnée, il faut systématiquement vérifier plusieurs éléments.

| Question | Ce qu'il faut vérifier |
| --- | --- |
| **Qui ?** | Qui produit la donnée ? |
| **Quoi ?** | Que mesure exactement la variable ? |
| **Quand ?** | De quelle année ou période date-t-elle ? |
| **Quelle unité ?** | %, habitants, euros, km², etc. |
| **Quelle population ?** | Quelle population est réellement mesurée ? |
| **Où ?** | À quelle échelle géographique ? |
| **Quel format ?** | CSV, XLSX, GeoJSON, GeoPackage, etc. |
| **Quel identifiant ?** | Existe-t-il un code permettant de relier la donnée à un territoire ? |

---

## ⚠️ Attention à la date

Une donnée ancienne n'est pas nécessairement inutilisable.

En revanche, une donnée datant de 2012 ne doit pas être présentée comme décrivant une situation actuelle.

La **date ou la période** doit toujours être clairement indiquée.

---

## ⚠️ Attention à l'unité

Une variable intitulée « PIB » peut correspondre :

- à des euros ;
- à des dollars ;
- à des milliers ou millions d'euros ;
- au PIB total ;
- au PIB par habitant.

> **Ne jamais interpréter une variable sans connaître son unité.**

---

## ⚠️ Attention à la population mesurée

Deux indicateurs portant un nom similaire peuvent reposer sur des définitions différentes.

Pour le chômage, par exemple, il faut vérifier si la donnée concerne :

- la population totale ;
- la population active ;
- les personnes de 15 à 64 ans ;
- les demandeurs d'emploi inscrits ;
- une autre population de référence.

---

# 15. Les formats de données

Vous pourrez rencontrer différents formats :

- **CSV** ;
- **XLS / XLSX** ;
- **GeoJSON** ;
- **Shapefile** ;
- **GeoPackage** ;
- **JSON** ;
- **API**.

Tous ces formats ne contiennent pas nécessairement une géométrie.

Un fichier Excel comportant une colonne `Pays` et une colonne `PIB` contient des **données statistiques**, mais pas nécessairement les formes géographiques des pays.

Il faudra alors éventuellement relier ce tableau à un **fond géographique**.

---

# 16. Les métadonnées

Les **métadonnées** sont des « données sur les données ».

Elles permettent notamment de savoir :

- qui a produit la donnée ;
- quand elle a été produite ;
- comment elle a été construite ;
- selon quelle définition ;
- dans quelle unité ;
- avec quelles limites.

> **Bon réflexe : ne téléchargez pas uniquement le fichier de données. Consultez également sa documentation et ses métadonnées.**

---

# ✏️ Exercice pratique - Rechercher et évaluer une donnée

Vous disposez d'un jeu de données de l'**INSEE datant de 2012** présentant, pour chaque département français, les effectifs de différentes catégories socioprofessionnelles.

Choisissez l'une des situations proposées :

- cartographier le nombre d'agriculteurs ;
- cartographier le nombre d'ouvriers ;
- comparer le nombre de cadres ;
- cartographier le nombre de retraités ;
- représenter la répartition des employés.

---

## Travail demandé

À partir du jeu de données, identifiez :

| Élément à vérifier | Votre réponse |
| --- | --- |
| **1. Question étudiée** | |
| **2. Source** | |
| **3. Producteur** | |
| **4. Nom exact de la variable** | |
| **5. Année** | |
| **6. Unité** | |
| **7. Valeur absolue ou relative** | |
| **8. Échelle géographique** | |
| **9. Format** | |
| **10. Identifiant géographique** | |
| **11. Présence d'une géométrie** | |
| **12. Fiabilité de la donnée** | |
| **13. Représentation cartographique envisagée** | |

---

## 💡 Pour aller plus loin

Observez les valeurs de plusieurs départements.

Est-il toujours pertinent de comparer directement des **nombres absolus** entre des départements ayant des populations très différentes ?

Quelle transformation de la donnée permettrait de mieux comparer les départements ?

---

# ✅ Bilan de la matinée

À retenir :

1. **Une carte commence par une question claire.**
2. Une donnée doit être comprise avant d'être cartographiée.
3. Il faut connaître sa **source, sa date, son unité, sa définition et son échelle**.
4. Il faut distinguer les données **qualitatives et quantitatives**.
5. Il faut distinguer les **valeurs absolues et relatives**.
6. L'échelle géographique influence l'analyse.
7. Un **identifiant géographique commun** permet de relier des données statistiques à des territoires.

**Question → Données → Vérification → Préparation → Cartographie**

---

# 🌇 Après-midi (13h–16h) - Découvrir QGIS et réaliser une première carte

# 17. Découvrir QGIS et importer des données

## 🎯 Objectif

Comprendre rapidement le fonctionnement d'un **système d'information géographique (SIG)** et réaliser les premières manipulations dans QGIS.

---

## 17.1. Qu'est-ce qu'un SIG ?

Un système d'information géographique permet d'organiser, de visualiser et de manipuler des informations localisées dans l'espace.

Le principe fondamental peut être résumé ainsi :

> **SIG = géométrie + attributs**

QGIS organise les informations sous forme de **couches superposées**.

Une couche peut représenter :

- des points ;
- des lignes ;
- des polygones ;
- ou d'autres types de données géographiques.

---

## 17.2. Découvrir l'interface de QGIS

Repérez notamment :

- le **canevas cartographique** ;
- le **panneau des couches** ;
- le panneau **Explorateur** ;
- les outils de navigation ;
- la table attributaire ;
- les propriétés d'une couche ;
- les options de symbologie ;
- les informations concernant le système de coordonnées.

---

## 🛠️ Manipulation 1 - Ouvrir et explorer des données

Dans QGIS :

1. ouvrez QGIS et créez un nouveau projet ;
2. ajoutez une couche géographique ;
3. ajoutez un fichier CSV ;
4. affichez et masquez les couches ;
5. modifiez leur ordre ;
6. ouvrez la table attributaire ;
7. sélectionnez un objet sur la carte ;
8. retrouvez l'objet correspondant dans la table ;
9. identifiez la source de la couche ;
10. identifiez son système de référence de coordonnées.

---

# 18. Les principaux formats

Au cours du module, vous rencontrerez notamment :

| Format | Utilisation |
| --- | --- |
| **GeoPackage (.gpkg)** | Format moderne permettant de stocker des données géographiques |
| **GeoJSON (.geojson)** | Format ouvert fréquemment utilisé pour échanger des données géographiques |
| **Shapefile (.shp)** | Format historique encore très répandu |
| **CSV (.csv)** | Tableau de données pouvant contenir ou non des informations de localisation |

> **Attention : un CSV n'est pas automatiquement une couche géographique.**

Pour pouvoir être directement localisé, il doit par exemple contenir des coordonnées ou être relié à une autre couche géographique.

---

# 19. Le système de référence de coordonnées - SCR

Une couche géographique possède généralement un **système de référence de coordonnées (SCR)**.

Le SCR permet à QGIS de savoir comment les coordonnées correspondent à des positions sur la Terre.

À ce stade du cours, l'objectif n'est pas de maîtriser les projections cartographiques.

Vous devez surtout prendre l'habitude de :

- identifier le SCR d'une couche ;
- vérifier qu'il est correctement reconnu ;
- comprendre qu'un problème de SCR peut entraîner une mauvaise localisation ou une mauvaise superposition des données.

> **Premier réflexe dans QGIS : si une couche n'apparaît pas au bon endroit, vérifiez son SCR.**

---

# 20. Créer des données dans QGIS

QGIS permet également de créer ses propres données géographiques.

Pour créer une couche, il faut notamment :

1. choisir un type de géométrie ;
2. définir les champs de la table attributaire ;
3. activer le mode édition ;
4. créer les objets ;
5. renseigner leurs attributs ;
6. enregistrer les modifications.

---

# ✏️ Exercice pratique - Créer une couche de points

Créez une couche contenant **5 à 10 points**.

Vous pouvez par exemple représenter :

- des universités ;
- des ambassades ;
- des institutions européennes ;
- des lieux culturels ;
- des équipements ;
- ou un autre ensemble de lieux de votre choix.

Créez au minimum les champs suivants :

| Champ | Contenu |
| --- | --- |
| **Nom** | Nom du lieu |
| **Catégorie** | Type de lieu |
| **Valeur** | Une valeur numérique |
| **Année** | Année de référence |

Ajoutez ensuite les objets sur la carte et renseignez leurs attributs.

---

# 21. Représenter les données

Une fois les objets créés, testez plusieurs types de représentation.

---

## Symbole unique

Tous les objets sont représentés de la même manière.

Cette représentation permet principalement de montrer leur **localisation**.

---

## Catégorisé

Les objets sont différenciés selon une variable qualitative.

Exemple :

- université ;
- ambassade ;
- institution européenne.

---

## Gradué

Les objets sont représentés selon une progression correspondant à une variable quantitative.

---

## Symboles proportionnels

La taille du symbole varie selon la quantité représentée.

> **Plus la valeur est importante, plus le symbole est grand.**

---

## Étiquettes

Les étiquettes permettent d'afficher certaines informations directement sur la carte, par exemple le **nom des objets**.

---

# 22. Premiers principes de représentation cartographique

Le choix d'une représentation dépend de la **nature de la donnée**.

| Nature de l'information | Représentation possible |
| --- | --- |
| **Catégories sans ordre** | couleurs ou teintes différentes |
| **Valeurs relatives / taux** | progression du clair au foncé |
| **Quantités / stocks** | symboles de tailles différentes |
| **Localisation** | symbole unique |
| **Nom des objets** | étiquettes |

> **Une représentation doit être choisie en fonction de la donnée et du message à transmettre, et pas simplement pour son esthétique.**

---

# 23. Réaliser et exporter sa première carte

## 🎯 Objectif

Transformer le travail réalisé dans QGIS en une **carte lisible et communicable**.

À partir de la couche créée pendant l'exercice, réalisez une première carte comportant au minimum :

- plusieurs objets géographiques ;
- des attributs ;
- une symbologie adaptée ;
- un titre ;
- une légende ;
- la source des données ;
- l'auteur ;
- une mise en page claire.

Selon la carte, vous pourrez également ajouter :

- une échelle ;
- une orientation.

---

## 🗺️ Mise en page dans QGIS

Dans QGIS, ouvrez une **nouvelle mise en page**.

Ajoutez progressivement :

1. la carte ;
2. un titre précis ;
3. une légende ;
4. la source des données ;
5. le nom de l'auteur ;
6. éventuellement une échelle ;
7. éventuellement une flèche du nord.

Vérifiez ensuite la lisibilité générale de la carte.

---

## 📤 Exporter la carte

Une fois la mise en page terminée, exportez votre travail :

- au format **PDF** ;
- ou au format **PNG**.

---

# 🎯 Production attendue en fin de séance

À la fin de cette première journée, vous devez avoir réalisé une **première carte simple sous QGIS** comprenant :

- au moins cinq objets ;
- des informations attributaires ;
- une symbologie adaptée ;
- un titre ;
- une légende ;
- une source ;
- une mise en page lisible.

L'objectif n'est pas encore de réaliser une carte complexe.

Il s'agit de comprendre l'enchaînement général :

> **Données → QGIS → Symbologie → Mise en page → Carte finale**

---

# 📄 Support de cours

Le support général du module est disponible au format PDF.

👉 [**Télécharger le support de cours - Initiation à la cartographie avec QGIS (PDF)**](documents/Initiation_cartographie_M2_EEIMCRI_CYCergy.pdf)

Le support contient la présentation du module ainsi que le contenu détaillé de la **Séance 1 — De la question de recherche aux données cartographiques**.

---

# 🌐 Sites utiles pour la séance 1

Pour rechercher et vérifier vos données :

👉 [**INSEE - Statistiques françaises**](https://www.insee.fr/)

👉 [**Eurostat - Statistiques européennes**](https://ec.europa.eu/eurostat/)

👉 [**World Bank Open Data - Données internationales**](https://data.worldbank.org/)

👉 [**United Nations Statistics Division**](https://unstats.un.org/)

👉 [**data.gouv.fr - Données publiques françaises**](https://www.data.gouv.fr/)

👉 [**Paris Data - Données ouvertes de la Ville de Paris**](https://opendata.paris.fr/)

👉 [**INRAE - Institut national de recherche pour l'agriculture, l'alimentation et l'environnement**](https://www.inrae.fr/)

👉 [**CNRS - Centre national de la recherche scientifique**](https://www.cnrs.fr/)

---

# 💻 Logiciel

Le logiciel utilisé pendant le module est **QGIS**, un système d'information géographique libre et open source.

👉 [**Accéder au site officiel de QGIS**](https://qgis.org/)

👉 [**Télécharger QGIS**](https://qgis.org/download/)

> Il est recommandé de vérifier avant le cours que QGIS est correctement installé et peut être lancé sur votre ordinateur.

---

# 🌐 Site du cours

Les supports, ressources et informations nécessaires au module sont également accessibles sur le site pédagogique :

👉 [**Accéder au site du cours**](https://kadjoraphael.github.io/initiation_cartographie_M2_QGIS/)

---

# ✅ À retenir - Séance 1

À la fin de cette première séance, retenez principalement que :

1. **Une carte commence par une question et non par un logiciel.**

2. Une donnée doit être comprise avant d'être représentée :
   
   **source + date + définition + unité + échelle géographique**

3. Une donnée géographique associe :

   **géométrie + attributs**

4. Les principales géométries vectorielles sont :

   **point + ligne + polygone**

5. Il faut distinguer :

   **données qualitatives / données quantitatives**

6. Pour les données quantitatives, la distinction entre :

   **valeur absolue / valeur relative**

   est essentielle.

7. L'échelle géographique influence l'analyse.

8. Un **identifiant géographique** permet de relier des données statistiques à des territoires.

9. Dans QGIS, les informations sont organisées sous forme de **couches**.

10. La représentation doit être choisie en fonction de la **nature de la donnée** et du message que l'on souhaite transmettre.

11. Une carte destinée à être communiquée doit être correctement **mise en page et documentée**.

---

## 🧭 Le chemin parcouru

**Question**

↓

**Recherche des données**

↓

**Compréhension et vérification**

↓

**Donnée géographique**

↓

**QGIS**

↓

**Symbologie**

↓

**Mise en page**

↓

**Première carte**

---

## ➡️ Pour préparer la suite

Conservez les informations concernant votre **projet cartographique personnel**.

Avant la prochaine séance, essayez notamment d'identifier :

- votre phénomène ;
- votre territoire ;
- votre période ;
- une ou plusieurs sources possibles ;
- les données dont vous aurez besoin ;
- l'échelle géographique des données ;
- un éventuel identifiant géographique.

Vous n'avez pas besoin d'avoir terminé votre projet : il sera construit progressivement pendant le module.
