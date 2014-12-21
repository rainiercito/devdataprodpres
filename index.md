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

## �Qu� es el �ndice de Masa Corporal?

EL �ndice de Masa Corporal es una medida para determinar la grasa del cuerpo con base en la estatura y peso de un individuo. La Organizaci�n Mundial de la Salud determina que con base en el �ndice de Individual una persona puede saber si esta bajo de peso, tiene peso normal o sobrepeso.

As� mismo propone la siguiente clasificacion:
* �ndice de Masa Corporal  <18.5       : Bajo de Peso
* �ndice de Masa Corporal [18.5-24.9]  : Peso Normal
* �ndice de Masa Corporal [25.0-29.9]  : Sobrepeso
* �ndice de Masa Corporal  >=30        : Obeso

--- 

## �C�mo se calcula el �ndice de Masa Corporal?
El �ndice de Masa Corporal se calcula con base en la f�rmula siguiente:

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

## Diagn�stico
Para determinar el estado de salud del individuo se interpreta el IMC con base en los intervalos definidos por la Organizaci�n Mundial de la Salud.

```r
fx_diagnostico<-function(peso,altura){
  indice<-peso/(altura^2)
  ifelse(indice<18.5,"bajo de peso",ifelse(indice<25,"peso normal",ifelse(indice<30,"sobre peso")))
}
```

Por ejemplo un individuo con un peso de 70 Kg cuya altura sea 1.60m su interpretaci�n ser�a:


```r
fx_diagnostico(70,1.60)
```

```
## [1] "sobre peso"
```
---
## Conclusi�n

El IMC es f�cil de calcular. Es un m�todo no invasivo que relaciona de manera razonable el nivel de grasa en el cuerpo de un individuo con base en su peso y estatura. El IMC es una aproximaci�n relativa a m�ltiples factores como actividad f�sica, etnia y edad del individuo. El IMC es un �ndice referencial que debe ser complementado con estudios espec�ficos a manera de obtener un valor m�s exacto si se requiere.
