---
sidebar_position: 2
id: data-class
title: Data classes
description: ¿Qué es una clase de datos? ¿Cuál es su diferencia con las clases?
tags:
  - Kotlin
  - Data class
---

# Data class

**Kotlin** tiene **clases de datos** que son particularmente útiles para **almacenar datos**. Las **clases de datos** tienen la misma funcionalidad que las **clases**, pero vienen automáticamente con **métodos** adicionales. Estos métodos le permiten **imprimir** fácilmente la **instancia** en una **salida legible**, **comparar instancias** de una **clase**, **copiar instancias** y mucho más. Como estos **métodos** están disponibles automáticamente, no tienes que dedicar tiempo a escribir el mismo código repetitivo para cada una de tus clases.

:::tip
La instancia de una clase es el símil de la definición de un objeto.
:::

Para definir una **clase** como una **clase de datos** debemos adicionar la palabra clave **data** como se muestra a continuación:

```kotlin
data class Estudiante(var nombre: String, 
                 var tipoIdentificacion: String, 
                 var numIdentificacion: String)
```

## Imprimir

Para **imprimir** una **cadena legible** de una **instancia** de una **clase**, puedes llamar explícitamente a la función **toString()**, o usar las funciones **print (println() e print())** que llaman automáticamente a **toString()**.

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
println(estudiante);
```

## Comparar

Para **comparar** dos **instancias** de una misma **clase** debes hacer uso del operador de comparación **==**

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
var estudiante2 : Estudiante = Estudiante("Bryan","CE","2");
println(if (estudiante == estudiante2) "Son iguales" else "Son diferentes")
```

## Copiar

Para crear una **copia exacta** de una **instancia** de una **clase** llame a la función **copy()** en la instancia como se muestra a continuación:

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
var estudiante2 : Estudiante = estudiante.copy()
```

Para crear una **copia** de una **instancia** de una **clase** y cambiar algunas **propiedades** llame a la función **copy()** en la **instancia** y agregue **valores de reemplazo** para las propiedades como **parámetros** de **función** como se muestra a continuación:

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
var estudiante2 : Estudiante = estudiante.copy(tipoIdentificacion = "CE")
```

:::tip
Crear una copia de una **instancia** es más seguro que modificar la **instancia original**, ya que cualquier modificación que se base en la **instancia original** no se ve afectado por la **copia** ni por lo que se haga con ella.
:::
