---
sidebar_position: 5
id: ciclos
title: Ciclos
description: ¿Qué es un ciclo? ¿Qué es un bucle? ¿Cómo ejecutar la instructiva for?
tags:
  - Kotlin
  - for
  - while
  - do..while
  - Ciclos
  - Bucles
---

# Ciclos

Los **ciclos** o **bucles** (también denominados **estructuras de control iterativas** o **repetitivas**) son sentencias que se utilizan para **ejecutar** una o varias **instrucciones** de forma **repetitiva** cuando sea necesario.

Estas estructuras están controladas por **variables** o **condiciones**. De esa manera es posible tener un control de la **cantidad de repeticiones** y así evitar la aparición de **bucles infinitos**.

## For

El ciclo **for** itera a través de una **variable** una **colección** de elementos. 

En el siguiente ejemplo se ilustra como a través de la variable **numero** se recorre un rango de números de 1 al 10. 

```kotlin
for(numero : Int in 1..10){
    println(numero)
}
```

En el siguiente ejemplo se ilustra como a través de la variable **numero** se recorre la lista creada previamente y bajo el nombre **lista**.

```kotlin
var lista = listOf(1,2,3,4,5)
for(numero : Int in lista){
    println(numero)
}
```

## While

El ciclo **while** valida una condición antes de ejecutar el contenido que debe ser iterado. 

En el siguiente ejemplo tenemos la variable **x** la cuál es inicializada con el valor de 10. En la instructiva **while** validamos que el valor de la variable **x** sea mayor a 0. Si esta condición se cumple, ingresa al contenido del ciclo **while** y ejecuta el decremento del valor de la variable **x** en 1. 

```kotlin
var x : Int = 10
while(x > 0){
    x--
}
```

:::tip

El siguiente fragmento de código :

```kotlin
var numero1 : Int = 3
numero1--
```

es símil al siguiente :

```kotlin
var numero1 : Int = 3
numero1 = numero1 - 1
```
:::

## Do..While

A comparación del ciclo **while**, el ciclo **do..while** ejecuta por lo menos una vez el contenido y después valida la condición. 

En el siguiente ejemplo tenemos la variable **x** la cuál es inicializada con el valor de 5. En la instructiva **do..while** sumamos al valor de la variable **x** el valor de 1. Después de ejecutar por primera vez el incremento, se valida si la condición de que el valor de la variable **x** sea menor o igual que 5 es verdadera. Si lo es, vuelve a ejecutar el incremento de la variable **x**. Si no lo es, finaliza. 

```kotlin
var x : Int = 1
do{
    x++
}while(x <= 5)
```