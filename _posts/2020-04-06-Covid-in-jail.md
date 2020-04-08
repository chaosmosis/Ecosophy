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

De cette manière on peut défininir une série d'indicateurs qui nous permettront de réaliser une brève analyse statistiques des tableaux de données qui servent à la gestion et au controle des prisons.

Notons notamment que la moyenne de détenu dans une des $$I$$ prisons peut être définie de la manière suivante :
 
 <div style="text-align: center">
 $$ \overline{N} = \frac{ \sum_{I} n_{i} }{ I }$$ 
 </div>
 
Ayant à l'esprit les notation précédentes, au cours de cette analyse nous désignerons par 
 
 - $$d^{h}_{i}$$, le nombre de détenus de type $$ h $$ dépendant de $$ i $$
 - $$\pi_{i} = \frac{\sum_{H}d^{h}_{i}}{N} = \frac{n_i}{N}$$, le pourcentage des détenus détenus au sein de la prison $$i$$ 
 - $$\pi^{h}_{i}= \frac{d^{h}_{i}}{n_i}$$, le pourcentage des détenus de type $$ h $$ au sein des détenus de $$i$$
 - $$\Pi^{h}_{i}= \frac{d^{h}_{i}}{N}$$, la part des détenus de type $$ h $$ dans $$i$$
 - $$\Pi^{h} = \frac{\sum_{I}d^{h}_{i}}{N}$$, le pourcentage de détenus de type $$h$$ dans le système carcéral.
 

## Les données

Les données que nous allons mobilisées ici proviennent du Conseil Centrale de Surveillance des Prisons ci-après CCSP. Cet organe para-parlementaire bénéficie d'une relation directe avec les différentes autorités responsables du sort des détenus. A l'instar d'un organisme para-législatif, le CCSP a une double mission : il est censé contrôler et organiser la surveillance des Prisons au nom du Parlement fédéral de Belgique. 

Vous trouverez les données brutes en cliquant sur le lien suivant.



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



### Analyse descriptive des données relatives aux nombres des détenus en Prison

Au sein des pays membres du conseil de l'Europe, le nombre de personnes détenues au sein d'un système carcérale devraient dépendre directement du travail opéré par le pouvoir judiciaire. N'est pas détenu qui veut.

> "Aucune personne ne peut être administrée ou retenu dans une prison en qualité de détenu sans une ordonnance d'incarcération valable, conformément au droit interne"

Cet extrait de la Recommandation Européenne sur les Règles Pénitentiaires est clair, il faut l'aval d'une autorité publique pour être qualifié de détenu en prison. 

En Belgique, comme le veut l'article  12 de la Constitution, 3ème alinéa :

> "Nul ne peut être arrêté qu'en vertu de l'ordonnance motivée du juge"

Ainsi, comme le souligne les auteurs du Guide du Prisonnier, *"Une décision judiciaire(ordonnance de mise en détention préventive, jugement, etc.) est toujours nécessaire"* pour être considéré comme un détenu en prison.


### Les détenus au sein des prisons

Le nombre de détenu dans une prison, ci-après $$n_i$$, varie énormément d'une prison à une autre. La prison qui comptabilise le moins de détenus est la maison de transition d'Enghien. Celle qui dénombre le plus grand nombre de détenus est la prison de Lantin. En moyenne, il y a 166 détenus par prison alors que la moitié des détenus sont regroupés dans des prisons avec plus de 147 détenus. 

```{r} 
tot=as.data.frame(prison[,2]+prison[,3]+prison[,4])
data=cbind(prison[,1],tot)
data=data[order(data[,2],decreasing=T), ]
p<-ggplot(data=data, aes(x=tot, y=name)) +  geom_bar(stat="identity")
p
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/histo_prison.jpg" alt="systeme"></div>

Le graphique suivant nous permet d'observer la distribution des effectifs de détenus au sein des prisons. Une grande hétérogénité apparait. Celle-ci traduit probablement une réalité immobilière concrète mais nous reviendrons sur ces interprétations plus tard. 

Pour l'instant, contentons-nous de constater que plus de la moitié des détenus sont regroupés dans des prisons détenant un nombre de détenus inférieur au nombre moyen de détenus par prison. Dans pareils cas, on dit que la distibution des effectifs est assymétrique. Dans le cas présent traduit ce phénomène puisque la distribution des détenus au sein du système carcéral est asymétrique au sens où la majorité des détenus sont détenus au sein de prisons ayant des effectifs de détenus inférieurs au nombre moyen de détenus par prison.


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

Au sein des 38 espaces fédéraux réservés à la détention des personnes physiques, le SPF justice comptablise auourd'hui un total de 9881 détenus enmurés.

Nous reviendrons plus loins sur les personnes détenues hors-les-murs des établissemens pénitenciaires mais dépendant de ceux-ci.

### Descrition des types de détenus au sein des pénitenciers

Les tableaux statistiques distribués par le ministère public témoignent des différents statuts attribué à ces détenus. A lire ceux que nous nous sommes procurés ils traduisent un  attachement certains aux différences de statuts. 

Au regard de ces seuls classements, il semble exister dans le chefs des autorités responsables des statsitques relatives aux détenus qu'il existe au moins huit types de détenus différents possibles. En effet, via ces documents on comprend que 

1. Le détenu est soit de genre Masculin ou de genre Féminin. 
2. Le détenu est ou prévenu ou condamné. 
3. et enfin, le détenu est interné ou non. `

