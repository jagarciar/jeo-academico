---
sidebar_position: 6
id: funciones
title: Funciones
description: ¿Qué es una función? ¿Qué es un retorno? ¿Qué es un parámetro? ¿Qué es Unit?
tags:
  - Kotlin
  - Named Arguments
  - Parámetros
  - fun
  - Funciones
  - return 
  - Unit
---

# Funciones

Las funciones son **fragmentos de código reutilizables** que permiten organizar el código fuente de nuestra aplicación. En **Kotlin** se definen a través de la instructiva **fun**.

En el siguiente ejemplo vamos a crear la función **suma**.

```kotlin
fun suma(){}
```

## Parámetros 

Las funciones pueden tener o no (es opcional) un conjunto de **parámetros**. Los **parámetros** son **variables** que existen únicamente en la función. Al ser una **variable**, debe tener un nombre y un **tipo de dato**. Cada **parámetro** debe estar  separado por una coma. 

```kotlin
fun suma(numero1 : Int, numero2 : Int){}
```

En el anterior ejemplo, la función **suma** tiene dos parámetros **numero1** y **numero2**. Ambos parámetros son de tipo entero (**Int**). En dado caso quisieramos asignar un **valor por defecto** a nuestro parámetro podriamos incluirlo :

```kotlin
fun suma(numero1 : Int, numero2 : Int = 5){}
```

En el anterior ejemplo, la función **suma** tiene dos parámetros **numero1** y **numero2**. Ambos parámetros son de tipo entero (**Int**). En dado caso al invocar la función no se le envie un valor al parámetro **numero2**, el tomará el valor por defecto igual a 5. 

Hasta el momento nuestra función no ejecuta ninguna acción. Si el nombre de la función es **suma**, el objetivo debe ser sumar un conjunto de números, en este caso, sumar los valores de los parámetros **numero1** y **numero2**. 

```kotlin
fun suma(numero1 : Int, numero2 : Int = 5){
  var resultado : Int = numero1 + numero2;
}
```

En el anterior ejemplo, la función **suma** tiene dos parámetros **numero1** y **numero2**. Ambos parámetros son de tipo entero (**Int**). En dado caso al invocar la función no se le envie un valor al parámetro **numero2**, el tomará el valor por defecto igual a 5. Durante la ejecución de la función, se crea una variable **resultado** de tipo entero (**Int**). La variable **resultado** será igual a la suma de la variable **numero1** y **numero2**.

## Retorno

Las funciones pueden tener o no (es opcional) un retorno. El **retorno** es el resultado de la **ejecución** de la función. 

```kotlin
fun suma(numero1 : Int, numero2 : Int = 5) : Int{
  var resultado : Int = numero1 + numero2;
  return resultado;
}
```

En el anterior ejemplo, la función **suma** tiene dos parámetros **numero1** y **numero2**. Ambos parámetros son de tipo entero (**Int**). En dado caso al invocar la función no se le envie un valor al parámetro **numero2**, el tomará el valor por defecto igual a 5. Durante la ejecución de la función, se crea una variable **resultado** de tipo entero (**Int**). La variable **resultado** será igual a la suma de la variable **numero1** y **numero2**. La función **suma** retornará el valor de la variable **resultado**. 

:::tip
La función **suma** puede definirse sin la creación de la variable **resultado**. Es viable que retorne el resultado de la suma de los parámetros **numero1** y **numero2** en una línea de código. 

```kotlin
fun suma(numero1 : Int, numero2 : Int = 5){
  return numero1 + numero2;
}
```
:::

### Unit

**Unit** significa que la función no retorna ningún valor. **Unit** es equivalente a los tipos **nulos** de datos que se muestran en otros lenguajes.

```kotlin
fun validar(letra : Char = 'a') : Unit{
      when(letra){
        'a' -> println("La letra no ha cambiado")
        'b' -> println("La letra cambió a b")
        else -> println("La letra cambió")
      }
}
```

En el anterior ejemplo se creó la función **validar** que recibe como parámetro una variable nombrada letra de tipo carácter (**Char**). El parámetro letra tiene un valor por defecto igual a la letra 'a'. La función **validar** no retorna ningún valor. Por tal motivo, se define el tipo de retorno **Unit**. Con el valor del parámetro letra se valida a través de la instructiva **when** que debe imprimir el programa por consola. 

## Invocación

Como lo mencionamos al inicio, el objetivo de las funciones es reutilizar el código fuente. En este caso, es poder **invocar** varias veces la misma función sin necesidad de repetir el código. 

```kotlin
var resultado1 : Int = suma(1,2);
```

En el anterior ejemplo se creó una variable :  **resultado1**. La variable **resultado1** es igual al resultado de la ejecución de la función **suma** enviando como parámetros los valores 1 y 2 respectivamente. En este caso, el valor del parámetro **numero1** será igual a 1 mientras que el valor del parámetro **numero2** será igual a 2. Al ejecutar la función se crea la variable **resultado** la cuál es igual a la suma de ambos parámetros. Por tal motivo, el valor de la variable **resultado1** será 3. 

```kotlin
var resultado2 : Int = suma(4);
```

En el anterior ejemplo se creó una variable :  **resultado2**. La variable **resultado2** es igual al resultado de la ejecución de la función **suma** enviando como parámetro el valor 4 respectivamente. En este caso, el valor del parámetro **numero1** será igual a 4 mientras que el valor del parámetro **numero2** será igual a 5 (el que se definió por defecto). Al ejecutar la función se crea la variable **resultado** la cuál es igual a la suma de ambos parámetros. Por tal motivo, el valor de la variable **resultado2** será 9.
