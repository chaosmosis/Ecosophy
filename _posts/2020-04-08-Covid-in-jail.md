---
layout: post
title: "Covid in jail "
categories: prison
author: "John Nève"
meta: "sante"
---

# La situation dans les prisons du Royaume de Belgique.

## Introduction

Vu l'urgence, l'enjeu de ce petit texte est de faire un pont entre les statistiques dont dispose l'administration pénitenciaire pour qualifier les conditions de vie des détenus au sein de ses lieux de détentions et les mesures à prendre lors du déconfinement génralisée tant attendu à l'heure du "lockdown".

Cela surprendra probablement certaines d'entre nous - étant donné, notamment,  le régime en place dans les prisons à l'heure actuelle : surpopulation, suppressions des visites, défault d'approvisionnement de certaines cantines- mais les associations informelles et non -gouvernementales redeviennent quasi les seules sources d'informations de premières mains - et différentes de celles provenant de l'administration pénitenciaire- relatives aux lieux de détentions et aux détenu.e.s au sein de ceux-là.<sup id="a6">[6](#f6)</sup>. 

Toutefois, ici et maintenant, en moblisant les rares données rendues disponibles par l'administration pénitentiaire, bien sousvent sous la pressions des orgnismes de controle aux mains du pouvoir législatif - à une heure où seulement les diplomates, les avocats et avocates des détenus sont autorisés à entrer en contact avec les détenus, je vous propose ici de procéder à une brève analyse descriptive de ces statistiques. Statistiques, qui, comme toutes statistiques pénitenciaires, ont le mérite d'être, quoique peu nombreuses, aussi, une approximation de la manière dont l'administration du Royaume de Belgique appréhende les personnes qu'elle administre tant que faire se peut.

Dans un premier temps, il s'agira dés maintenant de s'entendre sur quelques une des défintions qui nous serviront dans la suite de ce texte. Celles-ci - moyennnes, médiane, pourcentages, etc.. - nous permettront, d'une part,  dans les  deuxième troisième et quatrième temps, de jauger de la "concentration"  des "détenus" au sein des prisons et d'autre part, d'évaluer la distribution, sous la houlette du ministre actuel de la Justice,  des personnels au sein du système carcérale belge.

En effet, outillés de ces notations pour l'analyse du nombre de détenus par prison et selon leurs "statuts légaux", après avoir étudié brièvement les nombres relatifs aux personnels agissant au seins des prisons, nous reviendrons sur les statistques dont nous disposons concernant les "capacités de production" où rencontrent les deux entités phares de tout système carcérale : les déténus et les personnels de surveillance. Nous illustrerons avec la Prison-le-leuze les problemes que semblent poser, au sein de cette prison, une concentration de détenus et une distribution des personnelles hérités d'une politique pénitenciaire actuarielle et, quoiqu'en disent les autorités en charge actuellement, structurellement inhumaine.
 
Ainsi, dans un cinquième et dernier termps, et en guise de conclusion, nous terminerons par interroger,  à l'aune des données que nous avons réussi à récolter et présentés aux temps précédents, "le plan judiciaire à l'heure du corona virus" et les possibles points d'inflexions que le Ministre de la Justice, Koen Geens, a présenté à la chambre de députés au mois d'avril 2020.



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


Au sein des pays membres du conseil de l'Europe, le nombre de personnes détenues au sein d'un système carcérale devraient dépendre directement du travail opéré d'un démarche juridique singulière.

> "Aucune personne ne peut être administrée ou retenu dans une prison en qualité de détenu sans une ordonnance d'incarcération valable, conformément au droit interne"

Cet extrait de la Recommandation Européenne sur les Règles Pénitentiaires est clair, il faut l'aval d'une autorité publique pour être qualifié de détenu. à tout le moins, afin d'avoir le titre de détenu en prison. 

En Belgique, comme le veut l'article  12 de la Constitution, 3ème alinéa :

> "Nul ne peut être arrêté qu'en vertu de l'ordonnance motivée du juge"

Ainsi, comme on peut le lire dans le Guide du Prisonnier en Belgique, on comprend vite qu'*"Une décision judiciaire(ordonnance de mise en détention préventive, jugement, etc.) est toujours nécessaire"*<sup id="a0">[0](#f0)</sup> pour être considéré comme un détenu en prison.

#### Les facteurs influencantles nombres des détenus

