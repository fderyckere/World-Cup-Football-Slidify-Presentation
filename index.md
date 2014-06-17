---
title       : World Cup 2014
subtitle    : Heights and Weights of Team's Players
author      : Filip Deryckere
job         : NA
framework   : io2012   # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---



## Objective and Scope

The world cup football has started recently in Brazil. Several national teams are competing for the world cup. Players of all size and weights are giving their best performance on the pitch.

I leave it up to the coaches and supporters to determine whether the height and weight of their team's keepers, defenders, midfielders and attackers determine the chances to beat the opponents or not. 

The application gives the supporter an overview of the heights and weights of their team compared to the total population of football players participating in the tournament.

---

## The Data


The data has been scraped with the XML package in R from the website [soccerway](http://int.soccerway.com/international/world/world-cup/2014-brazil/group-stage/r16351/?ICID=TN_02_03_01).
The example below shows how the data has been captured.

```r
library(XML)
url <- "http://int.soccerway.com/teams/rankings/fifa/"
fifaRanking <- readHTMLTable(url, which=1, stringsAsFactors=FALSE)
head(fifaRanking)
```

```
##   #        Team  Points  Change
## 1 1       Spain 1485.00       -
## 2 2     Germany 1300.00       -
## 3 3      Brazil 1242.00      +1
## 4 4    Portugal 1189.00      -1
## 5 5   Argentina 1175.00      +2
## 6 6 Switzerland 1149.00      +2
```

---

## The Application

The application has been built using Shiny in R.
You can find the application [here](https://filipderyckere.shinyapps.io/WorldCupFootball2014HeightsAndWeights/).

In this simple application, the height and weight of the team's players are compared to these of their adversaries. 

The results contain the following
* The grey dots in the graph represent all players in the competition. 
* The slope line indicates the linear regression between height and weight of the entire population of players. 
* The coloured dots represent the players of the national team of your choice. Goalkeepers, defenders, midfielders and attackers all have their own dot color.

---

## Some Sidenotes

Note: sorry for all of you who don't participate this time.
![World cup](./FIFA-World-Cup-2014.jpg)






