---
layout: post
title: "L'absence, les surveillances électroniques, l'interruption de peine et le Virus : "
categories: stat
author: "John Nève"
meta: "marx"
---

Une email et quelques pièces jointes. Le problème de la définition des variables. 

## Notations pour les Prisons

Supposons qu'il existe un nombre déterminé de prisons (e.g $$ I \in \mathbf{R} $$) sur un terrtoire. Désignons par $i$ l'une des $I$ prisons de ce territoire et par $$ n_i $$, le nombre de détenus au sein de la prison $$i$$.

Supposons que chaque prison $$i$$ a une "capacité théorique", ci-après dénotée $$ \xi_i $$. Nommons le nombre total de détenus au sein du système carcéral belge par $$ N $$ et la capacité totale de détention du système carcérale par $$ \Xi $$. 

Enfin, désignons par $$g_i$$ le nombre de salariés travaillant au sein de la prison $$i$$ et par $$G$$ le nombre total de salariés oeuvrant à la reproduction des tâches journalières auquelles sont confronté les membres du système carcérale fédéral.

En l'espèce, nous dirons donc qu'au sein des $$I$$ prisons fédérales du pays, il y a

- $$ N = \sum_{I} n_{i} $$ détenus pour

- $$ \Xi = \sum_{I} \xi_{i} $$ lits et 

- $$ G = \sum_{I} g_{i} $$ intervenants salariés.


## Construire les données 



## La question de l'absence.

```{r}

prison <- read.csv("prison.csv", header = TRUE, sep = ";", dec =",")
rownames(prison)=prison[,1]
rownames(prison)

[1] "Antwerpen"                    "Beveren"                      "Brugge"                       "Dendermonde"                  "Gent"                         "Hasselt_Nieuw"               
 [7] "Hoogstraten"                  "Ieper"                        "Leuven_Centraal"              "Leuven_Hulp"                  "Malines_Maison_de_transition" "Mechelen"                    
[13] "Merksplas"                    "Oudenaarde"                   "Ruiselede"                    "Tongeren_Nieuw"               "Turnhout"                     "Wortel"                      
[19] "Andenne"                      "Arlon"                        "Dinant"                       "Enghien_Maison_de_transition" "Huy"                          "Ittre"                       
[25] "Jamioulx"                     "Lantin"                       "Leuze-en-Hainaut"             "Marche-En-Famenne"            "Marneffe"                     "Mons"                        
[31] "Namur"                        "Nivelles"                     "Paifve"                       "St._Hubert"                   "Tournai"                      "Berkendael"                  
[37] "Forest"                       "St-Gilles"                   
```

Au sein des 38 espaces fédéraux réservés à la détention des personnes physiques, le ministère public classe les détenus, notamment, via "leurs statuts légaux".


## La question de la présence

Le $$n_i$$ varie énorménent de prison en prison. La prison qui comptabilise le moins de détenus est la maison de transition d'Enghien. Celle qui dénombre le plus grand nombre de détenus est la prison de Lantin. En moyenne, il y a 166 détenus par prison alors que la moitié des détenus sont regroupés dans des prisons avec plus de 147 détenus. 

```{r} 
tot=as.data.frame(prison[,2]+prison[,3]+prison[,4])
data=cbind(prison[,1],tot)
data=data[order(data[,2],decreasing=T), ]
p<-ggplot(data=data, aes(x=tot, y=name)) +  geom_bar(stat="identity")
p
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/histo_prison.jpg" alt="systeme"></div>

Le graphique suivant nous permet d'observer la distibution des effectifs de détenus au sein des prisons. Une grande hétérogénité s'y fait voir. On constate notamment que plus de la moitié des détenus sont regroupés dans des prisons détenant un nombre de détenus inférieur au nombre moyen de détenus par prison.


```{r}

dev.new(width=6.5,height=4.5)
par(cex.lab=1.5,cex.axis=1.3,mar=c(5,5,2,4))
m <- matrix(c(1,1,2,1,1,2),nrow=3)
layout(m)
hist(data[,2],freq=FALSE,xlim=1.5*range(data[,2]),xlab="",ylab="fréquence",
  axes=FALSE,main="",col="grey95")