Dés lors, même s'il existe très probablement *un seuil* , comme le pense la théorie du choix rationnel, à partir duquel un agent économique - diligent et pro-actif- décide de s'inscrire dans un devenir de détenu, on voit bien que la réalité dans laquelle la décision sera prise implique que la décision n'appartient pas directement, ou en tout cas uniquement aux choix de d'un individu.

Les outils de la théorie des jeux peuvent nous aider à démontrer rapidement que quand bien même le crime résulterait d'un choix, ce choix n'en est pas la résultant d'un processus interactif entre l'individu et ce qui l'entoure.


Pour ce faire, l'instar de ce qui se fait dans la théorie du choix rationnel lorsqu'il s'agit d'appréhender des agents économiques, il s'agit de prendre en compte l'état de joie, ou de félicité, que les agents ressentent dans différents contextes. 

Imaginons un  jeu. Dans celui-ci, la configuration des paiemens associté à chacun aux états du monde possibles est telle qu'elle implique une dépendance claire des choix de devenir de chacun des acteurs.  Prenons le jeu bien connu des économistes de la bataille des sexes. Dans celui-ci, il existe on dit géénralement qu'il *existe deux équilibres de Nash en stratégie pure*

Dans l'un, on pourrait dire que on a affaire à une situation de banditisme généralisé ù la société a décide de ne plus sataisfaire les prérequis de l'état de droit et où l'individu lui aussi à décidé de ne plus suivre les règles.  En réalité sont choix et tout à fait dépendant du choix de son "adversaire" dans le jeu considéré.  

EN effet, si la socité venait à changer de startégie et à faire respecter l'état de droit, l'agent  économique trouverait plus rationnel de s'incrire désormais dans  un devenir légaliste. De même que la théoie des jeux a permis de mettre à genoux la théorie de la concurrence parfaire en sciences économiques, elle a, outillé d'une réprésentation *à la becker* des individus, le mérite de rompre le coup à l'idée selon laquelle, logiquement, on est soit criminel ou non criminel lorsque l'on a a décidé de sa vie.



Les tableaux statistiques distribués par le ministère public témoignent des différents statuts attribués aux individus qui peulples les prison du Royaume de Belgique. Quoique sommaires, ces documents traduisent sans conteste un attachement certains, de la part des directeurs de prisons, aux différences de statuts des détenus mais aussi d'une partie de la réalité auquelle sont confrontés ces derniers.

Au regard de ces seuls classements, il semble exister dans le chefs des autorités responsables des statsitques relatives aux détenus au moins huit types de détenus possibles. En effet, via ces documents on comprend que 

1. Alors qu'il sera ou détenu ou prévenu ou condamné ou encore mis à disposition du tribunal de l'application des peines.
2. Le détenu sera soit de genre Masculin, soit de genre Féminin. 

Ainsi, selon la typologie dont use l'administration pénitentiaire en général,  il existe bien potentiellement huit manières différentes d'appréhender les détenus au sein d'une prison.

$$\begin{tabular}{|c|c|c|} u_1 & \Rightarrow & u_2 \\ \end{tabular} \end{center} $$



Ces outils nous permettent de penser l'acuqisition du titre de détenus dans termes, quoique provicateurs, qui n'en sont pas moins évocateurs de la manière dont la politique carcérale est menée aujourd'hui. 

En effet, alors que la théorie du choix rationnele raisson en termes de choix entre des états de monde possibles, où l'ensemble des mondes possibles est donnée par ce qu'on appelle comunément le modélisateur, la manière dont les politiques appréhendent et ont appréhender les politqiues carcérale s'est, dans leurs majorité soldé par une vision du type de celle de l'école de chicago. 
Selon cette vision, le crime et partant, le statut de détenu est, in fine, une affaire de choix. 

Ainsi, il sera courant de faire l'hypothèse que ce qu'on appelle communément le joueur $$1$$ est en réalité un individu  exepté qu'il est tourmenter par le fait de devenir bandir ou de devenir un bon père de Famille. Pour cette théorie, * poussée dans ses limites*, acquérir le statut de détenu est le choix de vie, un choi rationnel, autrement dit, réflexif et complet. Si on le simplifie à l'extrême ce choix, cela revient à dire qu'un détenu a son arc deux stratégie possible un jour où l'autres : soit devenir Bandit, soit Travailler comme monsieur et madame tout-le-monde.

Imaginons que le fait de choisir le devenir bandit ou le devenir légaliste est le fait d'un jeu en interaction stratégique avec ce que l'on pourrait appeler la société. 

Par tourmenté j'entends qu'il a l'impression qu'il joue un jeu avec la société et où la société, elle même oscillent entre un devenir légaliste et un devenir bandit. 



