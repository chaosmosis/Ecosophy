---
layout: post
title: "Covid in jail "
categories: prison
author: "John Nève"
meta: "sante"
---

# Esquisse de la situation dans les prisons du Royaume de Belgique.

## Introduction

Vu l'urgence, l'enjeu de ce petit texte est de faire un pont entre les statistiques dont dispose l'administration pénitentiaire pour qualifier les conditions de vie des détenus au sein de ses lieux de détentions et les mesures à prendre lors du *déconfinement* attendu.

Ainsi, ici et maintenant, en mobilisant les rares données rendues disponibles par l'administration pénitentiaire, bien souvent sous la pression des organismes de contrôle aux mains du pouvoir législatif - à une heure où seulement les diplomates, les avocats et avocates des détenus sont autorisés à entrer en contact avec les détenus<sup id="a7">[7](#f7)</sup>, je vous propose ici de procéder à une brève analyse descriptive de ces statistiques. Statistiques, qui, comme toutes statistiques pénitentiaires, ont le mérite d'être, quoique peu nombreuses, aussi, une approximation de la manière dont l'administration du Royaume de Belgique appréhende les personnes qu'elle administre tant que faire se peut.<sup id="a6">[6](#f6)</sup>. 

Dans un premier temps, il s'agira donc de s'entendre sur quelques unes des définitions qui nous serviront dans la suite de ce texte. Celles-ci - moyennes, médiane, pourcentages, etc. - nous permettront, d'une part,  dans les deuxième, troisième et quatrième temps, de jauger de la *"concentration des détenus"* au sein des prisons et d'autre part, d'évaluer la *"distribution des personnels"* au sein du système carcérale belge.

En effet, outillés de ces notations pour l'analyse du nombre de détenus par prison et selon leurs "statuts légaux", après avoir étudié brièvement les nombres relatifs aux personnels agissant au seins des prisons, nous reviendrons sur les statistiques dont nous disposons concernant les "capacités de production" où se rencontrent les deux entités phares de tout système carcérale : les détenus et les personnels de surveillance. 

Nous illustrerons avec la Prison-le-leuze les problèmes que semblent poser, au sein de cette prison, une concentration de détenus et une distribution des personnels hérités d'une politique pénitentiaire actuarielle et, quoiqu'en disent les autorités en charge actuellement, structurellement inhumaine.
 
Ainsi, dans un cinquième et dernier temps, et en guise de conclusion, nous terminerons par interroger,  à l'aune des données que nous avons réussi à récolter et présentés aux temps précédents, "le plan judiciaire à l'heure du corona virus" que le Ministre de la Justice, Koen Geens, a soumis à la chambre de députés au mois d'avril 2020.



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

## Notations pour les Prisons

### N'est pas détenu qui veut. 

> "Aucune personne ne peut être administrée ou retenu dans une prison en qualité de détenu sans une ordonnance d'incarcération valable, conformément au droit interne"

Alors que cet extrait de la Recommandation Européenne sur les Règles Pénitentiaires est clair quant à la naissance de la "qualité de détenu" au sein d'une prison et au sein des pays membres du conseil de l'Europe, nous restons sur notre fin quant à savoir ce qu'est un détenu du point de vue de ce règlement. 

A tout le moins, on comprend néanmoins que le nombre de personnes détenues au sein d'un système carcérale donnée devraient dépendre directement du travail opéré par un autorité territoriale et pyramidale. 

En Belgique, l'article  12 de la Constitution, 3ème alinéa, n'est pas plus clair sur ce qui fait le détenu  mais nous permet de qualifier une partie de ce pouvoir territoriale et structurer de manière pyramidale en la personne du juge :

> "Nul ne peut être arrêté qu'en vertu de l'ordonnance motivée du juge"

En définitive, comme on peut le lire dans le Guide du Prisonnier en Belgique, on comprend vite qu'*"Une décision judiciaire(ordonnance de mise en détention préventive, jugement, etc.) est toujours nécessaire"*<sup id="a0">[0](#f0)</sup> pour être considéré comme un détenu en prison mais on reste toujours sans définition du détenu en tant que tel.

Les tableaux statistiques distribués par le ministère public témoignent quant à eux des différents statuts attribués aux individus qui peuplent les prison du Royaume de Belgique. Quoique sommaires, ces documents traduisent sans conteste un attachement certains, de la part des directeurs de prisons, aux différences de statuts des détenus mais aussi d'une partie de la réalité à laquelle sont confrontés ces derniers, notamment lorsque l'on considères les différents personnels qui travaillent au jour le jour au sein de ces prisons.

Au regard de ces seuls classements, si on s'intéresse premièrement aux "détenus", il semble exister, dans le chef des autorités responsables des statistiques relatives aux détenus,  au moins huit types de détenus possibles : 

1. Alors qu'il sera ou interné ou prévenu ou condamné ou encore mis à disposition du tribunal de l'application des peines,
2. le détenu sera nécessairement  ou de genre Masculin ou de genre Féminin. 

Comme on le comprend, selon la typologie dont use l'administration pénitentiaire en général,  il existe donc potentiellement huit manières différentes d'appréhender les détenus au sein d'une prison.


#### quelques symbolisations et définitions

Désignons par $i$ l'une des $I$ prisons du Royaume et par $$ n_i $$, le nombre de détenus au sein de la prison $$i$$. Si il existe un nombre déterminé de prisons, disons $$I$$ (e.g $$ I \in \mathbf{R} $$), sur un territoire, le nombre total de détenus au sein des prison peut être défini comme la somme du nombre de détenus *au sein* des $$I$$ du dit territoire, autrement dit :

$$ N = \sum_{I} n_{i} $$ 

Supposons ensuite que pour chaque prison $$i$$, il existe une valeur symbolisant une "capacité théorique", ci-après dénotée $$ \xi_i $$. En procédant de manière similaire que pour le  nombre de détenus, désignons la capacité totale de détention du système carcérale par $$ \Xi $$ et  posons :

$$ \Xi \equiv \sum_{I} \xi_{i} $$ 

Enfin, désignons par $$g_i$$ le nombre de salariés travaillant au sein de la prison $$i$$ et, dans la foulée des définitions précédentes, désignons par $$G$$ le nombre total de salariés oeuvrant à la reproduction des tâches journalières auxquelles sont confronté les membres du système carcérale fédéral, autrement dit :

$$ G = \sum_{I} g_{i} $$ 


De cette manière on pouvons définir une série d'indicateurs qui nous permettront de réaliser une brève analyse statistique descriptive des tableaux de données rendus disponibles par les étbalissements pénitentiers pour la gestion et au contrôle des prisons.

A cette fin, notons notamment que la moyenne de détenu dans une des $$I$$ prisons peut être définie de la manière suivante :
 
 <div style="text-align: center">
 $$ \overline{N} = \frac{ \sum_{I} n_{i} }{ I }$$ 
 </div>
 
 De même, la capacité de détention moyenne d'une prison sur le territoire  peut être définie de la manière suivante :

  <div style="text-align: center">
 $$\overline{\Xi} = \frac{ \sum_{I} \xi_{i} }{ G }$$
  </div>
 
Dans la foulée, nous symboliserons par $$\overline{G}$$ le nombre moyen de personnels au sein d'une prison $$i$$ :

  <div style="text-align: center">
$$\overline{G} = \frac{ \sum_{I} G_{i} }{ G }$$
  </div>
  
Enfin, sachant qu'au cours de l'analyse descritive, afin de faire parler au mieux les données de l'administration pénitentiaire, nous distinguerons les détenus par selon, au moins quatre types, il va nous être utile de désigner par : 
 - $$n^{h}_{i}$$, le nombre de détenus de type $$ h $$ détenu dans $$ i $$
 - $$\pi_{i} = \frac{\sum_{H}n^{h}_{i}}{N} = \frac{n_i}{N}$$, le part des détenus détenus dans $$i$$ parmi tous les détenus
 - $$\pi^{h}_{i}= \frac{n^{h}_{i}}{n_i}$$, le pourcentage de détenus de type $$ h $$ détenus parmi les détenus détenus dans $$i$$
 - $$\Pi^{h} = \frac{\sum_{I}n^{h}_{i}}{N}$$, le pourcentage de détenus de type $$h$$ parmi tous les détenus.
 - $$\Pi^{h}_{i}= \frac{n^{h}_{i}}{N}$$, la part des détenus de type $$ h $$ détenus dans $$i$$ parmi tous les détenus.
 
 Terminons par rappelons trois des autres définitions séculaires de la statistique descriptive, à savoir, la médiane, le minium et le maximum  reprise dans les documents du conseil de l'Europe : 
 
 
 En l'espèce, nous supposons donc qu'au sein des $$I$$ prisons fédérales du pays, il y a

- $$ N = \sum_{I} n_{i} $$ détenus pour

- $$ \Xi = \sum_{I} \xi_{i} $$ lits et 

- $$ G = \sum_{I} g_{i} $$ intervenants salariés.

 

### Analyse descriptive des données relatives aux nombres des détenus en Prison



### Les détenus au sein des prisons

Comme on peut s'y attendre, le nombre de détenu dans une prison, ci-après $$n_i$$, varie énormément d'une prison à une autre. Les raison de ces variations est l'objet d'une littérature abondante sur la population des prisons. Littérature d'autant plus abondante en Belgique, que depuis la première visite du comité européen pour la prévention de la Torture en Belgique, ce pays n'a eu de cesse de se faire vilipendé par les organismes internationaux et nationaux.

La prison qui comptabilise le moins de détenus est la maison de transition d'Enghien. Celle qui dénombre le plus grand nombre de détenus est la prison de Lantin. En moyenne, il y a 166 détenus par prison alors que la moitié des détenus sont regroupés dans des prisons avec plus de 147 détenus. 

```{r} 
tot=as.data.frame(prison[,2]+prison[,3]+prison[,4])
data=cbind(prison[,1],tot)
data=data[order(data[,2],decreasing=T), ]
p<-ggplot(data=data, aes(x=tot, y=name)) +  geom_bar(stat="identity")
p
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/histo_prison.jpg" alt="systeme"></div>

Le graphique suivant nous permet d'observer la distribution des effectifs de détenus au sein des prisons. Une grande hétérogénéité y apparait. Celle-ci traduit probablement une réalité immobilière concrète mais nous reviendrons sur cette interprétation plus tard. Pour l'instant, contentons-nous de constater que plus de la moitié des détenus sont groupés dans des prisons détenant un nombre de détenus inférieur au nombre moyen de détenus par prison. Dans de pareilles situation, on dit que la distribution des effectifs d'une variable est asymétrique. 

Le cas présent traduit ce phénomène puisque la distribution des détenus au sein du système carcéral est telle que la majorité des détenus sont détenus au sein de prisons ayant des effectifs de détenus inférieurs au nombre moyen de détenus par prison. Autrement dit, pour ces prisons, $$n_i$$ est inférieur à $$\overline{N}$$.

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

Au sein des 38 espaces fédéraux réservés à la détention des personnes physiques, le SPF justice comptabilise aujourd'hui un total de 9881 détenus emmurés.

Nous reviendrons plus loins sur les personnes détenues hors-les-murs des établissements pénitentiaires mais dépendant de ceux-ci.

### Description des types de détenus au sein des pénitenciers



Sans égard pour l'instant relativement à la question du genre, nous avons représenté dans le graphique suivant les parts respectives des différents types de détenus au sein des prisons qui relèvent du champs de compétence du ministre de la Justice, $$\Pi^{h} = \frac{\sum_{I}n^{h}_{i}}{N}$$. 

Comme on peut l'observer, au sein de ces prisons, au cours du mois d'avril 2020, la grande majorité des détenus sont soit prévenus, soit condamnés. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/repart.jpg" alt="statuts"></div>

#### les internés

Si on s'attelle uniquement à une sommaire description des nombres décrivant les détenus dit "internés", on remarque que ces détenus sont placés dans dix établissements différents et selon une distribution beaucoup moins uniforme que la distribution que nous avons pu observer pour l'ensemble des détenus. 

Au vu de son statut particulier, comme on peut s'y attendre, Paifve détenait, au mois d'avril 2020, uniquement des détenus internés. Selon ce même classement, remarquons aussi la part importante des internés, $$\pi^{h}_{i}= \frac{n^{h}_{i}}{n_i}= 0,25$$, au sein de la prison de Merklpass. 


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/Intbarplot.jpeg" alt="barplot"></div>

#### les prévenus 

Si on s'attelle  maintenant à décrire quelques statistiques description, on remarquera que les détenus dit "Prévenus" sont présents dans la quasi totalités des pénitenciers. Cependant, la distribution des prévenus au sein des prisons n'en est pas pour autant uniforme au sein du système carcéral. On remarque en particulier que la plupart des prévenus sont détenus à Lantin, Saint-Gilles, Bruges ou Merklpass. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus_distribution.jpg" alt="distribution des prevenus"></div>

- Notons en outre que seulement 7 pénitenciers sur les 38  considérés - Hoogstraten, Leuven Centraal, Maison de transition Malines, Ruiselede, Maison de transition d'Enghien, Paifve, et St. Hubert - ne détiennent aucun prévenus.

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus.jpg" alt="prevenu"></div>

#### les condamnés

Remarquons derechef que les détenus dit condamnés sont présents dans toutes les prisons, sauf à Paifve.  Si on s'attelle uniquement à l'étude de ceux-ci, comparativement aux autres statuts de détenus, la distribution  de la part des individus de types $$h$$ au sein des prisons, soit la distribution statistique de $$\Pi^{h}_{i}= \frac{d^{h}_{i}}{N}$$, admet une distribution plus uniforme au sein du système carcéral que les autres distributions analysées jusqu'ici. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/comdamne_distribution.jpg" alt="distribution des condamnés"></div>

Notons en outre que si on s'intéresse à la part des détenus condamnés parmi les détenus d'une prison, soit $$\pi^{h}_{i}= \frac{d^{h}_{i}}{n_i}$$, deux faits statistiques émergent rapidement. 

1. Premièrement, seulement 2 pénitenciers sur 38 n'accueillent que des détenus condamnés : les deux maisons de transition de Maligne et Enghien. 
2. Deuxièmement, on remarquera aussi trois types de pénitenciers en matière de détentions de condamnés: 

- Les pénitenciers s'occupant uniquement de détenus condamnés.
- Les pénitenciers avec plus 50 % de détenus condamnés.
- Les pénitenciers avec moins de 25 % de détenus condamnés.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distribution_jail.jpg" alt="Pourcentage de Condamnés par Prison"></div>

Ici encore, on peut remarquer que la  distribution des détenus condamnés au sein des détenus des 38 prisons est asymétrique. Comme on peut le voir sur la graphique suivant, plus de la moitié des prisons détiennent plus de 55% de détenus condamnés entre leurs murs. 

Cette asymétrie est telle qu'on remarquera en outre qu'alors qu'en moyenne le pourcentage de détenus condamnés parmi la population d'une prison est de plus 66%, 25% des prisons accueillent en leurs murs une population essentiellement composée de détenus condamnés, soit de plus de neuf détenus sur dix (*i.e.* le 3ème quartile : 93%). 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distr_con.jpg" alt="Histogramme des pourcentages de Condamnés dans la population d'une Prison"></div>

### Analyse descriptive des données relatives aux personnels en charge des détenus

Alors que la qualification de détenu dépend directement de l'action de la magistrature assise du pouvoir judiciaire, les personnels qui concourent à la concorde ou à la discorde au sein d'un établissement pénitentiaire sont l'oeuvres de nombreuses instances. 

En Belgique, "l'administration pénitentiaire " a un rôle pivot dans l'organisation des personnels en charge des détenus. 

> "l'administration pénitentiaire est un service du SPF Justice depuis 1830. Elle est organisée d'une part en Direction générale des établissements pénitentiaires (DG EPI) et d'autre part en services extérieurs où figurent les 33 établissements pénitentiaires. La mission de son directeur s'inscrit dans le cadre général de l'exécution des peines, qui doit être compatible avec le respect des droits fondamentaux  des individus"<sup id="a1">[1](#f1)</sup> 

### le personnel au sein des établissements pénitentiaires

<div style="text-align: right"><img src="{{ site.baseurl }}/assets/sempe.jpg" alt="sempe" style="width:175px;" ></div>

Au sein des établissements pénitentiaires, l'organisation du travail du personnel en charge des détenus offre à voir une structure très hiérarchisée.

> *"La direction d'un établissement comprend le directeur, et le cas échéant, le(s) sous-directeur(s); ils sont placés sous l'autorité hiérarchiques du ministre de la Justice . Les membres de la direction dirigent l'établissement conformément aux principes modernes de gestion et aux principes de droits nationaux et internationaux, tant sur le plan individuel qu'aux niveau des équipes".*<sup id="a2">[2](#f2)</sup> 

En face des postes de direction, le restant du personnel de surveillance au sein d'un établissement pénitentiaire est d'au moins quatre types selon le guide du Prisonnier : assistant pénitentiaire, chef surveillant, chefs de quartier, et agents pénitentiaires.

> *"Chaque surveillant porte un uniforme qui diffère selon son grade."*<sup id="a3">[3](#f3)</sup> 

Si on s'en tient aux notations proposées ci-dessus, $$g_{i}$$ pourrait représenter maintenant le nombre d'individus s'identifiant à ces deux types de personnel au sein d'un des $$I$$ établissements pénitenciers et nous pourrions définir dans la foulée le nombre moyen de personnes salariée dépendant directement du ministre de la Justice via la Direction Générale de l'Administration Pénitentiaire comme :

 
 <div style="text-align: center">
 $$ \overline{G} = \frac{ \sum_{I} g_{i} }{ G }$$ 
 </div>
 

#### Le Comité de Concertation de base

Le comité de concertation de base est probablement l'organe dont on a le plus entendu parler dans les médias ces dernières années. Probablement car c'est aussi un organe clef dans la reproduction journalière de l'organisation du travail au sein des établissements pénitenciers.

> *"Il s'agit d'un organe de concertation de la direction de la prison et les organisation syndicales. Ce comité est notamment chargé d'organiser et d'améliorer les conditions de travail du personnel pénitentiaire. Dans ce cadre, les décision qui y sont prises peuvent  avoir des conséquences sur le régime pénitentiaire et la vie en prison puisque le lieu de travail du personnel est le même que le lieu de vie des détenus."*<sup id="a4">[4](#f4)</sup> 

Dans les documents fournis par le CCSP, les chiffres concernant  les effectifs de ces personnels au sein des établissements pénitenciers sont les résultantes du protocole 464. 

Les valeurs que prennent ces nombres ne dépendent plus des Juges comme dans le cas des détenus, mais directement de cette interface relativement informelle entre l'organe de contrôle du personnel et le personnel en tant que tel.

#### le distribution du personnel au sein des établissements pénitentiaires

Comme on pouvait s'en douter, les statistiques représentés dans le graphique ci-dessous témoignent d'une distribution des effectifs par prison asymétrique. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/perso.jpg" alt="Distribution négociée des effectifs"></div>

Le graphique précédent se base sur les effectifs négociés dans le cadre du comité de concertation de base. Dans réalité, les directeurs de établissements pénitenciers et ceux et celles qui les assistent organisent le travail attenant aux détenus en comptant avec une main-d'oeuvre réduite. Il semblerait que cette main d'oeuvre réduite, soit dénommée, dans les classements du ministère de la Justice, comme des  "effectifs opérationnels".

Ainsi, d'après ces statistiques, seuls sept prisons avaient, au début du mois d'avril 2020, des effectifs opérationnels légèrement supérieurs aux effectifs négociés avec les syndicats. Avant d'aborder plus en détails les établissements pénitenciers avec un effectif opérationnel bien inférieur à l'effectif théorique, notons que la seule Prison de Berkendael satisfaisait, le 9 mars 2020,  aux effectifs résultants d'un Protocole 464.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/diff.jpg" alt="Différences"></div>


<b id="f0">0</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.19[↩](#a0)

<b id="f1">1</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.29[↩](#a1)

<b id="f2">2</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.30[↩](#a2)

<b id="f3">3</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.31[↩](#a3)

<b id="f4">4</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.33[↩](#a4)


<b id="f4">5</b> Ficher, I., Guillain, C., « Du difficile équilibre entre le respect des droits fondamentaux des détenus et le droit à l’action collective des agents pénitentiaires » in Droit de grève : actualités et questions choisies, Bruxelles, Éditions Larcier, 2015, p. 87-124[↩](#a5)

<b id="f6">6</b> S'il y a bien une leçon du confinement instaurée en Belgique que l'on peut tirer maintenant , c'est bien le fait que la société civile a un rôle moteur dans la production de connaissances. En effet, cela surprendra probablement certaines d'entre nous - étant donné, notamment,  le régime en place dans les prisons à l'heure actuelle : surpopulation, suppressions des visites, défaut d'approvisionnement de certaines cantines- mais les associations informelles et non -gouvernementales redeviennent quasi les seules sources d'informations de premières mains - et différentes de celles provenant de l'administration pénitentiaire- relatives aux lieux de détentions et aux détenu.e.s au sein de ceux-là.[↩](#a6)

<b id="f7">7</b> Les différentes mesures misent en place dans les prisons ont été présentée aux députés et députées fédérales du Royaume le 8 avril 2020 : https://www.youtube.com/watch?v=CdreDHFtRcw [↩](#a7)
