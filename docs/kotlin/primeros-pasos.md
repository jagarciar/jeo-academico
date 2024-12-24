---
sidebar_position: 1
description: ¿Qué son las variables? ¿Qué son los tipos de datos? 
tags:
  - Kotlin
  - Variables
  - var
  - val
  - Mutable
  - Read-Only
  - Concat
  - Int
  - Float
  - Double
  - Char
  - String
  - Boolean
---

# Primeros pasos
  
## Variables {#variables}

Las **variables** en **Kotlin** nos permiten **almacenar** **datos** y son de tipo **read-only** (**val**) o de tipo **mutable** (**var**). Es decir, cuando se declara una variable de tipo **val**, el valor de esta variable no podrá cambiar en el tiempo. Por el contrario, si
se declara una variable de tipo **var**, el valor de esta variable podrá cambiar en el tiempo.  

```kotlin
var palabra = "hola"
var numero = 1
val palabra2 = "hola2"
val numero2 = 2
```

En el anterior ejemplo se crearon dos variables de tipo **var** (**palabra** y **numero**) y dos de tipo **val** (**palabra2** y **numero2**).

```kotlin
var palabra = "hola"
var numero = 1
val palabra2 = "hola2"
val numero2 = 2

numero = 3
palabra = "¿Cómo estás?
```

Por tal motivo, la **variable** **numero** y la **variable** **palabra** pueden ser modificadas. Sin embargo, las **variables** **palabra2** y **numero2** no pueden ser modificadas. 

## Tipos de datos {#tipos-datos}

Kotlin **infiere** sobre los **tipos de datos** de las **variables**. Por tal motivo, no es obligatorio adicionar el **tipo de dato** de la variable.

```kotlin
var numero1 : Int = 2
var numero2 : Float = 3.56
val numero3 : Double = 3.45
val bandera : Boolean = true
val caracter : Char = ','
val palabra : String = "Hola"
```

- Las variables de tipo **Int** al igual que las variables de tipo **Float** guardan **32 Bits**. Sin embargo, las variables de tipo **Double** guardan **64 Bits**. 
- Las variables de tipo **Boolean** solo pueden guardar dos posibles valores : **true** o **false**. 

## Arreglos

Un **arreglo** es una **estructura de datos** que contiene un **número fijo** de elementos del mismo tipo. 

```kotlin
var nombres = arrayOf("jeyson","andres","garcia")
nombres += "rodriguez"
nombres.joinToString()
println(nombres)
```

A través de la función **arrayOf()** podemos crear un arreglo y haciendo uso de la función **joinToString()** adicionamos un nuevo elemento al final del mismo. Si queremos crear un arreglo completamente vacío deberemos invocar la función **emptyArray()**

### Operaciones

#### contentEquals()

La función **contentEquals()** nos va permitir comparar dos arreglos, como por ejemplo:

```kotlin
var nombres = arrayOf("jeyson","andres","garcia")
var nombres2 = arrayOf("jeyson","andres","garcia")
println(nombres.contentEquals(nombres2))
```

Si la variable nombres es igual a la variables nombres2 retornará **true**, de lo contrario, retornara **false**