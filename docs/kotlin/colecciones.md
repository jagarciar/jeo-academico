---
sidebar_position: 3
id: colecciones
title: Colecciones
description: ¿Qué es una List? ¿Qué es un Set? ¿Qué es un Map?
tags:
  - Kotlin
  - List
  - count()
  - first()
  - last()
  - Set
  - in
  - containsKey()
  - Map
---

# Colecciones

Las colecciones son **estructuras de datos** que almacenan más de un **valor** de un mismo **tipo de dato**. 

## Array

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

## List

Las **listas** almacenan los **elementos** en el **orden** en que se agregan y permiten **elementos duplicados**.

```kotlin
var lista1 = listOf("jeyson","andres","garcia")
println(lista1)
```

A través de **listOf** podemos crear una lista de tipo **Read-Only**.

```kotlin
var lista1 : MutableList<String> = mutableListOf("jeyson","andres","garcia")
println(lista1)
```

A través de **mutableListOf** podemos crear una lista de tipo **Mutable**

```kotlin
var lista1 : MutableList<String> = mutableListOf("jeyson","andres","garcia")
var lista2 : List<String> = lista1
println(lista1)
```

A través del **casting** podemos convertir una lista de tipo **Mutable** a una lista de tipo **Read-Only**. En el anterior ejemplo, la lista **Mutable** es lista1, mientras que la lista2 es la lista **Read-Only**

### Operaciones

#### first()

#### last()

Kotlin le permite a un desarrollador obtener el **valor de un elemento** de una lista a través del **operador de acceso indexado []** y de las funciones : **first()** y **last()**. El **operador de acceso indexado []** espera un número entero que debe ser menor a la cantidad total de elementos de la lista. La función **first()** retorna el primer elemento, mientras que la función **last()** retorna el último elemento**. 

```kotlin
var lista1 : MutableList<String> = mutableListOf("jeyson","andres","garcia")
println(lista1[1])
println(lista1.first())
println(lista1.last())
```

En el ejemplo anterior se imprime por consola : andres, jeyson y garcia en ese orden respectivamente. 

#### count()

```kotlin
var lista1 : MutableList<String> = mutableListOf("jeyson","andres","garcia")
println(lista1.count())
```

En el ejemplo anterior se imprime por consola : 3. Esto dado que a través de la función **count()** se obtiene el total de elementos de la lista. 

#### add()

#### remove()

A través de las funciones **add()** y **remove()** podemos adicionar y eliminar elementos a una lista previamente creada respectivamente. 

```kotlin
var lista1 : MutableList<String> = mutableListOf("jeyson","andres","garcia")
lista1.add("rodriguez")
println(lista1)
lista1.remove("jeyson")
println(lista1)
```

Por tal motivo en una primera instancia imprime por consola jeyson andres garcia rodriguez, mientras que en una segunda instancia imprime andres garcia rodriguez. 

## Set

Mientras que las **List** están **ordenadas** y permiten elementos duplicados, los **Set** **no están ordenados** y solo almacenan **elementos únicos**.

```kotlin
var set1 = setOf("jeyson","andres","garcia")
println(set1)
```

A través de **setOf** podemos crear un Set de tipo **Read-Only**.

```kotlin
var set1 : MutableSet<String> = mutableSetOf("jeyson","andres","garcia")
println(set1)
```

A través de **mutableSetOf** podemos crear un Set de tipo **Mutable**

```kotlin
var set1 : MutableSet<String> = mutableSetOf("jeyson","andres","garcia")
var set2 : List<String> = set1
println(set2)
```

A través del **casting** podemos convertir un Set de tipo **Mutable** a un Set de tipo **Read-Only**. En el anterior ejemplo, el Set **Mutable** es set1, mientras que set2 es el Set **Read-Only**

### Operaciones

#### add()

#### remove()

A través de las funciones **add()** y **remove()** podemos adicionar y eliminar elementos a un Set previamente creado respectivamente. 

```kotlin
var set1 : MutableSet<String> = mutableSetOf("jeyson","andres","garcia")
set1.add("rodriguez")
println(set1)
set1.remove("jeyson")
println(set1)
```

Por tal motivo en una primera instancia imprime por consola jeyson andres garcia rodriguez, mientras que en una segunda instancia imprime andres garcia rodriguez. 

#### count()

```kotlin
var set1 : MutableSet<String> = mutableSetOf("jeyson","andres","garcia")
println(set1.count())
```

En el ejemplo anterior se imprime por consola : 3. Esto dado que a través de la función **count()** se obtiene el total de elementos del Set. 

#### in 

```kotlin
var set1 : MutableSet<String> = mutableSetOf("jeyson","andres","garcia")
println("andres" in set1)
```

A través del operador **in** podemos validar si existe un elemento dentro de un **Set**. Si existe retorna **true**. Si no existe, retorna **false**.

## Map

Los **mapas** almacenan elementos como pares **clave-valor**. Para acceder al **valor**, debe hacer referencia a la **clave**.

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map1)
```

A través de **mapOf** podemos crear un Map de tipo **Read-Only**.

```kotlin
var map1 : MutableMap<String, Int> = mutableMapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map1)
```

A través de **mutableSetOf** podemos crear un Set de tipo **Mutable**

```kotlin
var map1 : MutableMap<String, Int> = mutableSetOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
var map2 : Map<String, Int> = map1
println(set2)
```

A través del **casting** podemos convertir un Map de tipo **Mutable** a un Map de tipo **Read-Only**. En el anterior ejemplo, el Map **Mutable** es map1, mientras que el map2 es el Map **Read-Only**

### Operaciones

Si queremos obtener el valor de una clave de un **Map** debemos hacer uso del operador de acceso indexado como se muestra a continuación:

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map1["andres"])
```

En el ejemplo anterior imprimirá por consola : 2. 

Si queremos imprimir todas las claves podemos ejecutar el siguiente algoritmo:

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map1.keys)
```

Mientras si queremos imprimir todos los valores podemos ejecutar el siguiente algoritmo:

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map1.values)
```

#### count()

```kotlin
var map : MutableMap<String, Int> = mutableSetOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println(map.count())
```

En el ejemplo anterior se imprime por consola : 3. Esto dado que a través de la función **count()** se obtiene el total de elementos del Map. 

#### add()

#### remove()

Si queremos crear una nueva clave-valor deberemos asignar con el mismo operador de acceso indexado :

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
map1["rodriguez"] = 4
```

Pero si queremos eliminar una clave junto a su valor debemos hacer uso de la función **remove()**:

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
map1.remove("garcia")
```

#### containsKey()

A través de la función **containsKey()** podemos consultar si un Map tiene una clave creada. Si la tiene, retorna **true** de lo contrario retorna **false**. 

```kotlin
var map1 = mapOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
map1.containsKey("garcia")
```

En el ejemplo anterior retornaria :  **true**.

#### in 

```kotlin
var map1 : MutableMap<String, Int> = mutableSetOf("jeyson" to 1,"andres" to 2,"garcia" to 3)
println("andres" in map1.keys)
```

A través del operador **in** podemos validar si existe un elemento dentro de un **Map**. Si existe retorna **true**. Si no existe, retorna **false**. Podemos hacer uso de **map1**, **map1.keys** o **map1.values**.