$$\begin{center}\begin{tabular}{|c|c|c|}\hline & \textit{Bandit}    & \textit{bon Père de famille} \\ \hline \textit{Bandit} & \textit{a,b}    &  \textit{c,d} \\ \hline \textit{P} & \textit{e,f}  & \textit{g,h}\\ \hline \end{tabular} \end{center}$$

Dans une telle situation, il est rationnel d'élire le devenir bandit diront les théoriciens des jeux. Évidemment, cette configuration des paiements est tout à fait arbitraire. Elle n'est pas la seule configuration possible qui permette l’avènement du banditisme généralisé.



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
 
 - $$n^{h}_{i}$$, le nombre de détenus de type $$ h $$ détenu dans $$ i $$
 - $$\pi_{i} = \frac{\sum_{H}n^{h}_{i}}{N} = \frac{n_i}{N}$$, le part des détenus détenus dans $$i$$ parmis tous les détenus
 - $$\pi^{h}_{i}= \frac{n^{h}_{i}}{n_i}$$, le pourcentage de détenus de type $$ h $$ détenus parmis les détenus détenus dans $$i$$
 - $$\Pi^{h} = \frac{\sum_{I}n^{h}_{i}}{N}$$, le pourcentage de détenus de type $$h$$ parmis tous les détenus.
 - $$\Pi^{h}_{i}= \frac{n^{h}_{i}}{N}$$, la part des détenus de type $$ h $$ détenus dans $$i$$ parmis tous les détenus.
 
 

### Analyse descriptive des données relatives aux nombres des détenus en Prison



### Les détenus au sein des prisons

Le nombre de détenu dans une prison, ci-après $$n_i$$, varie énormément d'une prison à une autre. Les raison de ces variation est l'objet d'une littérature abondante sur la population des prisons. Littérature d'autant plus abodnante en belgique, que depuis la première visite du comité européen pour la prévention de la Torture en belgique, ce pays n'a eu de cesse de se faire vilenpendé par les organismes internationaux et nationaux.

La prison qui comptabilise le moins de détenus est la maison de transition d'Enghien. Celle qui dénombre le plus grand nombre de détenus est la prison de Lantin. En moyenne, il y a 166 détenus par prison alors que la moitié des détenus sont regroupés dans des prisons avec plus de 147 détenus. 

