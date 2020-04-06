---
layout: post
title: "Mr. Piketty en Belgique"
categories: stat
author: "John Mévergnies"
meta: "marx"
---

Si nous nous intéressons un instant aux flux et stocks financiers d'un état-nation comme le Royaume de Belgique, le site d'Eurostat est une mine d'or d'information.  

Au sein de l'eurosystème, la commission européenne est résponsable  de la coordination des états-nations dans la collecte des données. <sup id="a1">[1](#f1)</sup>

On peut retrouver plusieurs bases de données constituées à partir du règlement européen *SEC2010*. 

Suivant à cet égarde les "règles internationales", ce réglèment décompose en deux grandes opérations l'ensemble des activités économiques : il y a les opérations financières et les opérations non financières.

Attardons-nous un instant sur les "Comptes de Patrimoine Financier", dont l'acronyme n'est autre que *nasa_10_f_bs*. Il se présente selon deux volets  : les avoirs et les engagements. 

Comme le veux la coutume on interprète le premier de ces deux volets comme l'ensemble des opérations financières qui constatent un *dominium* dans le chef de l'acteur considéré. Concernant le deuxième volet, il nous informe sur la manière dont ce droit réel, démembré ou non, a été acquit.

On y retrouve un ensemble de  catégorie qui sont chacune subdivisée en plusieurs parties. L'ensemble représente le "Total financier des avoirs/des engagements". 
On retourne une catégorie historique dans la première subdivision  : l'or monétaire et les droits de tirage spéciaux, qui ne sont autre que les avoirs en monnaies du fond monétaire internationlale.<sup id="a2">[2](#f2)</sup>

Deux Subdivisions existent donc. Vient ensuite l'ensemble des encaisse monétaires et des dépôts. Ces dépôts peuvent être transférable ou non. On dénombre jusqu'à 9 subdivision de la catégorie é Monnaies et dépôts".Vient ensuite la catégorie non moins importante des possession des unité considérés  des Titres de Créances. Viennent ensuite les Crédits(F4). Les actions (F5) et "Droits sur les provisions techniques d'assurance, sur les fonds de pension et sur les réserves de garanties standard" (F6), dans la septième des grosse catégories, on dénombre les "Produits financiers dérivés et options sur titres des salariés", et enfin, les "autres comptes à recevoir".  lorsque l'on s'intéresse à l'évolution d'un tel patrimoine au cours d'une année écoulée, on parlera de la "Valeur nette financière".


On retrouve sur le site d'eurostat un ratio interessant. 

> "*Le rapport entre la valeur financière nette et le revenu des ménages combine des données de comptabilité financière et non financière. Il correspond au rapport entre la valeur nette des actifs financiers des ménages, c’est-à-dire tous les actifs financiers diminués de tout le passif financier, enregistrée à la fin de l’année civile, et le revenu disponible brut accumulé par ces ménages au cours de l’année considérée. Il représente donc l’accumulation d’actifs financiers, passif déduit, des ménages par rapport à leur revenu annuel. Toutefois, ce rapport ne tient pas compte des actifs non financiers, tels que le logement.*"

Etant entenduque le degrée de raffinement atteint dans la collecte de ces données est récent. Nous nous attarderons rapidement sur quelques un des faits principaux liés aux revenus des ménages et des association sans but lucratif à leurs services. 

## Une question de recherche 

```{r}
library(eurostat)
library(knitr)
library(eurostat)
library(rvest)
library(tidyr)
library(dplyr)

a <- get_eurostat("nasa_10_f_bs", time_format = "num", type = "label", lang = "fr")

aa<-subset(a,  finpos == "ASS" )
be<-subset(aa,  geo == "BE" )
```

###Chercher les données sur le revenu disponible


```{r}
b <- get_eurostat("nasa_10_nf_tr", time_format = "num", type = "label", lang = "fr")
```
#### "Households; non-profit institutions serving households"


```{r}
data_mn_isbl_be<-subset(b , geo == "Belgium")
data_mn_isbl_be<-subset(data_mn_isbl_be, direct == "Paid" )
data_mn_isbl_be<-subset(data_mn_isbl_be, sector ==  "Households; non-profit institutions serving households") 
data_mn_isbl_be<-subset(data_mn_isbl_be, unit ==  "Current prices, million euro") 
### regardons un instant le revenu disponible de ce secteur, bru
#
rd_isbl_mn_be<-subset(data_mn_isbl_be, na_item  == "Disposable income, gross" )     
rd_isbl_mn_be<-spread(rd_isbl_mn_be,na_item,values)  

rd_mnisbl_ts = ts(rd_isbl_mn_be[,6],start=c(1995,1))

ts.plot(ts(rd_isbl_mn_be[,6],start=c(1995,1)))
ts.plot(rd_mnisbl_ts[,6])
```
Evidement -, le revenu disponible ne nous intéresse que peu en soi, c'est dans son rapport avec d'autres agrégats qu'il commence à nous fournir des détails intéressants. 

Remarquons notamment que le revenu disponible des ménages peut être soit épargné soit consommé dans un usage finale. 

