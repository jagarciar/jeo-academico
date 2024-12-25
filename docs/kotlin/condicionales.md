---
sidebar_position: 3
id: condicionales
title: Condicionales
description: ¿Qué es el if/else? ¿Qué es el when?
tags:
  - Kotlin
  - if
  - else
  - else if
  - when
  - operadores
  - operador de comparación
  - operador de incremento
  - operador de decremento
---

# Condicionales

## if else

Kotlin es capaz de tomar decisiones en función de si un **fragmento de código** se evalúa como **verdadero o** como **falso**. Estos fragmentos de código se denominan **expresiones condicionales**. 

```kotlin
var numero1 : Int = 3

if(numero1 == 1){
  numero1 += 3
} else {
  numero1 -= 3
}
```

En el anterior ejemplo se hace uso de la instructiva **if**. En esta instructiva se
esta validando si el valor de la variable **numero1** es igual a 1 (haciendo uso del operador **==**). Si esta condición llega a ser verdadera, se incrementa el valor de la variable **numero1** en 3 (haciendo uso del operador **+=**). Si esta condición no es verdadera, el valor de la variable **numero1** se decrementa en 3 (haciendo uso del operador **-=**) bajo la instructiva **else**. 

:::tip

El siguiente fragmento de código :

```kotlin
var numero1 : Int = 3
numero1 += 3
```

es símil al siguiente :

```kotlin
var numero1 : Int = 3
numero1 = numero1 + 3
```
:::

En dado caso sea necesario, Kotlin permite adicionar varias condiciones a través de la instructiva **else if**. 

```kotlin
var numero1 : Int = 3

if(numero1 == 1){
  numero1 += 3
} else if(numero1 == 2) {
  numero1 -= 3
} else if(numero1 == 3){
  numero1 *= 2
} else {
  numero1 /= 2
}
```

En el anterior ejemplo se adicionaron tres condiciones a la inicial. La segunda condición valida si el valor de la variable **numero1** es igual a 2. Si lo es, se decrementa el valor de la variable **numero1** en 3. Si no lo es, se valida la tercera condición. La tercera condición compara el valor de la variable **numero1** con 3. Si cumple esta condición, se multiplica el valor de la variable **numero1** con 2. Si no lo es, se divide el valor de la variable **numero1** con 2. 

:::tip

El siguiente fragmento de código :

```kotlin
var numero1 : Int = 3
numero1 *= 2
```

es símil al siguiente :

```kotlin
var numero1 : Int = 3
numero1 = numero1 * 2
```
:::

### Operador ternario

En Kotlin podemos hacer uso del operador ternario. Este operador ternario reemplaza a la instructiva **if** **else** siempre que se pueda definir en una línea de código.

```kotlin
val numero1 : Int = 3
val numero2 : Int = 3

println( if (numero1 != numero2) "No son iguales" else "Son iguales")
```

En el anterior ejemplo sobre la función **println** imprime por consola **No son iguales** 
siempre que el valor de la variable **numero1** sea diferente del valor de la variable **numero2**. Si son iguales, la función **println** imprime **Son iguales**. 

:::tip

El siguiente fragmento de código :

```kotlin
var numero1 : Int = 3
numero1 -= 3
```

es símil al siguiente :

```kotlin
var numero1 : Int = 3
numero1 = numero1 - 3
```
:::

## when

En otros lenguajes de programación se conoce la instructiva **switch**. Esta instructiva es la misma **when** en **Kotlin**. Su objetivo es condicionar el valor de una variable con posibles resultados. 

```kotlin
var numero1 : Int = 3
when(numero1) {
  1 -> println("El valor de la variable es 1")
  2 -> println("El valor de la variable es 2")
  3 -> println("El valor de la variable es 3")
  else -> println("El valor de la variable es $numero1")
}
```

En el anterior ejemplo tenemos la variable **numero1**. A través de la instructiva **when** estamos condicionando su valor. Si el valor es 1, imprimira por consola **El valor de la variable es 1**. Si el valor es 2, imprimira por consola **El valor de la variable es 2**. Si el valor es 3, imprimira por consola **El valor de la variable es 3**. Si no es ninguno de los valores mencionados, imprimirá por consola **El valor de la variable es n** donde **n** es el valor de la variable **numero1**. 

```kotlin
var numero1 : Int = 3
var numero2 : Int = when {
  numero1 == 1 -> numero1 * 10
  numero1 == 2 -> numero1 / 10
  numero1 == 3 -> numero1 % 2
  else -> 0
}
```

En el anterior ejemplo tenemos dos variables : **numero1** y **numero2**. El valor de la variable **numero2** dependerá del resultado de la instructiva **when**. La instructiva **when** depende del valor de la variable **numero1**. Si el valor es 1, el valor de la variable **numero2** será la multiplicación entre el valor de la variable **numero1** y 10. Si el valor es 2, el valor de la variable **numero2** será la división entre el valor de la variable **numero1** y 10. Si el valor es 3, el valor de la variable **numero2** será el residuo entre el valor de la variable **numero1** y 2. Si no es ninguno de esos valores, el valor de la variable **numero2** será 0. 