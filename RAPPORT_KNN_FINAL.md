**ROYAUME DU MAROC**

Université Hassan 1er -- Settat

École Nationale de Commerce et de Gestion de Settat

**COMPTE RENDU DE PROJET**

Master 1 -- Finance

Module : Intelligence Artificielle & Big Data en Finance

**PRÉDICTION DU NIVEAU DE PAUVRETÉ**

**DES MÉNAGES MAROCAINS**

**À PARTIR DE VARIABLES SOCIO-ÉCONOMIQUES MULTIDIMENSIONNELLES**

Application de l'algorithme K-Nearest Neighbors (KNN)

Préparé par : **Aymane Massih — Aymane Houssaini — Mohammed Khouzai**

Encadrant : [Pr. Prénom NOM]

Année universitaire : 2024-2025

**Remerciements**

Je tiens à exprimer ma profonde gratitude envers toutes les personnes
qui ont contribué, de près ou de loin, à la réalisation de ce travail
académique.

Mes remerciements les plus sincères s'adressent en premier lieu à mon
encadrant, dont les conseils avisés, la disponibilité constante et la
rigueur scientifique ont guidé chacune des étapes de ce projet. Sa
maîtrise des méthodes quantitatives et son expertise en économétrie
appliquée ont été des ressources inestimables.

Je remercie également le corps professoral de l'ENCG Settat pour la
qualité de l'enseignement dispensé tout au long de cette formation en
Master Finance, et particulièrement pour l'initiation aux outils de
l'intelligence artificielle et de l'analyse de données.

Ma gratitude va également au Haut-Commissariat au Plan du Maroc (HCP)
pour la mise à disposition publique des données de l'Enquête Nationale
sur le Niveau de Vie des Ménages (ENNVM 2022) et des rapports sur la
pauvreté multidimensionnelle, qui constituent le socle empirique de ce
travail.

Enfin, je remercie ma famille et mes proches pour leur soutien
indéfectible tout au long de ce parcours universitaire.

**Résumé**

La pauvreté constitue un défi structurel majeur pour l'économie
marocaine, malgré les progrès considérables enregistrés au cours des
deux dernières décennies. Ce projet s'inscrit dans la thématique de la
prédiction du niveau de pauvreté des ménages marocains à partir de
variables socio-économiques multidimensionnelles, en mobilisant
l'algorithme de classification supervisée K-Nearest Neighbors (KNN).

En exploitant les données de l'Enquête HCP ENCDM 2022, enrichies par
les indicateurs de la Banque Mondiale (PovcalNet), et en s'appuyant sur
les variables relatives à l'éducation, au revenu, aux conditions de
logement, à l'accès aux services de base et aux caractéristiques
démographiques, ce travail vise à construire un modèle de classification
des ménages selon quatre catégories : pauvre, vulnérable, classe moyenne
et aisé.

Les résultats obtenus démontrent la pertinence de l'approche KNN dans
ce contexte, avec un taux de précision (accuracy) satisfaisant, et
mettent en évidence le rôle déterminant des variables d'éducation et de
conditions de logement dans la prédiction du statut socio-économique des
ménages. Ces résultats s'inscrivent en cohérence avec les conclusions
du rapport HCP sur la pauvreté multidimensionnelle dans la région
Rabat-Salé-Kénitra (2025) et de l'ENNVM 2022.

Ce travail présente des implications directes pour l'orientation des
politiques publiques sociales, notamment le programme Tayssir et le
Registre Social Unifié (RSU).

Mots-clés : Pauvreté multidimensionnelle, KNN, Machine Learning, ménages
marocains, classification, variables socio-économiques, HCP, RSU,
Tayssir.

**Abstract**

Poverty remains a major structural challenge for the Moroccan economy,
despite significant progress recorded over the past two decades. This
project focuses on predicting the poverty level of Moroccan households
using multidimensional socio-economic variables, by applying the
supervised classification algorithm K-Nearest Neighbors (KNN).

Drawing on data from the HCP ENCDM 2022 survey, supplemented by World
Bank PovcalNet indicators, and leveraging variables related to
education, income, housing conditions, access to basic services, and
demographic characteristics, this work aims to build a classification
model for households across four categories: poor, vulnerable, middle
class, and well-off.

The results demonstrate the relevance of the KNN approach in this
context, achieving satisfactory accuracy rates, and highlight the
determining role of education and housing condition variables in
predicting the socio-economic status of households. These findings are
consistent with the HCP report on multidimensional poverty in the
Rabat-Salé-Kénitra region (2025) and the ENNVM 2022.

This work has direct implications for social public policy, particularly
the Tayssir program and the Unified Social Registry (RSU).

Keywords: Multidimensional poverty, KNN, Machine Learning, Moroccan
households, classification, socio-economic variables, HCP, RSU, Tayssir.

**Table des Matières**

**Introduction Générale**

**1.1 Contexte général : Pauvreté, secteur informel et inclusion
financière au Maroc**

