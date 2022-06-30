# Graphiques de consommation de deux individus 

Ce projet est basé sur des données issues d'une récolte de notre consommation de boissons et de nourriture du 27 avril au 9 mai 2022.

Il s'agit essentiellement d'un exercice effectué à la suite du cours [Visualisation de données](https://applicationspub.unil.ch/interpub/noauth/php/Ud/ficheCours.php?v_enstyid=78116&v_ueid=174&v_etapeid1=29023&v_langue=fr&v_isinterne=1) donné par Isaac Pante à l'Université de Lausanne au semestre de Printemps 2022, lors duquel nous avons acquis nos toutes premières notions de programmation.

Nous décrivons ci-dessous les étapes de notre travail: 
1. la récolte de données;
2. l'organisation des données dans un .csv final;
3. les sources utilisés pour la création de la visualisation;
4. la transformation du document .csv en .json;
5. l'adaptation du code.

## Récolte de données
Dans un premier temps, nous avons récolté manuellement les données détaillées de notre consommation de produits alimentaires et de boissons. 

A la fin de cette étape, nous avons obtenu un .csv (le fichier "données_initiales" du dossier) documentant notre consommation selon les 6 variables suivantes (exemples entre parenthèses): 

1. QUI (Sofia Boteva, Clara Chavan) – uniquement deux valeurs 
2. DATE (27/04/2022) 
3. HEURE (10:17:00)
4. NOURRITURE / BOISSON (glace au Tiramisu, Fanta orange)
5. PROVENANCE (restaurant) – nous nous sommes imposées trois valeurs possibles au préalable pour désigner la provenance de la nourriture: restaurant, maison, shop (comprenant les cafétérias). 
6. LIEU (Athènes) – nous avons choisi d'indiquer le lieu car nous savions que nous serions les deux en vacances; respectivement à Milan, et Athènes et Bâle.

##  L'organisation des données dans un .csv final
Nous avons volontairement choisi de documenter d'abord notre consommation selon le nombre maximum des variables pour ensuite avoir plus de liberté à choisir parmi elles les plus adéquates en fonction du type de visualisation que nous allions utiliser, et éliminer le reste.

Nous n'avons finalement pas exploité les dimensions temporelles et spatiales de nos données. Donc nous avons supprimés les valeurs correspondantes pour notre .csv final (fichier "donnees_fin") et nous nous sommes concentrées sur 3 valeurs pour caractériser chaque produit consommé:

1. QUI
2. TYPE (boisson/petit déjeuner/déjeuner/dîner/snack) - 5 valeurs catégorielles. 
3. CATÉGORIE (p.e., pour les boissons: alcoolisé/non alcoolisé, pour le petit déjeuner: œufs/laitier/céréales, etc.)

## Sources de visualisation
Nous nous sommes inspirées du projet [Dear Data](http://www.dear-data.com/theproject) pour imaginer la visualisation.

Pour programmer ce que nous avions imaginé sur papier initialement, nous nous sommes basées sur la visualisation [Zoomable Sunburst](https://observablehq.com/@d3/zoomable-sunburst). 

## Du .csv au .json
Le code sur lequel nous nous sommes basées pour notre visualisation s'est avéré plus ardu à comprendre et à maîtriser que prévu. 

Pour que les données soient intélligibles pour le code, elles devaient être organisés dans un document .json à structure hiérarchique, dans laquelle chaque objet a une valeure numérique et chaque couche est divisée en catégories selon la somme des valeurs des objets que ces catégories et subcatégories contiennent. 

Pour la valeur numérique, nous avons décidé de calculer le nombre des fois que nous avons consommé tel ou tel produit pendant cette période. Ensuite, nous avons passé énormément de temps à effectuer un document .json correct. Nous avons finalement créé un code Python (inclu dans la documentation) qui crée à partir du document .csv un .json hiérarchique de la même structure que dans le dossier initial. 

A la fin de cette étape, nous avons créé deux fichiers .json pour nos données respectives ("Clara_repas_data", "Sofia_repas_data"), dont chacun peut être lu par le code.

## Adaptation finale du code

Après avoir obtenu les bons fichiers .json, nous avons adapté le code pour pouvoir utiliser les deux .json en même temps et avoir deux visualisations respectives affichées correctement. 

Enfin, nous avons travaillé sur le design des graphiques et de la page .html pour que le style visuel soit plus expressif (et plus joli :)) et corresponde mieux à la thématique de nos données, c'est-à-dire la nourriture. Nous avons donc ajouté un arrière-plan dynamique, des curseurs interactifs et une îcone pour la page web.

On a aussi étudié les palettes des couleurs utilisées dans les commerces de nourriture pour choisir une  combinaison des couleurs appropriée pour notre sujet. 

## En guise de conclusion

En ce qui concerne l'analyse des données, cette visualisation nous permet surtout de comparer les habitudes de consommation entre deux individues. 

Mais ce qui était le plus important pour nous dans ce projet – c'est la première expérience de la programmation et de la visualisation de données dans nos vies.  Nous avons vécu le processus complèxe de la récolte des données jusqu'à la visualisation, nous avons eu l'idée
de la structure du code et, surtout, nous avons appris de façon empirique l'un des points les plus importants de ce genre de projets : l'organisation des données.

![Nourriture](burger.jpg)