```{r} 
tot=as.data.frame(prison[,2]+prison[,3]+prison[,4])
data=cbind(prison[,1],tot)
data=data[order(data[,2],decreasing=T), ]
p<-ggplot(data=data, aes(x=tot, y=name)) +  geom_bar(stat="identity")
p
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/histo_prison.jpg" alt="systeme"></div>

Le graphique suivant nous permet d'observer la distribution des effectifs de détenus au sein des prisons. Une grande hétérogénité y apparait. Celle-ci traduit probablement une réalité immobilière concrète mais nous reviendrons sur cette interprétation plus tard. 

Pour l'instant, contentons-nous de constater que plus de la moitié des détenus sontregroupés dans des prisons détenant un nombre de détenus inférieur au nombre moyen de détenus par prison. Dans de pareilles situation, on dit que la distibution des effectifs est d'une variable est asymétrie. Le cas présent traduit ce phénomène puisque la distribution des détenus au sein du système carcéral est telle que la majorité des détenus sont détenus au sein de prisons ayant des effectifs de détenus inférieurs au nombre moyen de détenus par prison. Autrement dit, $$n_i$$ est inférieur à $$\overline{N}$$.

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



Sans égard pour l'instant relativement à la question du genre, nous avons représenté dans le graphique suivant les parts respectives des différents types de détenus au sein des prisons qui relèvent du champs de compétence du ministre de la Justice, $$\Pi^{h} = \frac{\sum_{I}n^{h}_{i}}{N}$$. 

Comme on peut l'observer, au sein de ces prisons, au cours du mois d'avril 2020, la grande majorité des détenus sont soit prévénus, soit condamnés. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/repart.jpg" alt="statuts"></div>

#### les internés

Si on s'attelle uniquement à une sommaire description des nombres décrivant les déténus dit "internés", on remarque que ces détenus sont placés dans dix établissements différents et selon une distibution beaucoup moins uniforme que la distribution que nous avons pu observer pour l'ensemble des détenus. 

Au vu de son statut particulier, comme on peut s'y attendre, Paifve détenait, au mois d'avril 2020, uniquement des détenus internés. Selon ce même classement, remarquons aussi la part importante des internés, $$\pi^{h}_{i}= \frac{n^{h}_{i}}{n_i}= 0,25$$, au sein de la prison de Merklpass. 


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/Intbarplot.jpeg" alt="barplot"></div>

#### les prévenus 

Si on s'attelle  maintenant à décrire quelques statistiques description, on remarquera que les déténus dit "Prévenus" sont présents dans la quasi totalités des pénitenciers. Cependant, la distribution des prévenus au sein des prisons n'en est pas pour autant uniforme au sein du système carcéral. On remarque en particulier que la plupart des prévenus sont détenus à Lantin, Saint-Gilles, Bruges ou Merklpass. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus_distribution.jpg" alt="distribution des prevenus"></div>

- Notons en outre que seulement 7 pénitenciers sur les 38  considérés - Hoogstraten, Leuven Centraal, Maison de transition Malines, Ruiselede, Maison de transition d'Enghien, Paifve, et St. Hubert - ne détiennent aucun prévenus.

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/prevenus.jpg" alt="prevenu"></div>

#### les condamnés

Remarquons derechef que les détenus dit condamnés sont présents dans toutes les prisons, sauf à Paifve.  Si on s'attelle uniquement à l'étude de ceux-ci, comparativement aux autres statuts de détenus, la distribution  de la part des individus de typen $$h$$ au sein des prisons, soit la distribution statistique de $$\Pi^{h}_{i}= \frac{d^{h}_{i}}{N}$$, admet une distribution plus uniforme au sein du système carcéral que les autres distributions analysées jusqu'ici. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/comdamne_distribution.jpg" alt="distribution des condamnés"></div>

Notons en outre que si on s'intéresse à la part des détenus condamnés parmis les detenus d'une prison, soit $$\pi^{h}_{i}= \frac{d^{h}_{i}}{n_i}$$, deux faits statistiques émergent rapidement. 

1. Premièrement, seulement 2 pénitenciers sur 38 n'acceuillent que des détenus condamnés : les deux maisons de transition de Maligne et Enghien. 
2. Deuxièmement, on remarquera aussi trois types de pénitenciers en matière de détentions de condamnés: 

- Les pénitenciers s'occupant uniquement de détenus condamnés.
- Les pétitenciers avec plus 50 % de détenus condamnés.
- Les pénitenciers avec moins de 25 % de détenus condamnés.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distribution_jail.jpg" alt="Pourcentage de Condamnés par Prison"></div>

Ici encore, on peut remarquer que la  distribution des détenus condamnés au sein des détenus des 38 prisons est asymétrique. Comme on peut le voir sur la graphique suivant, plus de la moitié des prisons détiennent plus de 55% de détenus comdamnés entre leurs murs. 

Cette asymétrie est telle qu'on remarquera en outre qu'alors qu'en moyenne le pourcentage de détenus condamnés parmis la population d'une prison est de plus 66%, 25% des prisons acceuillent en leurs murs une population essentiellement composée de détenus comdamnés, soit de plus de neuf détenus sur dix (*i.e.* le 3ème quartile : 93%). 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/distr_con.jpg" alt="Histogramme des pourcentages de Comdamnés dans la population d'une Prison"></div>

### Analyse descriptive des données relatives aux personnnels en charge des détenus

Alors que la qualification de détenu dépend directement de l'action de la magistrature assise du pouvoir judiciaire, les personnels qui concourent à la concorde ou à la discorde au sein d'un établissement pénitentiaire sont l'oeuvres de nombreuses instances. 

En Belgique, "l'administration pénitentiaire " a un rôle pivot dans l'organsiation des personnels en chage des détenus. 

> "l'administration pénitentiaire est un service du SPF Justice depuis 1830. Elle est organisée d'une part en Direction générale des établissements pénitentiaires (DG EPI) et d'autre part en services extérieurs où figurent les 33 établissements pénitentiaires. La mission de son directeur s'inscrit dans le cadre général de l'excécution des peines, qui doit être compatible avec le respect des droits fondamentaux  des individus"<sup id="a1">[1](#f1)</sup> 

### le personnel au sein des établissements pénitenciaires

<div style="text-align: right"><img src="{{ site.baseurl }}/assets/sempe.jpg" alt="sempe" style="width:175px;" ></div>

Au sein des établissements pénitentiaires, l'organisation du travail du personnel en charge des détenus offre à voir une structure très hierarchisée.

> *"La direction d'un établissement comprend le directeur, et le cas échéant, le(s) sous-directeur(s); ils sont placés sous l'autorité hierarchiques du ministre de la Justice . Les membres de la direction dirigent l'établissement conformément aux principes modernes de gestion et aux principes de droits nationaux et internationaux, tant sur le plan individuel qu'aux niveau des équipes".*<sup id="a2">[2](#f2)</sup> 

En face des postes de direction, le restant du personnel de surveillance au sein d'un établissement pénitenciaire est d'au moins quatre types selon le guide du Prisonnier : assistant pénitentiaire, chef surveillant, chefs de quartier, et agents pénitentiaires.

> *"Chaque surveillant porte un uniforme qui diffère selon son grade."*<sup id="a3">[3](#f3)</sup> 

Si on s'en tient aux notations proposées ci-dessus, $$g_{i}$$ pourrait représenter maintenant le nombre d'individus s'indentifiant à ces deux types de personnel au sein d'un des $$I$$ établissements pénitenciers et nous pourrions définir dans la foulée le nombre moyen de peronnes salariée dépendant directement du minitre de la Justice via la Direction Générale de l'Administration Pénitenciaire comme :

 
 <div style="text-align: center">
 $$ \overline{G} = \frac{ \sum_{I} g_{i} }{ G }$$ 
 </div>
 

#### Le Comité de Concertation de base

Le comité de concertation de base est probablement l'organe dont on a le plus entendu parler dans les médias ces dernières années. Probablement car c'est aussi un organe clef dans la reproduction journalière de l'organisation du travail au sein des établissements pénitenciers.

> *"Il s'agit d'un organe de concertation de la direction de la prison et les organisation syndicales. Ce comité est notamment chargé d'organiser et d'améliorer les conditions de travail du personnel pénitentiaire. Dans ce cadre, les décision qui y sont prises peuvent  avoir des conséquences sur le régime pénitentiaire et la vie en prison puisque le lieu de travail du personnel est le même que le lieu de vie des détenus."*<sup id="a4">[4](#f4)</sup> 

Dans les documents fournis par le CCSP, les chiffres concernant  les effectifs de ces personnels au sein des établissements pénitenciers sont les résultantes du protocole 464. 

Les valeurs que prennent ces nombres ne dépendent plus des Juges comme dans le cas des détenus, mais directement de cette interface relativement informelle entre l'organe de controle du personnel et le personnel en tant que tel.

#### le distribution du personnel au sein des établissements pénitenciaires

Comme on pouvait s'en douter, les statistiques représentés dans le graphique ci-dessous témoignent d'une distribution des effectifs par prison asymétrique. 

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/perso.jpg" alt="Distribution négociée des effectifs"></div>

Le graphique précédent se base sur les effectifs négociés dans le cadre du comité de concertation de base. Dans réalité, les directeurs de établissements pénitenciers et ceux et celles qui les assistent organisent le travail attenant aux détenus en comptant avec une main-d'oeuvre réduite. Il semblerait que cette main d'oeuvre réduite, soient dénomées, dans les classements du ministère de la Justice, comme des  "effectifs opérationnels".

Ainsi, d'après ces statistiques, seuls sept prisons avaient, au début du mois d'avril 2020, des effectifs opérationnels légérement supérieurs aux effectifs négociés avec les syndicats. Avant d'aborder plus en détails les établissements pénitenciers avec un effectif opérationnel bien inférieur à l'effectif théorique, notons que la seule Prison de Berkendael satisfaisait, le 9 mars 2020,  aux effectfis résulants d'un Protocole 464.


<div style="text-align: center"><img src="{{ site.baseurl }}/assets/diff.jpg" alt="Différences"></div>


<b id="f0">0</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.19[↩](#a0)

<b id="f1">1</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.29[↩](#a1)

<b id="f2">2</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.30[↩](#a2)

<b id="f3">3</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.31[↩](#a3)

<b id="f4">4</b> Le guide du Prisonnier en Belgique, sous la dir. de Marie-aude Beernaert, Philipppe Mary et Marc Nève, éditions Luc Pire, 2016, p.33[↩](#a4)


<b id="f4">5</b> Ficher, I., Guillain, C., « Du difficile équilibre entre le respect des droits fondamentaux des détenus et le droit à l’action collective des agents pénitentiaires » in Droit de grève : actualités et questions choisies, Bruxelles, Éditions Larcier, 2015, p. 87-124[↩](#a5)

<b id="f6">6</b> S'il y a bien une leçon du confinement instaurée en Belgique que l'on peut tirer maintenant , c'est bien le fait que la société civile a un rôle moteur dans la production de connaissances.[↩](#a6)


