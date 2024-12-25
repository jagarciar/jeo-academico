---
sidebar_position: 4
id: funciones
title: Funciones
description: ¿Cómo debo ejecutar Println? ¿Cómo debo ejecutar Readln()?
tags:
  - Kotlin
  - Readln
  - Println
---

# Funciones

## Println {#println}

La función **println** permite imprimir por consola el valor de una o más variables. 

```kotlin
var palabra = "hola"
var numero = 1
println(numero)
println("Soy $numero")
println("Soy ${numero + 1}")
```

En el anterior ejemplo se imprime por consola tres valores: el primer valor corresponde al valor de la variable numero, es decir, 1. En el segundo valor imprime la **concatenación** de Soy y el valor de la variable numero, es decir, **Soy 1**. Finalmente en el tercer valor imprime la **concatenación** de Soy y el valor de la suma de la variable numero con 1, es decir, **Soy 2**. 

## Readln {#readln}

La función **readln** permite leer un valor desde una entrada estándar. 

```kotlin
var palabra = readln()
println(palabra)
```

En el anterior ejemplo se le solicita a un usuario que digite el valor de la variable palabra para luego imprimirla por pantalla o consola. 