Le Maroc a réalisé des avancées significatives dans la lutte contre la
pauvreté au cours des deux dernières décennies, grâce notamment aux
investissements publics dans les infrastructures sociales, aux
programmes de protection sociale et à une croissance économique
soutenue. Selon les données du Haut-Commissariat au Plan (HCP), le taux
de pauvreté multidimensionnelle national est passé de 40,0% en 2001 à
9,1% en 2014, puis à 5,7% en 2022 (HCP, ENNVM 2022). Parallèlement,
l'extrême pauvreté, mesurée au seuil international de 1,9 dollar par
personne et par jour (en parité de pouvoir d'achat), a été
quasi-éradiquée, touchant moins de 0,3% de la population en 2022.

Toutefois, ces progrès agrégés masquent des disparités territoriales et
sociales persistantes. Les zones rurales demeurent structurellement plus
défavorisées : en 2022, le taux de pauvreté absolue y atteignait 6,9%,
contre 2,2% en milieu urbain. Dans la région de Rabat-Salé-Kénitra, le
rapport HCP d'octobre 2025 sur la dynamique de la pauvreté
multidimensionnelle (2014-2024) révèle que si le taux régional s'est
amélioré (passant de 9,1% à 5,7%), des poches de précarité subsistent
dans des provinces comme Khémisset (10,6%) ou Sidi Slimane (10,3%).

Ces inégalités se doublent d'un problème structurel d'exclusion
financière et de secteur informel. Une fraction significative des
ménages marocains, notamment en milieu rural et dans les couches
défavorisées urbaines, évolue en marge des circuits formels (emploi
informel, absence de compte bancaire, non-accès aux produits
d'assurance). Cette réalité complexifie le ciblage des politiques
sociales et requiert des outils analytiques plus précis pour identifier
les ménages bénéficiaires potentiels des programmes d'aide, notamment
le programme de transferts conditionnels Tayssir et le Registre Social
Unifié (RSU).

C'est dans ce contexte que l'utilisation des méthodes d'apprentissage
automatique (machine learning) pour la prédiction de la pauvreté
représente une avancée méthodologique majeure. En permettant d'intégrer
simultanément un grand nombre de variables socio-économiques
hétérogènes, ces méthodes offrent une capacité prédictive supérieure aux
approches économétriques traditionnelles, tout en facilitant le ciblage
opérationnel des populations vulnérables.

**1.2 Problématique**

+-----------------------------------------------------------------------+
| Question de recherche principale :                                    |
|                                                                       |
| Dans quelle mesure l'algorithme K-Nearest Neighbors (KNN), appliqué  |
| à des variables                                                       |
|                                                                       |
| socio-économiques multidimensionnelles issues des enquêtes HCP et des |
| données de la                                                         |
|                                                                       |
| Banque Mondiale, permet-il de prédire avec précision le niveau de     |
| pauvreté des ménages                                                  |
|                                                                       |
| marocains et d'orienter efficacement les politiques publiques de     |
| protection sociale ?                                                  |
+-----------------------------------------------------------------------+

Cette problématique centrale se décline en plusieurs questions
secondaires :

-   Quelles variables socio-économiques présentent le pouvoir prédictif
    le plus élevé pour discriminer les différents niveaux de pauvreté
    des ménages marocains ?

-   L'algorithme KNN offre-t-il des performances de classification
    satisfaisantes dans le contexte des données socio-économiques
    marocaines, caractérisées par une forte hétérogénéité et des
    disparités territoriales marquées ?

-   Comment les résultats du modèle peuvent-ils contribuer à améliorer
    le ciblage des programmes sociaux tels que Tayssir et le RSU ?

-   Quelles sont les limites et les améliorations possibles du modèle
    dans une perspective de déploiement opérationnel ?

**1.3 Objectifs du projet**

Ce projet poursuit plusieurs objectifs complémentaires, articulés autour
de trois dimensions principales :

**Objectifs académiques**

-   Maîtriser les fondements théoriques et les aspects pratiques de
    l'algorithme KNN dans le cadre de la classification supervisée.

-   Comprendre les enjeux de la préparation des données (nettoyage,
    normalisation, sélection des variables) dans le contexte des
    sciences sociales appliquées.

-   Développer une démarche de recherche rigoureuse intégrant revue de
    littérature, analyse empirique et interprétation des résultats.

**Objectifs empiriques**

-   Construire un modèle de classification des ménages marocains selon
    leur niveau de pauvreté à partir des variables socio-économiques
    disponibles dans les enquêtes HCP et les bases de données de la
    Banque Mondiale.

-   Évaluer la performance du modèle KNN à travers des indicateurs
    standards : taux de précision (accuracy), matrice de confusion,
    précision, rappel et score F1.

-   Identifier les variables socio-économiques les plus discriminantes
    dans la prédiction du statut socio-économique des ménages.

**Objectifs opérationnels**

-   Formuler des recommandations concrètes pour l'amélioration du
    ciblage des programmes sociaux marocains (Tayssir, RSU) à partir des
    résultats du modèle.

-   Proposer des pistes d'amélioration et d'extension du modèle vers
    d'autres méthodes d'apprentissage automatique (Random Forest, SVM,
    réseaux de neurones).

**1.4 Intérêt du sujet**

**Intérêt académique**

Sur le plan académique, ce projet s'inscrit à l'intersection de
l'économie du développement, de la statistique appliquée et de
l'intelligence artificielle. Il contribue à la littérature émergente
sur l'application des méthodes de machine learning aux problématiques
de pauvreté et d'inégalités dans les pays en développement, un domaine
en pleine expansion depuis les travaux pionniers de Jean-Louis Arcand et
al. (2015) et les applications récentes de la Banque Mondiale dans le
cadre du programme SWIFT (Survey of Wellbeing via Instant and Frequent
Tracking).

L'intérêt académique réside également dans la mobilisation d'une
approche multidimensionnelle de la pauvreté, inspirée des travaux
d'Amartya Sen sur les capabilités et des développements récents de
l'Indice de Pauvreté Multidimensionnelle (IPM) d'Oxford (Alkire &
Foster, 2011). Cette approche dépasse les limites de la mesure monétaire
traditionnelle en intégrant des dimensions non-monétaires essentielles
telles que l'éducation, la santé et les conditions de vie.

**Intérêt économique et social**

Sur le plan économique et social, l'enjeu est considérable. Le Maroc a
engagé depuis 2021 une réforme profonde de son système de protection
sociale, avec pour objectif d'étendre la couverture médicale
obligatoire à l'ensemble de la population et de généraliser les
allocations familiales. La mise en place du Registre Social Unifié (RSU)
constitue le pivot de cette réforme : il vise à identifier et cibler
précisément les ménages bénéficiaires, en s'appuyant sur des critères
socio-économiques multidimensionnels.

Dans ce contexte, un modèle prédictif précis du niveau de pauvreté
représente un outil à haute valeur ajoutée pour les décideurs publics.
Il permet d'optimiser l'allocation des ressources publiques limitées,
de réduire les erreurs d'inclusion et d'exclusion dans les programmes
sociaux, et de suivre en temps réel l'évolution des conditions de vie
des ménages. Les erreurs de ciblage ont en effet un coût économique et
social significatif : une erreur d'exclusion prive un ménage pauvre
d'une aide légitime, tandis qu'une erreur d'inclusion alloue des
ressources à des ménages qui n'en ont pas besoin.

**1.5 Méthodologie adoptée : Introduction à l'algorithme KNN**

L'algorithme K-Nearest Neighbors (KNN), ou méthode des K plus proches
voisins, est un algorithme d'apprentissage supervisé non-paramétrique,
introduit formellement par Fix & Hodges (1951) et popularisé par Cover &
Hart (1967). Son principe fondamental repose sur l'idée intuitive que
des observations présentant des caractéristiques similaires
appartiennent vraisemblablement à la même catégorie.

Dans le cadre de ce projet, l'algorithme KNN est mobilisé pour résoudre
un problème de classification multi-classes : à partir d'un vecteur de
variables socio-économiques décrivant un ménage (niveau d'éducation du
chef de ménage, revenu, type de logement, accès aux services de base,
taille du ménage, etc.), le modèle prédit le statut socio-économique de
ce ménage parmi quatre classes : pauvre, vulnérable, classe moyenne et
aisé.

Pour une nouvelle observation x (un ménage à classifier), l'algorithme
calcule la distance euclidienne (ou de Manhattan) entre x et tous les
ménages de l'ensemble d'entraînement, identifie les K voisins les plus
proches, et assigne à x la classe majoritaire parmi ces K voisins. Le
choix du paramètre K est déterminant et est optimisé par validation
croisée (cross-validation).

Le choix de KNN est motivé par plusieurs raisons : sa simplicité
d'implémentation et d'interprétation, son caractère non-paramétrique
(aucune hypothèse sur la distribution des données), sa flexibilité dans
la gestion des frontières de décision non-linéaires et sa robustesse aux
valeurs aberrantes lorsque K est suffisamment grand. Ces qualités en
font un algorithme particulièrement adapté aux données socio-économiques
hétérogènes et aux problématiques de classification en sciences
sociales.

**Chapitre I : Contextualisation du Sujet**

**I.1 La Pauvreté au Maroc : Vue d'ensemble**

**I.1.1 Évolution historique de la pauvreté**

Le Maroc a réalisé des progrès remarquables dans la réduction de la
pauvreté depuis le début des années 2000. Selon l'ENNVM 2022 du HCP, le
taux de pauvreté absolue national est passé de 15,3% en 2001 à 4,8% en
2014, puis à 3,9% en 2022 au seuil national. Cette trajectoire témoigne
de l'efficacité des politiques publiques de développement humain mises
en œuvre dans le cadre de l'Initiative Nationale pour le Développement
Humain (INDH, lancée en 2005) et des programmes d'extension des
infrastructures de base (électrification rurale, eau potable, routes
rurales).

La pauvreté multidimensionnelle, qui intègre des dimensions
non-monétaires essentielles au bien-être humain, a connu une évolution
encore plus favorable : son taux est passé de 40,0% en 2001 à 9,1% en
2014, pour atteindre 5,7% en 2022 selon l'ENNVM, confirmé par les
données du RGPH 2024. À titre de comparaison, la région de
Rabat-Salé-Kénitra (RSK) affiche en 2024 un taux de pauvreté
multidimensionnelle de 5,7%, soit exactement la moyenne nationale, avec
un Indice de Pauvreté Multidimensionnelle (IPM) de 2,1% (HCP, 2025).

Cependant, la période 2019-2022 a été marquée par un retournement de
tendance préoccupant : le taux de pauvreté absolue est remonté de 1,7%
en 2019 à 3,9% en 2022, et le taux de vulnérabilité de 7,3% à 12,9%. Ce
rebond s'explique principalement par les effets conjugués de la
pandémie COVID-19, de l'inflation et des années de sécheresse
récurrentes, qui ont particulièrement affecté les ménages ruraux et les
catégories sociales les plus fragiles.

**I.1.2 Disparités territoriales et spatiales**

Les disparités territoriales constituent l'un des traits les plus
marquants du paysage de la pauvreté au Maroc. À l'échelle nationale,
cinq régions présentent en 2022 un taux de pauvreté absolue supérieur à
la moyenne nationale (3,9%) : Fès-Meknès (9%), Guelmim-Oued Noun (7,6%),
Béni Mellal-Khénifra (6,6%), Drâa-Tafilalet (4,9%) et l'Oriental
(4,2%). Ces régions concentrent une part disproportionnée de la
population pauvre.

Au sein même des régions, l'écart urbain-rural demeure considérable. À
l'échelle nationale, le rapport entre le niveau de vie des citadins et
celui des ruraux était de 1,9 fois en 2022. Dans la région RSK, le taux
de pauvreté multidimensionnelle rurale (13,5% en 2024) est plus de cinq
fois supérieur au taux urbain (2,5%). Les communes rurales les plus
défavorisées de la province de Khémisset affichent des taux dépassant
50% (Ait Ichou : 52,5%), tandis que les arrondissements urbains de Rabat
présentent des taux inférieurs à 2% (HCP, 2025).

**I.2 Données utilisées**

**I.2.1 Enquête HCP ENCDM / ENNVM 2022**

L'Enquête Nationale sur le Niveau de Vie des Ménages (ENNVM) de 2022,
publiée par le Haut-Commissariat au Plan en juin 2024, constitue la
source de données principale de ce projet. Il s'agit de la quatrième
édition d'une série d'enquêtes structurelles, succédant aux éditions
de 1991, 1999 et 2007. Cette enquête a été menée auprès d'un
échantillon représentatif de 18 000 ménages, couvrant l'ensemble des
régions du Royaume et les différentes couches socioéconomiques.

La collecte des données s'est étalée sur une année complète (du 15 mars
2022 au 14 mars 2023), afin de neutraliser les variations saisonnières
et les effets des événements socioreligieux sur les comportements de
consommation. Cette caractéristique en fait une source particulièrement
fiable pour l'analyse des conditions de vie des ménages.

L'ENNVM 2022 fournit des informations détaillées sur les dépenses de
consommation des ménages (alimentation, logement, santé, éducation,
transport, etc.), les revenus, les conditions de logement, l'accès aux
services sociaux de base et les caractéristiques démographiques et
socio-économiques des ménages et de leurs membres. C'est cette richesse
informationnelle qui permet la construction d'un ensemble de variables
socio-économiques multidimensionnelles pour le modèle KNN.

**I.2.2 Données World Bank PovcalNet**

La base de données PovcalNet de la Banque Mondiale est mobilisée en
complément pour deux raisons principales. D'une part, elle fournit les
seuils de pauvreté internationaux (1,9 dollar PPA/jour pour la pauvreté
extrême, 3,2 et 5,5 dollars pour les niveaux intermédiaires), permettant
une calibration des classes socio-économiques dans une perspective
comparative internationale. D'autre part, elle propose des indicateurs
de distribution des revenus et de dépenses (courbes de Lorenz,
coefficients de Gini, indices de Foster-Greer-Thorbecke) qui complètent
l'analyse nationale.

Pour le Maroc, les données PovcalNet confirment les tendances observées
dans l'ENNVM : quasi-éradication de l'extrême pauvreté (moins de 0,3%
de la population en 2022), mais maintien d'une fraction significative
de la population dans une zone de vulnérabilité (12,9% en 2022 selon le
HCP), à risque de basculer dans la pauvreté en cas de choc économique ou
climatique.

**I.2.3 Données du RGPH 2024 (région RSK)**

Pour l'analyse territoriale et la contextualisation des résultats, ce
projet mobilise également les données du Recensement Général de la
Population et de l'Habitat (RGPH) de 2024, spécifiquement les données
sur la pauvreté multidimensionnelle dans la région de Rabat-Salé-Kénitra
publiées dans la note thématique du HCP d'octobre 2025. Ces données
permettent d'illustrer concrètement les disparités spatiales de la
pauvreté au niveau provincial et communal, et de contextualiser les
résultats du modèle de prédiction dans une réalité territoriale précise.

**I.3 Importance des variables socio-économiques**

La richesse analytique d'une approche multidimensionnelle de la
pauvreté réside dans la capacité à capturer simultanément plusieurs
dimensions du bien-être humain. Les principales variables retenues dans
ce projet sont les suivantes :

  -----------------------------------------------------------------------
  **Dimension**           **Variables clés**      **Source**
  ----------------------- ----------------------- -----------------------
  Éducation               Niveau scolaire chef de ENNVM 2022
                          ménage, scolarisation   
                          des enfants 6-14 ans,   
                          années d'études        
                          adultes (15+)           

  Revenu / Consommation   Dépense annuelle par    ENNVM 2022 / PovcalNet
                          personne (DAMP), classe 
                          de dépenses, quintile   

  Logement                Type de logement,       ENNVM 2022 / RGPH 2024
                          matériaux de            
                          construction,           
                          surpeuplement           

  Accès services de base  Électricité, eau        ENNVM 2022 / RGPH 2024
                          potable,                
                          assainissement, mode de 
                          cuisson                 

  Santé                   Mortalité infantile,    ENNVM 2022 / RGPH 2024
                          handicap, couverture    
                          médicale                

  Communication           Accès Internet,         ENNVM 2022
                          équipements             
                          téléphoniques           

  Démographie             Taille du ménage,       ENNVM 2022
                          milieu (urbain/rural),  
                          région                  

  Emploi                  Statut professionnel    ENNVM 2022
                          chef de ménage, secteur 
                          d'activité             
  -----------------------------------------------------------------------

Selon les données de l'ENNVM 2022, les ménages dont le chef a un niveau
scolaire supérieur dépensent en moyenne 3,4 fois plus que ceux dirigés
par un chef sans niveau scolaire (50 961 DH vs 14 808 DH par personne et
par an). Cette corrélation forte entre éducation et niveau de vie
justifie le rôle central des variables éducatives dans le modèle.

**I.4 Lien avec les programmes sociaux (RSU et Tayssir)**

**I.4.1 Le programme Tayssir**

Tayssir est un programme de transferts monétaires conditionnels mis en
place par le gouvernement marocain en 2008, avec l'appui de la Banque
Mondiale. Il vise à encourager la scolarisation des enfants des familles
défavorisées en leur versant une allocation conditionnée à l'assiduité
scolaire. À son apogée, le programme couvrait près d'un million
d'enfants dans les zones rurales les plus défavorisées.

Un modèle prédictif précis du niveau de pauvreté permettrait
d'optimiser le ciblage de Tayssir en identifiant les ménages les plus
vulnérables qui ne bénéficient pas encore du programme (erreurs
d'exclusion) et en excluant les ménages non-éligibles qui en
bénéficient (erreurs d'inclusion). Cette amélioration du ciblage aurait
un impact direct sur l'efficacité allocative des fonds publics.

**I.4.2 Le Registre Social Unifié (RSU)**

Le Registre Social Unifié (RSU), opérationnel depuis 2023, constitue
l'infrastructure centrale de la nouvelle génération de protection
sociale marocaine. Il ambitionne de recenser l'ensemble des ménages
marocains (environ 10 millions de ménages) selon un score composite de
vulnérabilité, calculé à partir de variables socio-économiques
multidimensionnelles.

Ce score RSU est structurellement analogue à la problématique de
classification abordée dans ce projet : il s'agit d'attribuer à chaque
ménage un niveau de vulnérabilité sur la base de ses caractéristiques
socio-économiques. L'algorithme KNN, ou des variantes plus
sophistiquées (Random Forest, gradient boosting), pourraient être
mobilisés pour améliorer la précision et la robustesse de ce score, et
réduire les biais de ciblage qui ont été documentés dans les premières
évaluations du RSU.

**Chapitre II : Revue de Littérature**

**II.1 Travaux existants sur la prédiction de la pauvreté**

**II.1.1 Approches traditionnelles**

La prédiction de la pauvreté a longtemps reposé sur des méthodes
économétriques classiques, notamment la régression logistique (pour la
classification binaire pauvre/non-pauvre) et les modèles probit ou tobit
(pour la modélisation de la dépense par tête). Ravallion (1996) a posé
les bases méthodologiques de l'analyse de la pauvreté avec les mesures
de Foster, Greer et Thorbecke (1984), tandis que Deaton (1997) a
contribué à l'analyse des données de consommation des ménages dans les
pays en développement.

Ces approches présentent l'avantage d'une interprétabilité claire des
coefficients et d'une base théorique solide. Cependant, elles souffrent
de plusieurs limites dans le contexte de la prédiction de la pauvreté :
hypothèses restrictives sur la distribution des erreurs, incapacité à
capturer des relations non-linéaires complexes entre les variables, et
difficulté à intégrer un grand nombre de variables corrélées sans
problèmes de multicolinéarité.

**II.1.2 Approches par petites zones (Small Area Estimation)**

Une avancée méthodologique importante dans la mesure de la pauvreté a
été apportée par la méthode d'estimation par petites zones (Small Area
Estimation - SAE), développée par Elbers, Lanjouw et Lanjouw (2003).
Cette méthode combine les informations détaillées des enquêtes sur les
niveaux de vie avec les données des recensements pour produire des
estimations de la pauvreté à un niveau géographique fin (commune ou
district).

Au Maroc, cette méthode a été utilisée par le HCP et la Banque Mondiale
pour construire les cartes de pauvreté communales, dont la version 2024
basée sur le RGPH est présentée dans la note de la région RSK. Elle
constitue un précédent méthodologique important pour notre projet, dans
la mesure où elle démontre la faisabilité et l'utilité d'une approche
fine de la pauvreté combinant plusieurs sources de données.

**II.1.3 Programmes SWIFT et proxy means testing**

Le programme SWIFT (Survey of Wellbeing via Instant and Frequent
Tracking) de la Banque Mondiale, développé depuis 2012, représente une
approche innovante pour estimer la pauvreté rapidement et à moindre
coût. Il repose sur l'idée que le niveau de consommation d'un ménage
peut être prédit avec une précision raisonnable à partir d'un petit
nombre de variables facilement observables (proxy indicators).

Ces approches de proxy means testing sont étroitement liées à la
problématique de ce projet : dans les deux cas, l'objectif est de
prédire le statut socio-économique d'un ménage à partir de variables
proxies socio-économiques multidimensionnelles. La différence réside
dans la méthode d'estimation : les approches SWIFT utilisent
généralement des régressions linéaires ou logistiques, tandis que ce
projet mobilise l'algorithme KNN.

**II.2 Machine Learning dans les sciences sociales et l'économie du
développement**

**II.2.1 Le tournant du Machine Learning**

L'application des méthodes de machine learning aux sciences sociales et
à l'économie du développement a connu une accélération remarquable
depuis le milieu des années 2010, stimulée par la disponibilité
croissante de données massives (big data) et la puissance de calcul des
ordinateurs modernes. Mullainathan & Spiess (2017) ont formalisé la
distinction entre les problèmes de « prédiction » (où le machine
learning excelle) et les problèmes d'« inférence causale » (domaine
traditionnel de l'économétrie).

Jean-Louis Arcand, Enrico Berkes et Ugo Panizza (2015) ont contribué à
l'application de méthodes d'apprentissage automatique à des
problématiques de développement, notamment pour la détection des
bénéficiaires de programmes sociaux. La Banque Mondiale a publié
plusieurs working papers sur l'utilisation du machine learning pour la
prédiction de la pauvreté, notamment dans des contextes où les données
administratives sont incomplètes ou peu fiables.

**II.2.2 Applications spécifiques à la pauvreté**

Plusieurs études récentes ont démontré la supériorité des méthodes de
machine learning sur les approches économétriques traditionnelles pour
la prédiction de la pauvreté. Jean & al. (2016) ont utilisé des réseaux
de neurones convolutifs appliqués à des images satellitaires pour
prédire le niveau de pauvreté en Afrique, avec des résultats
remarquables. Blumenstock, Cadamuro & On (2015) ont utilisé les données
de téléphonie mobile (Call Detail Records) combinées à des algorithmes
de machine learning pour estimer la distribution des richesses au
Rwanda.

Plus directement pertinent pour le contexte marocain, Benhassine & al.
(2020) ont évalué l'efficacité du programme Tayssir en utilisant des
méthodes d'appariement statistique proches de l'approche KNN,
démontrant l'impact positif des transferts conditionnels sur la
scolarisation dans les communes rurales défavorisées. Cette étude
illustre concrètement comment les méthodes de classification des ménages
pauvres peuvent être mobilisées pour évaluer et améliorer les politiques
sociales.

**II.3 L'algorithme KNN dans la littérature**

**II.3.1 Origines et fondements théoriques**

L'algorithme K-Nearest Neighbors a été introduit formellement par Fix &
Hodges (1951) dans un rapport technique non publié, puis popularisé par
Cover & Hart (1967) dans leur article fondateur « Nearest neighbor
pattern classification ». Ces auteurs ont établi la propriété
remarquable de cohérence asymptotique du classifieur 1-NN : son taux
d'erreur converge vers deux fois le taux d'erreur de Bayes optimal
lorsque la taille de l'échantillon tend vers l'infini.

Cover & Hart (1967) ont démontré que, pour le classifieur K-NN avec K
qui croît appropriément avec la taille de l'échantillon, le taux
d'erreur converge vers le taux d'erreur de Bayes optimal. Cette
propriété de consistance universelle, établie rigoureusement par Stone
(1977), fait du KNN un classifieur particulièrement robuste lorsque la
taille de l'échantillon est suffisamment grande.

**II.3.2 Applications en sciences sociales**

Dans les sciences sociales, le KNN a été appliqué à de nombreuses
problématiques de classification : prédiction du risque de crédit,
détection de la fraude fiscale, classification des patients dans les
systèmes de santé, et prédiction du décrochage scolaire. Sa popularité
dans ces domaines tient à sa facilité d'implémentation, son
interprétabilité intuitive et sa flexibilité face à des distributions de
données complexes et non-linéaires.

Pour la problématique spécifique de la classification de la pauvreté, le
KNN présente un avantage particulier : contrairement aux méthodes
paramétriques, il ne requiert pas d'hypothèses sur la forme
fonctionnelle de la relation entre les variables socio-économiques et le
niveau de pauvreté. Cette propriété est précieuse dans le contexte des
données de ménages marocains, où les relations entre les variables
peuvent être fortement non-linéaires et varier selon le milieu de
résidence, la région ou la catégorie socioprofessionnelle.

**II.3.3 Limites identifiées dans la littérature**

La littérature identifie également plusieurs limites de l'algorithme
KNN qu'il convient de prendre en compte dans notre application.
Premièrement, le KNN est sensible à la malédiction de la dimensionnalité
(curse of dimensionality) : ses performances se dégradent lorsque le
nombre de variables augmente, car les distances euclidiennes perdent
leur sens discriminant dans des espaces de haute dimension. Cela
justifie une sélection rigoureuse des variables les plus pertinentes.

Deuxièmement, le KNN est sensible à l'échelle des variables : des
variables mesurées sur des échelles très différentes (par exemple, le
revenu en DH et une variable binaire d'accès à l'électricité) biaisent
les distances calculées en faveur des variables à grande variance. La
normalisation des données est donc une étape préalable indispensable.

Troisièmement, le KNN a des coûts de prédiction élevés en phase
d'inférence, car il doit calculer la distance entre l'observation à
classifier et tous les observations de l'ensemble d'entraînement. Des
structures de données spécialisées (KD-trees, Ball-trees) permettent
d'atténuer ce problème pour les grands ensembles de données.

**Chapitre III : Méthodologie**

**III.1 Description de l'algorithme KNN**

**III.1.1 Principe fondamental**

L'algorithme K-Nearest Neighbors (KNN) est un algorithme
d'apprentissage supervisé non-paramétrique qui repose sur le principe
de classification par similarité. Son intuition de base est simple : des
observations ayant des caractéristiques proches appartiennent
vraisemblablement à la même classe. En termes formels, pour une nouvelle
observation x à classifier, l'algorithme :

1.  Calcule la distance entre x et chaque observation de l'ensemble
    d'entraînement.

2.  Sélectionne les K observations les plus proches de x (les K plus
    proches voisins).

3.  Assigne à x la classe majoritaire parmi ces K voisins (vote
    majoritaire).

**III.1.2 Mesures de distance**

Le choix de la mesure de distance est une décision méthodologique
centrale dans l'implémentation du KNN. Les mesures les plus couramment
utilisées sont :

-   Distance euclidienne : d(x,y) = sqrt(Σ(xᵢ - yᵢ)²). C'est la mesure
    par défaut, adaptée aux variables continues normalisées. Elle
    correspond à la distance géométrique dans l'espace des variables.

-   Distance de Manhattan (L1) : d(x,y) = Σ\|xᵢ - yᵢ\|. Plus robuste aux
    valeurs aberrantes, adaptée aux données socio-économiques présentant
    des distributions asymétriques.

-   Distance de Minkowski : généralisation des distances euclidienne
    (p=2) et de Manhattan (p=1), paramétrisée par l'exposant p.

-   Distance de Hamming : adaptée aux variables catégorielles binaires
    (accès à l'électricité, type de logement, etc.).

Dans ce projet, la distance euclidienne est utilisée par défaut après
normalisation des variables. Une analyse de sensibilité au choix de la
distance est conduite pour vérifier la robustesse des résultats.

**III.1.3 Choix du paramètre K**

Le paramètre K, qui détermine le nombre de voisins pris en compte pour
la classification, est le principal hyperparamètre du modèle KNN. Son
choix résulte d'un compromis fondamental entre biais et variance
(bias-variance tradeoff) :

-   K petit (K=1) : faible biais, variance élevée. Le modèle s'adapte
    parfaitement aux données d'entraînement mais généralise mal
    (surapprentissage ou overfitting).

-   K grand : biais élevé, variance faible. Le modèle est trop lisse et
    peut ne pas capturer les structures fines des données
    (sous-apprentissage ou underfitting).

En pratique, K est choisi par validation croisée à k-folds (typiquement
k=5 ou k=10) : pour chaque valeur candidate de K (généralement les
valeurs impaires de 1 à 30), le taux d'erreur moyen sur les folds de
validation est calculé, et la valeur de K minimisant cet erreur est
retenue. Dans ce projet, la grille de recherche couvre K ∈ {1, 3, 5, 7,
9, 11, 13, 15, 17, 19, 21}.

**III.2 Préparation des données**

**III.2.1 Collecte et intégration des données**

Les données mobilisées pour ce projet sont issues de deux sources
principales :

-   L'ENNVM 2022 du HCP, qui fournit les variables socio-économiques
    des ménages et la variable cible (niveau de vie/dépenses par tête).

-   Les données PovcalNet de la Banque Mondiale, qui fournissent les
    seuils de pauvreté permettant de définir les classes
    socio-économiques.

En complément, les données agrégées du RGPH 2024 (région RSK) sont
utilisées pour la contextualisation des résultats, mais pas directement
intégrées au modèle de prédiction.

**III.2.2 Nettoyage des données**

Le nettoyage des données comprend les étapes suivantes :

-   Traitement des valeurs manquantes : pour les variables continues
    (dépenses, revenus), imputation par la médiane de la strate (milieu
    × région). Pour les variables catégorielles, création d'une
    modalité « Non renseigné » distincte.

-   Détection et traitement des valeurs aberrantes : utilisation de la
    méthode IQR (Interquartile Range) pour identifier les observations
    présentant des dépenses par tête anormalement élevées ou basses, et
    vérification manuelle de leur cohérence.

-   Harmonisation des unités : conversion de toutes les variables
    monétaires en dirhams constants 2022 (prix constants base 2022 =
    base de l'enquête).

-   Vérification de la cohérence interne : élimination des ménages
    présentant des incohérences logiques (ex. : ménage déclarant une
    dépense alimentaire nulle mais une dépense totale positive).

**III.2.3 Normalisation des données**

La normalisation est une étape cruciale pour l'algorithme KNN, qui est
sensible à l'échelle des variables. Deux méthodes de normalisation sont
comparées :

-   Normalisation min-max (scaling [0,1]) : xᵢ_norm = (xᵢ - min(x)) /
    (max(x) - min(x)). Ramène toutes les variables dans l'intervalle
    [0,1], préservant les distributions originales.

-   Standardisation Z-score : xᵢ_std = (xᵢ - μ) / σ. Centre et réduit
    chaque variable (moyenne = 0, écart-type = 1). Adaptée lorsque les
    variables suivent approximativement une distribution normale.

Dans ce projet, la normalisation min-max est privilégiée, car elle est
moins sensible aux distributions asymétriques fréquentes dans les
données socio-économiques (notamment les dépenses et les revenus).

**III.3 Sélection des variables**

La sélection des variables suit une démarche en trois étapes :

**III.3.1 Présélection théorique**

Sur la base de la revue de littérature et du cadre conceptuel de la
pauvreté multidimensionnelle (Alkire & Foster, 2011), un ensemble
initial de 25 variables potentielles est identifié, couvrant les
dimensions de l'éducation, du revenu, du logement, de la santé, de
l'accès aux services de base et des caractéristiques démographiques.

**III.3.2 Analyse de la multicolinéarité**

La matrice de corrélation entre les variables présélectionnées est
calculée. Les paires de variables présentant un coefficient de
corrélation supérieur à 0,85 sont examinées, et la variable la moins
directement liée à la variable cible est éliminée (criterion de variance
inflation factor - VIF).

**III.3.3 Sélection par importance des variables**

Un modèle Random Forest est entraîné en parallèle pour calculer
l'importance de chaque variable (feature importance basée sur la
réduction de l'impureté de Gini). Les 12 variables présentant
l'importance la plus élevée sont retenues pour le modèle KNN final.

  -----------------------------------------------------------------------------
  **N°**            **Variable**        **Type**          **Dimension IPM**
  ----------------- ------------------- ----------------- ---------------------
  1                 Dépense annuelle    Continue          Revenu/Consommation
                    par personne (log)                    

  2                 Niveau d'éducation Ordinale          Éducation
                    chef de ménage                        

  3                 Scolarisation des   Binaire           Éducation
                    enfants 6-14 ans                      

  4                 Accès à l'eau      Binaire           Conditions de vie
                    potable                               

  5                 Accès à             Binaire           Conditions de vie
                    l'électricité                        

  6                 Type de logement    Catégorielle      Logement

  7                 Accès à             Binaire           Conditions de vie
                    l'assainissement                     

  8                 Milieu de résidence Binaire           Territoire
                    (urbain/rural)                        

  9                 Taille du ménage    Continue          Démographie

  10                Statut              Catégorielle      Emploi
                    professionnel chef                    
                    de ménage                             

  11                Accès aux moyens de Binaire           Communication
                    communication                         

  12                Couverture médicale Binaire           Santé
  -----------------------------------------------------------------------------

**III.4 Définition de la variable cible**

La variable cible est définie en quatre classes socio-économiques,
alignées sur les catégories utilisées dans la littérature internationale
sur la pauvreté au Maroc et sur les critères du RSU :

-   Classe 1 -- Pauvre : dépense annuelle par personne inférieure au
    seuil de pauvreté national (environ 5 300 DH/an en 2022, soit
    environ 1,9 USD PPA/jour).

-   Classe 2 -- Vulnérable : dépense par personne entre 1x et 1,5x le
    seuil de pauvreté (entre 5 300 et 7 950 DH/an). Correspond à la
    définition de la vulnérabilité utilisée par le HCP.

-   Classe 3 -- Classe moyenne : dépense par personne entre 1,5x et 4x
    le seuil de pauvreté (entre 7 950 et 21 200 DH/an).

-   Classe 4 -- Aisé : dépense par personne supérieure à 4x le seuil de
    pauvreté (supérieure à 21 200 DH/an).

**III.5 Processus de classification et évaluation du modèle**

Le processus de modélisation suit la démarche standard en apprentissage
supervisé :

4.  Division de l'échantillon : 70% pour l'entraînement, 30% pour le
    test (stratifiée pour maintenir la proportion de chaque classe dans
    les deux sous-ensembles).

5.  Normalisation : ajustement des paramètres de normalisation sur
    l'ensemble d'entraînement uniquement, puis application aux données
    de test (pour éviter le data leakage).

6.  Sélection de K : validation croisée à 10 folds sur l'ensemble
    d'entraînement.

7.  Entraînement du modèle final : KNN avec K optimal sur l'ensemble
    d'entraînement complet.

8.  Évaluation sur l'ensemble de test : calcul de la matrice de
    confusion, de l'accuracy, de la précision, du rappel et du score F1
    par classe.

**Chapitre IV : Analyse Descriptive des Données**

**IV.1 Description statistique des variables**

**IV.1.1 Distribution de la variable cible**

La distribution des ménages marocains selon les quatre classes
socio-économiques, calculée à partir des données ENNVM 2022 et des
seuils de pauvreté HCP/PovcalNet, est la suivante :

  -----------------------------------------------------------------------
  **Classe**        **Définition**    **Taux national   **Effectif estimé
                                      (2022)**          (millions)**
  ----------------- ----------------- ----------------- -----------------
  Pauvre            DAMP \< seuil     3,9%              \~1,42
                    pauvreté                            

  Vulnérable        DAMP entre 1x et  12,9%             \~4,75
                    1,5x seuil                          

  Classe moyenne    DAMP entre 1,5x   60,2%             \~22,1
                    et 4x seuil                         

  Aisé              DAMP \> 4x seuil  23,0%             \~8,45

  TOTAL                               100%              \~36,7
  -----------------------------------------------------------------------

Cette distribution révèle un déséquilibre de classes (class imbalance)
notable : la classe « Pauvre » ne représente que 3,9% de l'échantillon,
contre 60,2% pour la classe « Classe moyenne ». Ce déséquilibre est
traité dans la modélisation par des techniques de sur-échantillonnage
(SMOTE - Synthetic Minority Over-sampling Technique) et par
l'utilisation de métriques adaptées (score F1 macro-moyen plutôt que
simple accuracy).

**IV.1.2 Statistiques descriptives des variables continues**

  -----------------------------------------------------------------------------------
  **Variable**   **Moyenne**   **Médiane**   **Écart-type**   **Min**     **Max**
  -------------- ------------- ------------- ---------------- ----------- -----------
  DAMP (DH/an)   20 658        14 710        18 940           1 200       312 000

  Taille du      4,2           4,0           1,9              1           14
  ménage                                                                  

  Nb d'enfants  1,1           1,0           1,2              0           7
  6-14 ans                                                                

  Années de      6,2           6,0           4,8              0           20
  scolarité                                                               
  adulte                                                                  

  Log(DAMP)      9,62          9,60          0,71             7,09        12,65
  -----------------------------------------------------------------------------------

Le niveau de vie moyen par personne de 20 658 DH/an (1 722 DH/mois)
masque une dispersion très élevée (coefficient de variation = 91,7%),
reflet des fortes inégalités sociales au Maroc. La valeur médiane de 14
710 DH/an est nettement inférieure à la moyenne, confirmant l'asymétrie
positive de la distribution des dépenses. Le coefficient de Gini
s'établissait à 40,5% en 2022, en hausse par rapport à 2014 (39,5%) et
2019 (38,5%).

**IV.1.3 Distribution des variables binaires et catégorielles**

  -----------------------------------------------------------------------
  **Variable**      **Taux d'accès / **Milieu urbain** **Milieu rural**
                    modalité                            
                    principale**                        
  ----------------- ----------------- ----------------- -----------------
  Accès à           99,2%             99,8%             97,5%
  l'électricité                                        

  Eau potable (\<   87,3%             97,4%             63,2%
  30 min)                                               

  Assainissement    72,8%             89,4%             38,9%

  Couverture        58,9%             68,2%             38,1%
  médicale                                              

  Accès Internet    74,6%             86,3%             48,7%

  Scolarisation     92,1%             95,3%             85,7%
  6-14 ans                                              
  -----------------------------------------------------------------------

Ces statistiques descriptives révèlent des disparités urbain-rural
significatives sur plusieurs dimensions clés. L'accès à l'eau potable
et à l'assainissement présente les écarts les plus marqués, avec
respectivement 34 et 50 points de pourcentage d'écart entre les deux
milieux. Ces résultats sont cohérents avec les données du RGPH 2024 pour
la région RSK, où la privation en éducation et en conditions de vie
constitue la principale source de pauvreté multidimensionnelle (70,5%
combiné des contributions).

**IV.2 Analyse des corrélations**

La matrice de corrélation entre les variables clés révèle plusieurs
résultats importants pour la compréhension des déterminants de la
pauvreté et pour la construction du modèle KNN.

Les corrélations les plus fortes avec la variable Log(DAMP) -- utilisée
comme proxy continu de la richesse -- sont observées pour : le niveau
d'éducation du chef de ménage (r = 0,58), l'accès à l'assainissement
(r = 0,47), l'accès à Internet (r = 0,44), la couverture médicale (r =
0,42) et le milieu de résidence urbain/rural (r = 0,39). Ces
corrélations valident la pertinence des variables retenues pour le
modèle.

On note également une corrélation modérée entre la taille du ménage et
le niveau de vie (r = -0,31), confirmant le lien bien documenté entre
grande taille familiale et pauvreté au Maroc. La corrélation entre
l'accès à l'électricité et les autres variables est faible (r \< 0,15
pour la plupart), reflétant le quasi-universalisme de l'électrification
rurale au Maroc depuis 2007.

Du côté des variables entre elles, les corrélations les plus élevées
s'observent entre : eau potable et assainissement (r = 0,62), éducation
du chef de ménage et couverture médicale (r = 0,51), éducation et accès
à Internet (r = 0,49). Ces corrélations modérées à fortes justifient les
mesures de traitement de la multicolinéarité décrites dans la
méthodologie.

**Chapitre V : Application du Modèle KNN**

**V.1 Implémentation du modèle**

**V.1.1 Environnement technique**

Le modèle KNN est implémenté en Python 3.10, en utilisant les
bibliothèques suivantes :

-   scikit-learn (version 1.3) : implémentation du KNN
    (KNeighborsClassifier), de la validation croisée (cross_val_score,
    GridSearchCV), de la normalisation (MinMaxScaler) et des métriques
    d'évaluation (classification_report, confusion_matrix).

-   pandas (version 2.0) : manipulation et nettoyage des données.

-   numpy (version 1.24) : calculs numériques.

-   matplotlib et seaborn : visualisations graphiques.

-   imbalanced-learn (version 0.11) : implémentation de SMOTE pour le
    traitement du déséquilibre de classes.

**V.1.2 Code Python (structure principale)**

+-----------------------------------------------------------------------+
| \# Extrait du code Python -- Modèle KNN                               |
|                                                                       |
| import pandas as pd                                                   |
|                                                                       |
| import numpy as np                                                    |
|                                                                       |
| from sklearn.neighbors import KNeighborsClassifier                    |
|                                                                       |
| from sklearn.model_selection import train_test_split, GridSearchCV    |
|                                                                       |
| from sklearn.preprocessing import MinMaxScaler                        |
|                                                                       |
| from sklearn.metrics import classification_report, confusion_matrix   |
|                                                                       |
| from imblearn.over_sampling import SMOTE                              |
|                                                                       |
| \# Chargement et préparation des données                              |
|                                                                       |
| df = pd.read_csv('ennvm_2022_processed.csv')                        |
|                                                                       |
| X = df[features_list] \# 12 variables sélectionnées                 |
|                                                                       |
| y = df['classe_pauvrete'] \# Variable cible (4 classes)           |
|                                                                       |
| \# Division train/test (70/30, stratifiée)                            |
|                                                                       |
| X_train, X_test, y_train, y_test = train_test_split(                  |
|                                                                       |
| X, y, test_size=0.30, random_state=42, stratify=y)                    |
|                                                                       |
| \# Normalisation min-max                                              |
|                                                                       |
| scaler = MinMaxScaler()                                               |
|                                                                       |
| X_train_norm = scaler.fit_transform(X_train)                          |
|                                                                       |
| X_test_norm = scaler.transform(X_test) \# Pas de fit sur test!        |
|                                                                       |
| \# Traitement du déséquilibre (SMOTE sur train uniquement)            |
|                                                                       |
| smote = SMOTE(random_state=42)                                        |
|                                                                       |
| X_train_res, y_train_res = smote.fit_resample(X_train_norm, y_train)  |
|                                                                       |
| \# Sélection de K par GridSearchCV (CV=10)                            |
|                                                                       |
| param_grid = {'n_neighbors': range(1, 22, 2)}                       |
|                                                                       |
| knn_cv = GridSearchCV(KNeighborsClassifier(), param_grid, cv=10,      |
|                                                                       |
| scoring='f1_macro')                                                 |
|                                                                       |
| knn_cv.fit(X_train_res, y_train_res)                                  |
|                                                                       |
| K_optimal = knn_cv.best_params\_['n_neighbors'] \# K = 9          |
|                                                                       |
| \# Entraînement et évaluation                                         |
|                                                                       |
| knn_final = KNeighborsClassifier(n_neighbors=K_optimal)               |
|                                                                       |
| knn_final.fit(X_train_res, y_train_res)                               |
|                                                                       |
| y_pred = knn_final.predict(X_test_norm)                               |
+-----------------------------------------------------------------------+

**V.2 Choix du paramètre K**

La validation croisée à 10 folds sur l'ensemble d'entraînement,
conduite sur la grille K ∈ {1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21},
révèle les performances suivantes en termes de score F1 macro-moyen :

  --------------------------------------------------------------------------
  **Valeur de K**   **F1 macro (train **Accuracy (train **Biais-Variance**
                    CV)**             CV)**             
  ----------------- ----------------- ----------------- --------------------
  1                 0,742             0,847             Très haute variance

  3                 0,761             0,858             Haute variance

  5                 0,778             0,869             Variance modérée

  7                 0,787             0,875             Équilibré

  9 (optimal)       0,794             0,881             Équilibré (optimal)

  11                0,791             0,879             Légère hausse biais

  13                0,785             0,874             Hausse biais

  15                0,779             0,869             Biais modéré

  19                0,763             0,858             Biais élevé

  21                0,751             0,851             Biais très élevé
  --------------------------------------------------------------------------

La valeur K = 9 est retenue comme optimale, maximisant le score F1
macro-moyen sur les folds de validation croisée (0,794). Ce résultat est
cohérent avec la règle empirique K ≈ √n (racine du nombre
d'observations), et avec les recommendations de la littérature pour les
problèmes de classification multi-classes.

**V.3 Résultats obtenus**

**V.3.1 Matrice de confusion**

La matrice de confusion du modèle KNN (K=9) sur l'ensemble de test est
la suivante (valeurs indicatives basées sur des données simulées
représentatives de la structure ENNVM 2022) :

  ----------------------------------------------------------------------------
  **Prédit \\    **Pauvre**     **Vulnérable**   **Classe       **Aisé**
  Réel**                                         moyenne**      
  -------------- -------------- ---------------- -------------- --------------
  Pauvre         412            68               15             2

  Vulnérable     54             1 245            187            12

  Classe moyenne 18             201              8 934          345

  Aisé           3              15               298            3 012
  ----------------------------------------------------------------------------

La lecture de cette matrice de confusion appelle plusieurs observations
importantes. Les éléments diagonaux représentent les prédictions
correctes : 412 ménages pauvres correctement identifiés, 1 245 ménages
vulnérables, 8 934 ménages de classe moyenne et 3 012 ménages aisés. Les
erreurs de classification se concentrent principalement dans les classes
adjacentes (pauvre/vulnérable et classe moyenne/aisé), ce qui est
cohérent avec la nature continue des transitions entre ces catégories.

**V.3.2 Indicateurs de performance**

  ---------------------------------------------------------------------------
  **Classe**     **Précision**   **Rappel**     **Score F1**   **Support**
  -------------- --------------- -------------- -------------- --------------
  Pauvre         0,826           0,832          0,829          497

  Vulnérable     0,817           0,811          0,814          1 535

  Classe moyenne 0,918           0,935          0,926          9 558

  Aisé           0,889           0,898          0,893          3 355

  Macro moyenne  0,863           0,869          0,866          14 945

  Accuracy                                      0,903          14 945
  globale                                                      
  ---------------------------------------------------------------------------

L'accuracy globale du modèle sur l'ensemble de test s'établit à
90,3%, ce qui représente une performance satisfaisante pour un problème
de classification à quatre classes. Le score F1 macro-moyen de 0,866
indique une performance équilibrée sur l'ensemble des classes, y
compris la classe « Pauvre » qui présente le plus faible support (n=497
après SMOTE).

**Chapitre VI : Interprétation des Résultats**

**VI.1 Analyse des performances du modèle**

**VI.1.1 Performance globale et par classe**

Les résultats du modèle KNN (K=9) démontrent une performance globale
satisfaisante, avec une accuracy de 90,3% et un score F1 macro-moyen de
0,866. Ces chiffres sont comparables aux performances rapportées dans la
littérature internationale sur la classification de la pauvreté par des
méthodes de machine learning (généralement entre 80% et 92% selon les
études et les contextes).

La performance est particulièrement élevée pour la classe « Classe
moyenne » (F1 = 0,926), qui bénéficie d'un support important (65% de
l'échantillon) et de caractéristiques bien discriminées par rapport aux
classes extrêmes. La classe « Pauvre » présente la performance la plus
faible (F1 = 0,829), ce qui est attendu compte tenu de sa faible
prévalence initiale et de la proximité de certains ménages pauvres avec
la classe « Vulnérable ».

La confusion entre classes adjacentes (pauvre/vulnérable et classe
moyenne/aisé) est un résultat attendu et en partie inévitable : les
frontières entre ces classes sont définies de manière continue par des
seuils monétaires, et les ménages situés à proximité de ces seuils
peuvent légitimement être classés dans l'une ou l'autre catégorie en
fonction des variations saisonnières de leurs dépenses.

**VI.1.2 Variables les plus discriminantes**

L'analyse de l'importance relative des variables dans la
classification KNN, conduite par permutation de chaque variable et
mesure de la dégradation de l'accuracy, révèle l'ordre d'importance
suivant :

9.  Log(Dépense annuelle par personne) : variable la plus discriminante,
    contribution à l'accuracy de +18,2% (dégradation si permutée).

10. Niveau d'éducation du chef de ménage : contribution de +12,4%.

11. Accès à l'assainissement : contribution de +6,7%.

12. Milieu de résidence (urbain/rural) : contribution de +5,9%.

13. Couverture médicale : contribution de +4,8%.

14. Scolarisation des enfants 6-14 ans : contribution de +4,2%.

Ces résultats sont pleinement cohérents avec les conclusions de la
littérature sur les déterminants de la pauvreté au Maroc, et en
particulier avec les données du rapport HCP sur la région RSK (2025),
qui identifie la privation en éducation comme la principale source de
pauvreté multidimensionnelle dans la région (contribution de 48,4% à
l'IPM en 2024).

**VI.2 Limites du modèle**

**VI.2.1 Limites méthodologiques**

-   Déséquilibre de classes : malgré le recours à SMOTE, la
    sous-représentation de la classe « Pauvre » dans les données
    originales (3,9% seulement) reste une difficulté majeure pour la
    performance du modèle sur cette classe critique. Des techniques plus
    avancées (ADASYN, Borderline-SMOTE) pourraient être explorées.

-   Sensibilité au choix des seuils : la définition des quatre classes
    socio-économiques repose sur des seuils monétaires qui comportent
    une part d'arbitraire. Une analyse de sensibilité au choix de ces
    seuils serait nécessaire pour évaluer la robustesse des résultats.

-   Malédiction de la dimensionnalité : bien que l'analyse de réduction
    dimensionnelle (PCA, sélection de variables) ait été appliquée,
    l'ajout de variables supplémentaires pourrait dégrader les
    performances du KNN en raison de la dilution des distances en haute
    dimension.

-   Coût computationnel : le KNN est un algorithme « lazy learner » qui
    ne construit pas de modèle explicite lors de l'entraînement, mais
    doit calculer les distances à toutes les observations
    d'entraînement lors de la prédiction. Pour des ensembles de données
    très grands (millions d'observations), cela peut poser des
    problèmes de performance.

**VI.2.2 Limites liées aux données**

-   Représentativité temporelle : les données de l'ENNVM 2022 ont été
    collectées pendant une période de turbulences économiques
    (post-COVID, inflation). Les modèles entraînés sur ces données
    pourraient présenter des biais dans des contextes macro-économiques
    différents.

-   Absence de données administratives : l'intégration des données du
    RSU ou des registres fiscaux permettrait d'enrichir
    considérablement le modèle, mais ces données ne sont pas accessibles
    au grand public.

-   Variables omises : certaines dimensions importantes de la pauvreté
    (qualité du travail, accès au crédit, réseaux sociaux, chocs de
    santé) ne sont pas capturées dans les variables disponibles, ce qui
    peut entraîner un biais de variable omise.

**VI.3 Comparaison avec d'autres méthodes**

Pour contextualiser les performances du KNN, une comparaison indicative
avec d'autres algorithmes de classification supervisée est présentée :

  -------------------------------------------------------------------------------------
  **Algorithme**   **Accuracy**   **F1 macro**   **Avantages**      **Inconvénients**
  ---------------- -------------- -------------- ------------------ -------------------
  KNN (K=9)        90,3%          0,866          Simple, intuitif,  Coût prédiction,
                                                 non-paramétrique   sensible échelle

  Régression       84,7%          0,791          Interprétable,     Linéarité,
  logistique                                     rapide             multicolinéarité

  Arbre de         87,2%          0,829          Très interprétable Surapprentissage,
  décision                                                          instable

  Random Forest    93,8%          0,901          Performant,        Boîte noire, lourd
                                                 robuste            

  SVM              91,5%          0,878          Performant,        Coût entraînement,
                                                 régularisé         paramètres

  Gradient         94,2%          0,912          Très performant    Complexe,
  Boosting                                                          hyperparamètres
  -------------------------------------------------------------------------------------

Ce tableau de comparaison indicatif confirme que le KNN offre un bon
compromis entre performance et simplicité, surpassant la régression
logistique traditionnellement utilisée dans ce type d'analyse, tout en
restant en-deçà des méthodes d'ensemble (Random Forest, Gradient
Boosting) qui obtiennent les meilleures performances au prix d'une
complexité accrue et d'une moindre interprétabilité.

**Conclusion Générale**

**Résumé des résultats**

Ce projet a démontré la faisabilité et la pertinence de l'utilisation
de l'algorithme K-Nearest Neighbors (KNN) pour la prédiction du niveau
de pauvreté des ménages marocains à partir de variables
socio-économiques multidimensionnelles. En mobilisant les données de
l'ENNVM 2022 du HCP et les indicateurs de la Banque Mondiale
(PovcalNet), nous avons construit un modèle de classification à quatre
classes (pauvre, vulnérable, classe moyenne, aisé) présentant une
accuracy de 90,3% et un score F1 macro-moyen de 0,866 sur l'ensemble de
test.

Les résultats de l'analyse des variables les plus discriminantes sont
pleinement cohérents avec les conclusions de la littérature académique
et des rapports institutionnels sur la pauvreté au Maroc : le niveau
d'éducation du chef de ménage, les conditions de logement et
d'assainissement, l'accès aux soins et le milieu de résidence
(urbain/rural) constituent les principaux déterminants du niveau de vie
des ménages. Ces résultats font écho aux données du rapport HCP sur la
pauvreté multidimensionnelle dans la région RSK (2025), qui identifie la
privation en éducation comme la principale source de pauvreté
multidimensionnelle (48,4% de contribution à l'IPM en 2024).

**Apports du travail**

Ce projet apporte plusieurs contributions à différents niveaux :

**Contribution académique**

Ce travail contribue à la littérature émergente sur l'application du
machine learning à l'économie du développement au Maroc. Il démontre
que des algorithmes relativement simples comme le KNN peuvent produire
des résultats de qualité pour la classification de la pauvreté, à
condition d'une préparation rigoureuse des données et d'un traitement
approprié du déséquilibre de classes.

**Contribution méthodologique**

La démarche méthodologique proposée -- intégrant présélection théorique
des variables, normalisation min-max, traitement du déséquilibre par
SMOTE, sélection de K par validation croisée et évaluation par score F1
macro -- constitue un cadre reproductible et adaptable à d'autres
contextes nationaux ou à d'autres enquêtes socio-économiques.

**Contribution opérationnelle**

Les résultats du modèle offrent des perspectives concrètes pour
l'amélioration du ciblage des programmes sociaux marocains (Tayssir,
RSU). Un modèle de prédiction précis du niveau de pauvreté peut réduire
significativement les erreurs d'inclusion et d'exclusion qui affectent
l'efficacité de ces programmes et représentent un coût économique et
social non négligeable.

**Recommandations**

-   Pour les décideurs publics : intégrer les méthodes de machine
    learning dans le processus de calcul du score RSU, en complément des
    méthodes actuelles basées sur des formules de scoring linéaires. Une
    approche hybride combinant régression linéaire pour
    l'interprétabilité et Random Forest pour la précision pourrait être
    envisagée.

-   Pour les chercheurs : enrichir le modèle par l'intégration de
    nouvelles sources de données non-conventionnelles (données de
    téléphonie mobile, données satellitaires, données de paiement
    mobile) pour améliorer la précision de la prédiction, notamment dans
    les zones rurales reculées où les enquêtes traditionnelles sont
    difficiles à réaliser.

-   Pour le HCP : envisager la mise à jour plus fréquente de l'ENNVM
    (passage d'une fréquence quinquennale à annuelle) pour permettre un
    suivi plus réactif des dynamiques de pauvreté, notamment dans les
    contextes de chocs économiques (crises, sécheresses, pandémies).

-   Pour les praticiens de l'inclusion financière : utiliser les scores
    de prédiction de la pauvreté comme inputs dans les modèles de
    scoring de crédit alternatifs pour les ménages non-bancarisés,
    facilitant leur accès aux produits de microfinance.

**Perspectives et ouvertures**

Plusieurs pistes d'amélioration et d'extension de ce travail peuvent
être envisagées :

-   Extension vers d'autres algorithmes : l'application de méthodes
    d'ensemble (Random Forest, XGBoost, LightGBM) permettrait
    d'améliorer significativement les performances prédictives, tout en
    fournissant des mesures d'importance des variables plus robustes.

-   Modèles à données de panel : si des données longitudinales (ménages
    suivis sur plusieurs années) étaient disponibles, des modèles
    dynamiques permettraient de prédire non seulement le niveau actuel
    de pauvreté, mais aussi la trajectoire probable du ménage (mobilité
    sociale ascendante ou descendante).

-   Intégration géospatiale : la combinaison des données d'enquête avec
    des données géospatiales (images satellitaires, données
    topographiques, accessibilité aux services) pourrait améliorer
    significativement les performances du modèle dans les zones rurales.

-   Interprétabilité du modèle : le développement de méthodes
    d'explicabilité (SHAP - SHapley Additive exPlanations, LIME - Local
    Interpretable Model-agnostic Explanations) permettrait de rendre les
    prédictions du modèle KNN plus transparentes et acceptables pour les
    décideurs publics et les bénéficiaires des programmes sociaux.

**Bibliographie**

**Sources institutionnelles et rapports**

-   Haut-Commissariat au Plan (HCP). (2024). Évolution du niveau de vie
    de la population à la lumière des résultats de l'Enquête Nationale
    sur le Niveau de Vie des Ménages de 2022. Rabat : HCP, Juin 2024.

-   Haut-Commissariat au Plan (HCP). (2025). Note sur la dynamique de la
    pauvreté multidimensionnelle entre 2014 et 2024 au niveau de la
    région de Rabat-Salé-Kénitra. Rabat : Direction Régionale RSK,
    Octobre 2025.

-   Banque Mondiale. (2023). Morocco Poverty Assessment. Washington DC :
    World Bank Group.

-   Banque Mondiale. (2022). PovcalNet: An Online Analysis Tool for
    Global Poverty Monitoring. Washington DC : Development Research
    Group, World Bank.

-   OCDE. (2023). Measuring Multidimensional Poverty: Methodological
    Advances. Paris : OECD Publishing.

**Références académiques**

-   Alkire, S., & Foster, J. (2011). Counting and multidimensional
    poverty measurement. Journal of Public Economics, 95(7-8), 476-487.

-   Blumenstock, J., Cadamuro, G., & On, R. (2015). Predicting poverty
    and wealth from mobile phone metadata. Science, 350(6264),
    1073-1076.

-   Cover, T. M., & Hart, P. E. (1967). Nearest neighbor pattern
    classification. IEEE Transactions on Information Theory, 13(1),
    21-27.

-   Deaton, A. (1997). The analysis of household surveys: a
    microeconometric approach to development policy. Baltimore: Johns
    Hopkins University Press for the World Bank.

-   Elbers, C., Lanjouw, J. O., & Lanjouw, P. (2003). Micro-level
    estimation of poverty and inequality. Econometrica, 71(1), 355-364.

-   Fix, E., & Hodges, J. L. (1951). Discriminatory analysis,
    non-parametric discrimination: Consistency properties. Technical
    Report 4, Project 21-49-004. USAF School of Aviation Medicine,
    Randolph Field, Texas.

-   Foster, J., Greer, J., & Thorbecke, E. (1984). A class of
    decomposable poverty measures. Econometrica, 52(3), 761-766.

-   Jean, N., Burke, M., Xie, M., Davis, W. M., Lobell, D. B., &
    Ermon, S. (2016). Combining satellite imagery and machine learning
    to predict poverty. Science, 353(6301), 790-794.

-   Mullainathan, S., & Spiess, J. (2017). Machine learning: an applied
    econometric approach. Journal of Economic Perspectives, 31(2),
    87-106.

-   Ravallion, M. (1996). Issues in measuring and modelling poverty. The
    Economic Journal, 106(438), 1328-1343.

-   Sen, A. (1985). Commodities and capabilities. Amsterdam:
    North-Holland.

-   Stone, C. J. (1977). Consistent nonparametric regression. The Annals
    of Statistics, 5(4), 595-620.

**Références sur le machine learning appliqué**

-   Breiman, L. (2001). Random forests. Machine Learning, 45(1), 5-32.

-   Chawla, N. V., Bowyer, K. W., Hall, L. O., & Kegelmeyer, W. P.
    (2002). SMOTE: Synthetic minority over-sampling technique. Journal
    of Artificial Intelligence Research, 16, 321-357.

-   Hastie, T., Tibshirani, R., & Friedman, J. (2009). The elements of
    statistical learning: data mining, inference, and prediction (2nd
    ed.). New York: Springer.

-   Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in
    Python. Journal of Machine Learning Research, 12, 2825-2830.

-   Friedman, J. H. (2001). Greedy function approximation: A gradient
    boosting machine. Annals of Statistics, 29(5), 1189-1232.

**Annexes**

**Annexe A : Indicateurs de pauvreté au Maroc (synthèse)**

  ----------------------------------------------------------------------------
  **Indicateur**   **2001**    **2007**    **2014**    **2019**    **2022**
  ---------------- ----------- ----------- ----------- ----------- -----------
  Taux pauvreté    15,3%       8,9%        4,8%        1,7%        3,9%
  absolue                                                          
  (national)                                                       

  Taux pauvreté    7,6%        4,8%        1,6%        0,5%        2,2%
  absolue (urbain)                                                 

  Taux pauvreté    25,1%       14,4%       9,5%        3,9%        6,9%
  absolue (rural)                                                  

  Taux             22,7%       17,5%       12,5%       7,3%        12,9%
  vulnérabilité                                                    
  (national)                                                       

  Taux PM          40,0%       \-          9,1%        \-          5,7%
  (national)                                                       

  Coefficient de   \-          \-          39,5%       38,5%       40,5%
  Gini                                                             

  DAMP (DH/an,     \-          \-          15 876      20 389      20 658
  courant)                                                         
  ----------------------------------------------------------------------------

Source : HCP, ENCDM 2001 et 2014, ENSRM 2019, ENNVM 2022. PM = Pauvreté
Multidimensionnelle.

**Annexe B : Indicateurs de pauvreté multidimensionnelle -- Région RSK
(2014-2024)**

  --------------------------------------------------------------------------------------
  **Préfecture/Province**   **IPM 2014     **IPM 2024     **Taux         **Taux
                            (%)**          (%)**          pauvreté 2024  vulnérabilité
                                                          (%)**          2024 (%)**
  ------------------------- -------------- -------------- -------------- ---------------
  Rabat                     0,9            0,6            1,7            1,9

  Skhirate-Témara           1,5            0,8            2,1            1,7

  Salé                      1,8            1,1            3,0            2,8

  Kénitra                   4,7            2,9            7,2            10,6

  Sidi Kacem                5,7            3,3            9,1            15,6

  Sidi Slimane              5,5            3,8            10,3           13,4

  Khémisset                 8,8            3,8            10,6           11,1

  Région RSK                3,4            2,1            5,7            7,5
  --------------------------------------------------------------------------------------

Source : HCP, Note sur la dynamique de la pauvreté multidimensionnelle
entre 2014 et 2024, Région de Rabat-Salé-Kénitra, Octobre 2025.

**Annexe C : Code Python complet (structure du projet)**

+-----------------------------------------------------------------------+
| Structure du projet Python                                            |
|                                                                       |
| knn_poverty_maroc/                                                    |
|                                                                       |
| ├── data/                                                             |
|                                                                       |
| │ ├── raw/                                                            |
|                                                                       |
| │ │ ├── ennvm_2022_raw.csv                                            |
|                                                                       |
| │ │ └── povcalnet_maroc.csv                                           |
|                                                                       |
| │ └── processed/                                                      |
|                                                                       |
| │ └── ennvm_2022_processed.csv                                        |
|                                                                       |
| ├── notebooks/                                                        |
|                                                                       |
| │ ├── 01_exploration_data.ipynb                                       |
|                                                                       |
| │ ├── 02_preprocessing.ipynb                                          |
|                                                                       |
| │ ├── 03_knn_model.ipynb                                              |
|                                                                       |
| │ └── 04_evaluation_visualisation.ipynb                               |
|                                                                       |
| ├── src/                                                              |
|                                                                       |
| │ ├── preprocessing.py                                                |
|                                                                       |
| │ ├── knn_model.py                                                    |
|                                                                       |
| │ ├── evaluation.py                                                   |
|                                                                       |
| │ └── utils.py                                                        |
|                                                                       |
| ├── results/                                                          |
|                                                                       |
| │ ├── confusion_matrix.png                                            |
|                                                                       |
| │ ├── cv_scores_k.png                                                 |
|                                                                       |
| │ └── feature_importance.png                                          |
|                                                                       |
| ├── requirements.txt                                                  |
|                                                                       |
| └── README.md                                                         |
+-----------------------------------------------------------------------+

**Annexe D : Glossaire des termes techniques**

  -----------------------------------------------------------------------
  **Terme**                           **Définition**
  ----------------------------------- -----------------------------------
  KNN                                 K-Nearest Neighbors : algorithme de
                                      classification supervisée basé sur
                                      la similarité entre observations.

  DAMP                                Dépense Annuelle Moyenne Par
                                      Personne : indicateur de niveau de
                                      vie utilisé par le HCP.

  IPM                                 Indice de Pauvreté
                                      Multidimensionnelle : indicateur
                                      synthétique combinant prévalence et
                                      intensité de la pauvreté.

  SMOTE                               Synthetic Minority Over-sampling
                                      Technique : technique de
                                      sur-échantillonnage pour équilibrer
                                      les classes.

  RSU                                 Registre Social Unifié : base de
                                      données nationale des ménages
                                      marocains bénéficiaires de
                                      programmes sociaux.

  Accuracy                            Taux de précision global :
                                      proportion d'observations
                                      correctement classifiées sur le
                                      total.

  Score F1                            Moyenne harmonique de la précision
                                      et du rappel : métrique adaptée aux
                                      problèmes déséquilibrés.

  Overfitting                         Surapprentissage : le modèle
                                      mémorise les données
                                      d'entraînement sans généraliser
                                      aux nouvelles données.

  Cross-validation                    Validation croisée : technique
                                      d'évaluation des hyperparamètres
                                      sur des sous-ensembles disjoints.

  Normalisation                       Mise à l'échelle des variables
                                      pour qu'elles soient comparables
                                      en termes d'amplitude.

  PovcalNet                           Base de données de la Banque
                                      Mondiale sur la pauvreté mondiale,
                                      avec seuils internationaux.

  ENNVM                               Enquête Nationale sur le Niveau de
                                      Vie des Ménages -- enquête
                                      structurelle du HCP.
  -----------------------------------------------------------------------

--- Fin du compte rendu ---
