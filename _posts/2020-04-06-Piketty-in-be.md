---
layout: post
title: "Mr. Piketty en Belgique"
categories: stat
author: "John Mévergnies"
meta: "marx"
---

Lorsque l'on s'engage dans un travail de "thèse", on est souvent étonné des chemins par lesquelles nous passons.  En Belgique, le statut professionnel des assistant-chercheurs comme moi est relativement bien établit et les avantages qu'il procure ne sont pas négligeable. Si on excepte la grande incertitude quant la capacité pour les doctorants et les doctorats de trouver un emploie ensuite. 

Devant cette incertitude présenté en long et en large, ce travail de thèse, se présente ici comme le choix délibéré d'une recherche inscrite dans les temps politiques, climatiques et humains contemporains. Ceci dit, cette thèses 'inscrit dans un mouvement qui s"i'écrit dans la durée et dont la fin est par contre certaine: la résistance à aux dominations, sous quelques formes qu'elles soient. 

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

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit.

### qui voyageait

Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum.

Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc.

### de chaines d'approvisionnement

Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

> les risques entourant les perspectives de croissance dans la zone euro restent orientés à la baisse et traduisent en particulier les incertitudes accrues liées à l évolution de l économie mondiale ainsi que l accentuation des risques géopolitiques 


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Mario Draghi, Juillet 2018 :

> en résumé un recoupement des résultats de l analyse économique avec les signaux provenant de l analyse monétaire confirme qu un degré élevé de soutien monétaire demeure nécessaire pour assurer la poursuite de la convergence durable de l inflation vers des niveaux inférieurs à mais proches de 2 à moyen terme


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Christine Lagarde, Janvier 2020 :


> en résumé un recoupement des résultats de l analyse économique avec les signaux provenant de l analyse monétaire confirme qu un degré élevé de soutien monétaire demeure nécessaire pour assurer la poursuite de la convergence durable de l inflation vers des niveaux inférieurs à mais proches de 2 à moyen terme


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Christine Lagarde, Décembre  2019 :

> en résumé un recoupement des résultats de l analyse économique avec les signaux provenant de l analyse monétaire confirme q'un degré élevé de soutien monétaire demeure nécessaire à la poursuite de la convergence durable de l inflation vers des niveaux inférieurs à mais proches de 2 à moyen terme

### Le crédit à tout prix

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Mario Draghi,  Janvier  2019, dec, octobre, septembre, juillet, avril, mars, janvier, 2018

> les effets des mesures de politique monétaire en place depuis juin 2014 continuent de soutenir fortement les conditions d emprunt des entreprises et des ménages l accès au financement en particulier pour les petites et moyennes entreprises et les flux de crédits dans la zone euro

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. La varation de de 2017 de Mario Draghi ? Décembre, 2017

> les effets des mesures de politique monétaire en place depuis juin 2014 continuent d améliorer sensiblement les conditions d emprunt des entreprises et des ménages l accès au financement en particulier pour les petites et moyennes entreprises et les flux de crédits dans la zone euro

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Mario Draghi, Mars, 2019

> les effets de nos mesures de politique monétaire sur l économie réelle soutiennent la demande intérieure et facilitent le désendettement l amélioration de la rentabilité des entreprises et les conditions de financement très favorables continuent de favoriser un rebond de l investissement


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Mario Draghi, Octobre, 2016

> les effets de nos mesures de politique monétaire confortent la demande intérieure et ont facilité le processus de désendettement le regain de l investissement continue de bénéficier des conditions de financement très favorables et des améliorations de la rentabilité des entreprises


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Christine Largard, Mars, 2019


> face aux effets négatifs liés aux incertitudes économiques et politiques au niveau mondial l économie de la zone euro a continué de résister soutenue par nos vastes mesures de politique monétaire qui garantissent des conditions de financement très favorables pour les entreprises et les ménages

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. 

Mais dans le courant de l'année 2019, alors que dont on s'incline devant les succès de la politique monétaire menée depuis 2014 on rappelle néanmoins que pour les "effets bénéfiques" se face réellement jour, il faut aussi des réformes :

> afin que les effets bénéfiques de nos mesures de politique monétaire puissent se faire sentir pleinement d autres pans de la politique économique doivent apporter une contribution plus décisive au rehaussement du potentiel de croissance à plus long terme et à la réduction des vulnérabilités


In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

#### On continue à travailler : "whatever it cost" 

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.
Christien lagarde, en Janvier et Mars 2020, et en décembre 2019 

> nous entendons poursuivre les réinvestissements en totalité des remboursements au titre du principal des titres arrivant à échéance acquis dans le cadre de l app pendant une période prolongée après la date à laquelle nous commencerons à relever les taux d intérêt directeurs de la bce 


In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. ELle reprenait le flambeaux d'un Mario qui de Juin 2018 à Octobre 2018 a martelé :

> ce soutien monétaire continu est apporté par les achats nets supplémentaires d actifs décidés lors de notre réunion de politique monétaire d octobre par le volume considérable de titres acquis et les réinvestissements à venir ainsi que par nos indications sur la trajectoire future des taux d intérêt directeurs forward guidance



#### nourrissant les rêves les plus doux 

... you can ![get the PDF](/assets/john.jpg) directly.
In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

### Ne paniquons pas !

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

- First item, yo
- Second item, dawg
- Third item, what what?!
- Fourth item, fo sheezy my neezy

### Nous n'avons pas le temps

In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris.

1. First item, yo
2. Second item, dawg
3. Third item, what what?!
4. Fourth item, fo sheezy my neezy



## Il n'y pas de fatalité

Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc.

### Tables

Title 1               | Title 2               | Title 3               | Title 4
--------------------- | --------------------- | --------------------- | ---------------------
lorem                 | lorem ipsum           | lorem ipsum dolor     | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit


Title 1 | Title 2 | Title 3 | Title 4
--- | --- | --- | ---
lorem | lorem ipsum | lorem ipsum dolor | lorem ipsum dolor sit
lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur | lorem ipsum dolor sit amet | lorem ipsum dolor sit
lorem ipsum dolor | lorem ipsum | lorem | lorem ipsum
lorem ipsum dolor | lorem ipsum dolor sit | lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur
