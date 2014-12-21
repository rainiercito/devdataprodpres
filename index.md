---
title: "Calculadora de Indice de Masa Corporal"
author: "Victor Rainier Cruz Perez"
highlighter: highlight.js
output: html_document
job: null
knit: slidify::knit2slides
mode: selfcontained
hitheme: tomorrow
subtitle: Developing Data Products Project
framework: io2012
widgets: mathjax
---

## ¿Qué es el Índice de Masa Corporal?

EL Índice de Masa Corporal es una medida para determinar la grasa del cuerpo con base en la estatura y peso de un individuo. La Organización Mundial de la Salud determina que con base en el Índice de Individual una persona puede saber si esta bajo de peso, tiene peso normal o sobrepeso.

Así mismo propone la siguiente clasificacion:
* Índice de Masa Corporal  <18.5       : Bajo de Peso
* Índice de Masa Corporal [18.5-24.9]  : Peso Normal
* Índice de Masa Corporal [25.0-29.9]  : Sobrepeso
* Índice de Masa Corporal  >=30        : Obeso

--- 

## ¿Cómo se calcula el Índice de Masa Corporal?
El Índice de Masa Corporal se calcula con base en la fórmula siguiente:

IMC = Peso(kg) / Altura(m)$^2$

Por ejemplo:


```r
peso = 75
altura = 1.80
IMC<- peso / altura^2
IMC
```

```
## [1] 23.14815
```


---

## Diagnóstico
Para determinar el estado de salud del individuo se interpreta el IMC con base en los intervalos definidos por la Organización Mundial de la Salud.

```r
fx_diagnostico<-function(peso,altura){
  indice<-peso/(altura^2)
  ifelse(indice<18.5,"bajo de peso",ifelse(indice<25,"peso normal",ifelse(indice<30,"sobre peso")))
}
```

Por ejemplo un individuo con un peso de 70 Kg cuya altura sea 1.60m su interpretación sería:


```r
fx_diagnostico(70,1.60)
```

```
## [1] "sobre peso"
```
---
## Conclusión

El IMC es fácil de calcular. Es un método no invasivo que relaciona de manera razonable el nivel de grasa en el cuerpo de un individuo con base en su peso y estatura. El IMC es una aproximación relativa a múltiples factores como actividad física, etnia y edad del individuo. El IMC es un índice referencial que debe ser complementado con estudios específicos a manera de obtener un valor más exacto si se requiere.