Ainsi, selon la typologie du ministère public il existe bien huit manières différentes d'appréhender les détenus.

Sans égard pour la question du genre, nous avons représenté les parts respectives des différents types de détenus au sein des prisons. Comme on peut l'observer, la grande majorité des détenus sont soit prévénus, soit condamnés. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/repart.jpg" alt="statuts"></div>

#### les internés

- Si on s'attelle uniquement à l'étude des déténus dit "internés", on remarque qu'il sont placés dans dix établissements   différents et selon une distibution beaucoup moins uniforme que ce que nous avons pu observer pour les détenus en général. Paifve semble détenir uniquement des détenus de ce type alors que les internés représentent 25 % des effectfis totaux de detenus au sein de la prison historique de Merklpass.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/Intbarplot.jpeg" alt="barplot"></div>

- Notons aussi qu'un *test de student* sur les moyennes des pénitenciers au Nord et au sud de Bruxelles ne révèle aucune différences significatives. Autrement dit, après une brève analyse statistique, on ne peut pas affirmer, par exemple, que les internés sont, en moyenne, dans le sud du Royaume, plus regroupés ensemble que dans le reste du royaume de Belgique.

#### les prévenus 

- Si on s'attelle uniquement à l'étude des déténus dit "Prévenus", on remarque qu'il sont présents dans la quasi totalités des pénitenciers. Cependant, la distribution des prévenus au sein des prisons n'en est pas pour autant plus uniforme au sein du système carcéral. On remarque en particulier que la majorité des des prévenus sont détenus à Lantin, Saint-Gilles ou Merklpass. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus_distribution.jpg" alt="distribution des prevenus"></div>

- Notons en outre que seulement 7 pénitenciers sur les 38  considérés - Hoogstraten, Leuven Centraal, Maison de transition Malines, Ruiselede, Maison de transition d'Enghien, Paifve, et St. Hubert - ne détiennent aucun prévenus.

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus.jpg" alt="prevenu"></div>


#### les condamnés

Remarquons derechef que les détenus dit condamnés sont présents dans toutes les prisons sauf à Paifve. Ainsi, si on s'attelle uniquement à l'étude de ceux-ci, comparativement aux autres statuts de détenus, $$\Pi^{h}_{i}= \frac{d^{h}_{i}}{N}$$, la distribution des condamnés au sein des prisons admet une distribution plus uniforme au sein du système carcéral que les autres distributions analysées jusqu'ici. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/comdamne_distribution.jpg" alt="distribution des condamnés"></div>

Notons en outre que si on s'intéresse à la part des détenus condamnés parmis les detenus d'une prison, soit $$\pi^{h}_{i}= \frac{d^{h}_{i}}{n_i}$$, deux faits statistiques emrgent rapidement.

1. Premièrement, seulement 2 pénitenciers sur 38 n'acceuillent que des détenus condamnés : les deux maisons de transition de Maligne et Enghien. 
2. Deuxièmement, au premier coup d'oeil, on remarquera trois types de pénitenciers en matière de détentions de condamnés: 

- Les pénitenciers s'occupant uniquement de détenus condamnés.
- Les pétitenciers avec plus 50 % de détenus condamnés.
- Les pénitenciers avec moins de 25 % de détenus condamnés.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distribution_jail.jpg" alt="Pourcentage de Condamnés par Prison"></div>

Ici encore, on peut remarquer que la part des détenus condamnés au sein des détenus des 38 prison est asymétrique. Comme on peut le voir sur la graphique suivant, plus de la moitié des prisons détiennent plus de 55% de détenus comdamnés entre leurs murs. Notons en oute, qu'en moyenne, le pourcentage de détenus condamnés parmis la population des détenus d'une prison est de 66% alors que 25% des prisons acceuillent en leurs murs une population essentiellement composée de détenus comdamnés, soit une population plus de neuf détenus sur dix (*i.e.* le 3ème quartile : 93%). 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distr_con.jpg" alt="Histogramme des pourcentages de Comdamnés dans la population d'une Prison"></div>

### les personnnels en charge des détenus

#### le personnel au sein des établissements pénitenciaires

> "l'administration pénitentiaire est un service du SPF Justice depuis 1830. Elle est organisée d'une part en Direction génrale des établissements pénitentiaires (DG EPI) et d'autre part en services extérieurs où figurent les 33 établissements pénitentiaires. La mission de son directeur s'inscrit dans le cadre géénral de l'excécution des peines, qui doit être compatible avec le respect des droits fondamentaux  des individus"<sup id="a1">[1](#f1)</sup> 


<b id="f1">1</b> Le guide du Prisonnier en Belgique, sous la dir.  Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc pire, 2016, p.29[↩](#a1)

