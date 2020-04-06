---
layout: post
title: "Mr. Piketty en Belgique"
categories: stat
author: "John Mévergnies"
meta: "marx"
---

Lorsque l'on s'engage dans un travail de "thèse", on est souvent étonné des chemins par lesquelles nous passons.  En Belgique, le statut professionnel des assistant-chercheurs comme moi est relativement bien établit et les avantages qu'il procure ne sont pas négligeable. Si on excepte la grande incertitude quant la capacité pour les doctorants et les doctorats de trouver un emploie ensuite. 

Devant cette incertitude présenté en long et en large, ce travail de thèse, se présente ici comme le choix délibéré d'une recherche inscrite dans les temps politiques, climatiques et humains contemporains. Ceci dit, cette thèses 'inscrit dans un mouvement qui s"i'écrit dans la durée et dont la fin est par contre certaine: la résistance à aux dominations, sous quelques formes qu'elles soient. 

Si nous nous intéressons un instant aux flux et stocks financiers d'une état-nation comme le Royaume de Belgique, le site d'Eurostat est une mine d'or d'information, en ce que l'europe encadre l'action des états-nations dans la collecte des données. <sup id="a1">[1](#f1)</sup>

On peut retrouver plusieurs bases de données constituées à partir du règlement européen *SEC2010*. Elles "découpent"  en deux grandes opérations l'ensembles des activités économiques : il y a les opérations financières et les opérations non financières du point de vue du comptable européen. 

Attardons-nous un instant sur les "Comptes de patrimoine financier", dont l'acronyme n'est autre que *nasa_10_f_bs*. Il se présente selon deux volets  : les avoirs et les engagements. 

Comme le veux la coutume on interprète le premier de ces volets comme l'ensemble des opération financière qui constate un *dominium* dans le chef de l'acteur considéré sur quelque chose, concernant le deuxième volet, il nous informe sur la manière dont ce droit réel, démembré ou non, a été acquit.

On y retrouve un ensemble de  catégorie qui sont chacune subdivisée en plusieurs parties. L'ensemble représente le "Total financier des avoirs/des engagements". 
On retourne une catégorie historique dans la première subdivision  : l'or monétaire et les droits de tirage spéciaux, qui ne sont autre que les avoirs en monnaies du fond monétaire internationlale.<sup id="a2">[2](#f2)</sup>

Deux Subdivisions existent donc. Vient ensuite l'ensemble des encaisse monétaires et des dépôts. Ces dépôts peuvent être transférable ou non. On dénombre jusqu'à 9 subdivision de la catégorie é Monnaies et dépôts".Vient ensuite la catégorie non moins importante des possession des unité considérés  des Titres de Créances. Viennent ensuite les Crédits(F4). Les actions (F5) et "Droits sur les provisions techniques d'assurance, sur les fonds de pension et sur les réserves de garanties standard" (F6), dans la septième des grosse catégories, on dénombre les "Produits financiers dérivés et options sur titres des salariés", et enfin, les "autres comptes à recevoir".  lorsque l'on s'intéresse à l'évolution d'un tel patrimoine au cours d'une année écoulée, on parlera de la "Valeur nette financière".


On retrouve sur le site d'eurostat un ratio interessant. 

> "*Le rapport entre la valeur financière nette et le revenu des ménages combine des données de comptabilité financière et non financière. Il correspond au rapport entre la valeur nette des actifs financiers des ménages, c’est-à-dire tous les actifs financiers diminués de tout le passif financier, enregistrée à la fin de l’année civile, et le revenu disponible brut accumulé par ces ménages au cours de l’année considérée. Il représente donc l’accumulation d’actifs financiers, passif déduit, des ménages par rapport à leur revenu annuel. Toutefois, ce rapport ne tient pas compte des actifs non financiers, tels que le logement.*"

Etant entenduque le degrée de raffinement atteint dans la collecte de ces données est récent. Nous nous attarderons rapidement sur quelques un des faits principaux liés aux revenus des ménages et des association sans but lucratif à leurs services. 

## Une question de recherche 

```{r}
install.packages('eurostat')
library(eurostat)
library(knitr)
kable(head(toc))
library(eurostat)
library(rvest)
library(tidyr)
library(dplyr)
check_access_to_data()

aa<-subset(a,  finpos == "ASS" )
be<-subset(aa,  geo == "BE" )
a <- get_eurostat("nasa_10_f_bs", time_format = "num", type = "label", lang = "fr")
```

> ce scénario ressort également globalement des projections macroéconomiques de juin 2015 établies par les services de l eurosystème pour la zone euro qui tablent sur une hausse annuelle de l ipch de 0 3 en 2015

Christine Lagarde en 2019 emboîte le pas quasi parfaitement:

> cette évaluation ressort également globalement des projections macroéconomiques de décembre 2019 établies par les services de l eurosystème pour la zone euro qui tablent sur une hausse annuelle de l ipch de 1 2 en 2019 1

## un virus

<b id="f1">1</b> On notera notamment qu'en Belgique, l'institut des comptes nationaux travaille désormais mais dans la main avec la Banque Nationale de Belgique à cet égard [↩](#a1)
<b id="f2">2</b> C'est dans cette catégorie que les afficionados du Bitcoin de la première heure inscrire leurs dom minium sur des Bitcoin. 
 [↩](#a2)
