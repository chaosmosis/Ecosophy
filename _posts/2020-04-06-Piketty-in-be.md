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
