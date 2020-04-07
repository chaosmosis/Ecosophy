---
layout: post
title: "L'absence, les surveillances électroniques, l'interruption de peine et le Virus : "
categories: stat
author: "John Nève"
meta: "marx"
---

Une email et quelques pièces jointes. Le problème de la définition des variables. 

## Notations pour les Prisons

Supposons qu'il existe un nombre déterminé de prisons (e.g $$ I in \R{+}_{0}$$) sur un terrtoire donné. Désignons par $i$, l'une des $I$ prisons de ce territoire et par $$ n_i $$, le nombre de détenus au sein de la prison $$i$$.

Chaque prison $$i$$ a une "capacité théorique", ci-après dénotée $$ \xi_i $$. Nommons le nombre total de détenus au sein du système carcéral belge par $$ N $$ et le capacité totale de détention du système carcérale par $$ \Xi $$. 

Enfin, désignons par $$g_i$$ le nombre de salarié travaillant au sein de la prison $$i$$ et par $$G$$ le nombre total de salarié oeuvrant à la reproduction des tâches journalières auquel est confronté le système carcérale fédéral.

En l'espèce, nous dirons donc qu'au sein des $$I$$ prisons fédérales du pays, il y a

1. $$ N = \sum_{I} n_{i} $$ détenus pour

2. $$ \Xi = \sum_{I} \xi_{i} $$ lits et 

3. $$ G = \sum_{I} g_{i} $$ intervenants salariés.


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

Les tableaux statistiques distribués par le ministère public témoigne de cette attachement aux différences et traduisent essentiellement via deux genres de détenus et trois modes d'incarcérations différents huit types de détenus. 

En effet, via les documents on comprend que 

1. Le détenu est soit de genre Masculin, soit de genre féminin. 
2. Le détenu est ou prévenu ou condamné. 
3. et enfin, le détenu est interné ou non. 

Ainsi, on comprend bien qu'il existe, selon la typologie du ministère public, au moins huit types de détenus différents au sein du système carcéral fédéral.


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
