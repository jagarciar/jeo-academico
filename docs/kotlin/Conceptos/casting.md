---
sidebar_position: 9
id: casting
title: Casting
description: ¿Cómo validar el tipo de dato de una variable?
tags:
  - Kotlin
  - is
---

# Casting

En **Kotlin**, puedes realizar comprobaciones de tipo para comprobar el **tipo de dato** de un **objeto** en tiempo de ejecución. Las conversiones de tipo te permiten **convertir objetos** a un tipo diferente.

## Operador Is

Para realizar una verificación en tiempo de ejecución que identifique si un objeto se ajusta a un tipo determinado, utilice el operador **is** o su forma negada **!is**:

```kotlin
var nombre : String = "Jeyson Andrés García Rodríguez";
if(nombre is String){
    println("La variable nombre es String");
}
```

En el anterior ejemplo tenemos una validación del tipo de dato de la variable **nombre**. Para esto hace uso del operador **is**. 

```kotlin
var nombre : String = "Jeyson Andrés García Rodríguez";
when(nombre){
    is String -> println("El valor de la variable es String");
    !is Int -> println("El valor de la variable no es Int");
    else -> println("No se detectó el valor de la variable");
}
```

En el anterior ejemplo tenemos algunas validaciones del tipo de dato de la variable **nombre** haciendo uso de **when**. La primera validación es si el tipo de la variable **nombre** es **String**. La segunda validación es si el tipo de la variable **nombre** es diferente de **Int** y la tercera es la por defecto si no se cumplen las anteriores.

## Operador As

Para convertir explícitamente un objeto a un tipo no nulo, utilice el operador de conversión inseguro **as**:

```kotlin
var nombre : String = "Jeyson Andrés García Rodríguez";
var nombre2 = nombre as String;
```

En el anterior ejemplo tenemos dos variables : **nombre** y **nombre2**. El valor de la variable **nombre** es asignado a la variable **nombre2** convirtiendo el valor de la variable **nombre** como **String**. Supongamos que la variable **nombre** no fuese un **String** sino otro tipo de dato, la conversión lanzaría un error. Para evitar estos errores podemos usar el operador **as?**:

```kotlin
var nombre : String = "Jeyson Andrés García Rodríguez";
var nombre2 = nombre as? String;
```