abline(h=0)
rug(data[,2])
axis(2)
axis(4)
lines(density(data[,2]),col="red")
boxplot(data[,2],horizontal=TRUE,ylim=1.5*range(data[,2]),
  axes=FALSE,xlab="Nombre de détenus")
axis(1)
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/boxplot.jpeg" alt="densité"></div>

### les statuts 


Au courant de l'existence de valeurs possiblement "exhubérantes", il est intéressant d'observer de plus près la distribution des effectifs d'un certain type de détenus. 

Les tableaux statistiques distribués par le ministère public témoignent de son attachement aux différences et nous permettent d'appréhender huit types de détenus. En effet, via ces documents on comprend que 

1. Le détenu est soit de genre Masculin, soit de genre Féminin. 
2. Le détenu est ou prévenu ou condamné. 
3. et enfin, le détenu est interné ou non. `

Ainsi, selon la typologie du ministère public il existe au moins huit manières différentes d'appréhender les détenus.

Sans égard pour la question du genre, on remarque qu'il existe deux grosses catégories de déténus : les prévénus et les codamnés.

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/repart.jpg" alt="statuts"></div>

#### les internés

- Si on s'attelle uniquement à l'étude des déténus dit "internés", on remarque qu'il sont placés dans dix établissements   différents et selon une distibution beaucoup moins uniforme que ce que nous avons pu observer pour les détenus en général. Paifve semble détenir uniquement des détenus de ce type alors que les internés représentent 25 % des effectfis totaux de detenus au sein de la prison historique de Merklpass


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/Intbarplot.jpeg" alt="barplot"></div>

- Notons aussi qu'un *test de student* sur les moyennes des pénitenciers au Nord et au sud de Bruxelles ne révèle aucune différences significatives. Autrement dit, après une brève analyse statistique, on ne peut pas affirmer, par exemple, que les internés sont, en moyenne, dans le sud du Royaume, plus regroupés ensemble que dans le reste du royaume de Belgique.

#### les prévenus 

- Si on s'attelle uniquement à l'étude des déténus dit "Prévenus", on remarque qu'il sont présents dans la quasi totalités des pénitenciers. Cependant, la distribution des prévenus au sein des prisons n'en est pas pour autant plus uniforme au sein du système carcéral. On remarque en particulier que la majorité des des prévenus sont détenus à Lantin, Saint-Gilles ou Merklpass. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus_distribution.jpg" alt="distribution des prevenus"></div>

- Notons en outre que seulement 7 pénitenciers sur les 38  considérés - Hoogstraten, Leuven Centraal, Maison de transition Malines, Ruiselede, Maison de transition d'Enghien, Paifve, et St. Hubert - n détient aucun prévenus.

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus.jpg" alt="prevenu"></div>


#### les comdamnés

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/présence_distribution.jpg" alt="Pourcetage des comdamnés dans chaque prison"></div>

- Remarquons derechef que les détenus dit comdamnés sont présents dans toutes les prisons sauf à Paifve. Ainsi, si on s'attelle uniquement à l'étude de ceux-ci, comparativement aux autres statuts de détenus, la distribution des comdamné au sein des prisons admet une distribution plus uniforme au sein du système carcéral. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/comdamne_distribution.jpg" alt="distribution des comdamnés"></div>

- Notons en outre que si on s'intéresse au nombre de detenus vis à vis des autres par prison, dexu remarques sont à faire dans un premier temps.  Premièrement, il existe deux pénitenciers seulement qui n'acceuillent que des détenus comdamnés : les deux maisons de transition de Maligne et Enghien. Deuxièmement, au premier coup d'oeil, on remarquera trois types de pénitenciers en matière de détentions de comdamnés: 

1. Les pénitenciers s'occupant uniquement des comdamnés.
2. Les pétitenciers avec plus 50 % des détenus comdamnés.
3. Les pénitenciers avec moins de 25 % de détenus comdannés.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distribution_jail.jpg" alt="Pourcentage de Comdamnés par Prison"></div>