Depuis cette distinction fondamentale, outillé également de la notion d'investissement, on peut déterminer un autre indicateur très important afin de comprendre le cadre de ce cours : la notion de capacité de financement ou de besoin d'un secteur institutionnel, et par homothétie d'une économie nationale donnée.  

En effet, la différence de l'investissement brut avec l'épargne va refléter, pour le comptable, a posteriori, au regard des opérations non financières qu'elle a engendré, une série d'opérations financières, qui  sont en réalité la simple la contrepartie des actes pris lors des décisions d'investissement de ces acteurs. 

En effet, prenons le cas de notre économie précédente. 

Imaginons que la fabrique de papier décide d'investir dans des produits informatiques produits par des codeurs et codeuses organisées à l'instar de notre coopérative à finalité sociale mais résident principalement en Chine. 

Plusieurs opération vont avoir lieu. Considérons la première, l'opération sur le service. En rédigeant son contrat d'importation de service, la fabrique de papier va signaler à ses co-contractants le termes et les menus détails du contrat dont elle souhaite voir la réalisation. 

Pratiquement, les codeurs et les codeuses devront offrir le service en temps t. comme se sont des résidents d'une autre économie, ce qu'opère notre entreprise n'est rien d'autre qu'un contrat à l'importation visant à augmentation son capital fixe. Autrement, elle va reporter aux autorités compétentes qu'elle possèdent désormais un nouveau capital, et d'autre part qu'elle a transférer une somme d'argent x à des agents économiques non nationaux. 

Autrement son patrimoine financier va être affecté tant via l'achat de cet actif non financier qu'elle possède désormais et qu'elle peut inscrire, qu'elle doit inscrire à l'actif de son bilan, mais d'autres part, en fonction de la manière dont elle s'est procurer son bien, à son passif, elle va reporté aux autorité compétentes, si elles a fait varié ses dettes à long ou cours termes ou si elle elle 

### le rapport de Piketty ou le total des actif sur le revenu disponible en Belgique

Allons chercher le compte du patrimoine financier de la Belgique. Nous choisirons le coompte consolidé du patrimoine financier belge de l'ensemble de l'économie, autrement dit, le compte du partimoine où chaque secteur est pris comme un tout qui consitue une économie nation. Les dettes entre les agents économiques d'un même secteur et partant d'un même pays, ne sont pas apphréhendable quantitativement.

#### Le total des actifs

```{r}
total<-subset(a, geo == "Belgium")
total<-subset(total, co_nco == "Consolidated")
total<-subset(total, finpos == "Assets")
total<-subset(total, sector == "Total economy")
```

Dans ce compte, nous selectionnons la "somme total des actifs financiers" détenus par les secteurs isnitutionnels opérant principalement en belgique.

```{r}
total_as<-subset(total, na_item == "Total financial assets/liabilities")
total_as<-subset(total_as, unit == "Million euro")
total_as<-spread(total_as,na_item,values)
total_as_ts= ts(total_as[,7], start=c(1995,1))
ts.plot(total_as_ts)
```
<div style="text-align: center"><img src="{{ site.baseurl }}/assets/totalassetbe.jpg" alt="Asset"></div>

#### Les dettes des secteurs institutionnels en Belgique


```{r}
dette<-subset(a, geo == "Belgium")

dette<-subset(dette, co_nco == "Consolidated")
dette<-subset(dette, finpos == "Liabilities")
dette_mn<-subset(dette, sector == "Total economy")
dette_mn<-subset(dette_mn, na_item == "Debt securities")
dette_mn<-subset(dette_mn, unit == "Million euro")
dette_mn<-spread(dette_mn,na_item,values)
dette_mn_ts= ts(dette_mn[,7], start=c(1995,1))
ts.plot(dette_mn_ts)
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/totaldebtsecuritiesbe.jpg" alt="Dette"></div>
#### Le revenu disponible au prix courants en Belgique


```{r}
data2<-subset(b , geo == "Belgium")
data2<-subset(data2, direct == "Paid" )
data2<-subset(data2, sector == "Total economy")
data2<-subset(data2, unit == "Current prices, million euro")
RD<-subset(data2, na_item  == "Disposable income, gross" )     
RD<-spread(RD,na_item,values)
RD_ts= ts(RD[,6], start=c(1995,1))
ts.plot(RD_ts)
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/revenudispobru.jpg" alt="Revenu"></div>


#### Le Ratio de Piketty en Belgique 
#### l'évolution du capital privé 

```{r}
net_be=total_as_ts - dette_mn_ts
ratio_be= (net_be/RD_ts)
ts.plot(ratio_be)
```

<div style="text-align: center"><img src="{{ site.baseurl }}/assets/ratio_be.jpg" alt="Ratio"></div>


<b id="f1">1</b> On notera notamment qu'en Belgique, l'institut des comptes nationaux travaille désormais mais dans la main avec la Banque Nationale de Belgique à cet égard [↩](#a1)

<b id="f2">2</b> C'est dans cette catégorie que les afficionados du Bitcoin de la première heure inscrire leurs dom minium sur des Bitcoin. 
 [↩](#a2)
