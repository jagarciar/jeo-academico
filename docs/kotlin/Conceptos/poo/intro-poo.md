---
sidebar_position: 1
id: intro-poo
title: Introducción
description: ¿Qué es una clase? ¿Qué es POO? ¿Qué es un objeto?
tags:
  - Kotlin
  - Class
  - Propiedades
  - Métodos
---

# Programación orientada a objetos

**Kotlin** permite la **P.O.O** (Programación orientada a objetos). La **Programación Orientada a Objetos** se define como un paradigma de la programación, una manera de programar específica, donde se **organiza** el código en unidades denominadas **clases**, de las cuales se crean **objetos** que se relacionan entre sí para conseguir los objetivos de las aplicaciones.

Pensar en términos de objetos es muy parecido a cómo lo haríamos en la vida real. Por ejemplo vamos a pensar en un estudiante para tratar de modelizarlo en un esquema de POO.

Diríamos que el estudiante es el elemento principal que tiene una serie de **características**, como podrían ser el **nombre**, el **tipo de identificación** o el **número de identificación**. Además tiene una serie de **funcionalidades** asociadas, como pueden ser **estudiar** o **dormir**.

Por tanto, pensar en objetos requiere analizar qué elementos vas a manejar en tus programas, tratando de identificar sus **características** y **funcionalidades**. Una vez tengamos un ecosistema de objetos, éstos colaborarán entre sí para resolver los objetivos de las aplicaciones.

## Clases

En un esquema de programación orientada a objetos el **estudiante** sería lo que se conoce como **Clase**. La **clase** contiene la definición de las **características** de un modelo (el **estudiante**), como el **nombre**, el **tipo de identificación** o el **número de identificación**, junto con la implantación de sus funcionalidades, como **estudiar** o **dormir**.

Las **características** definidas en la clase las llamamos **propiedades** y las **funcionalidades** asociadas las llamamos **métodos**.

```kotlin
class Estudiante()
```

En el anterior ejemplo se crea una clase nombrada **Estudiante** sin propiedades. En caso de requerir adicionar propiedades (que es lo común) tendriamos que adicionarlos en los paréntesis como lo mostramos a continuación:

```kotlin
class Estudiante(var nombre: String, 
                 var tipoIdentificacion: String, 
                 var numIdentificacion: String)
```

### Propiedades

Las **propiedades** pueden tener un valor por defecto (como sucede con los parámetros en las funciones). Para definir un valor por defecto debemos indicarlo en la definición de la propiedad como lo mostramos a continuación:

```kotlin
class Estudiante(var nombre: String, 
                 var tipoIdentificacion: String = "CC", 
                 var numIdentificacion: String)
```

### Métodos

Los **metodos** se definen en el contenido de la **clase**. Según nuestro ejemplo debemos crear dos métodos : **estudiar** y **dormir**. 

```kotlin
class Estudiante(var nombre: String, 
                 var tipoIdentificacion: String = "CC", 
                 var numIdentificacion: String){
  
  fun estudiar(){
    println("El estudiante con nombre $nombre va a estudiar");
  }
  
  fun dormir(){
    println("El estudiante con nombre $nombre va a dormir");
  }

}
```

#### Constructor

Una **clase** en **Kotlin** tiene un **constructor principal** y posiblemente, uno o más **constructores secundarios**. El **constructor principal** se declara en el encabezado de la clase y va después del nombre de la **clase** y las **propiedades** de tipo opcionales.

A continuación vemos como en la definición de la clase **Estudiante** se adiciona el palabra clave **constructor** (este se incluye indirectamente siempre)

```kotlin
class Estudiante constructor(var nombre: String, 
                 var tipoIdentificacion: String, 
                 var numIdentificacion: String)
```

El **constructor principal** inicializa una **instancia** de una **clase** y sus **propiedades** en el encabezado de la clase. El encabezado de la clase no puede contener ningún código ejecutable. Si desea ejecutar algún código durante la creación de objetos, use el **bloque inicializador** dentro del cuerpo de la clase. Los **bloques inicializadores** se declaran con la palabra clave **init** seguida de llaves.

En el siguiente ejemplo podemos ver que se incluye el bloque inicializador **init** el cuál ejecuta la función **println**. Es decir, después de crear la **instancia** de la **clase** o el **objeto** se imprime por consola el valor de la **propiedad** **nombre**. 

```kotlin
class Estudiante constructor(var nombre: String, 
                 var tipoIdentificacion: String, 
                 var numIdentificacion: String){

                  init{
                    println("El nombre del estudiante es : $nombre")
                  }

                 }
```

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
```

En otras palabras, después de que se ejecuta el código en el cuál se crea el objeto **estudiante**, automáticamente se imprime por consola **El nombre del estudiante es : Jeyson**.

## Objetos

A partir de una **clase** podemos crear cualquier número de **objetos** de esa **clase**. Por ejemplo, a partir de la clase el **estudiante** podemos crear un estudiante nombrado Jeyson con tipo de identificación CC y número de identificación 1, otro nombrado Bryan con tipo de identificación CE y número de identificación 2. 

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson", "CC", "1");
var estudiante2 : Estudiante = Estudiante("Bryan","CE","2");
```

En el anterior ejemplo creamos dos objetos : **estudiante** y **estudiante2**. Los valores de las propiedades del objeto **estudiante** son : [nombre = "Jeyson", tipoIdentificacion = "CC", numIdentificacion = "1"]. Los valores de las propiedades del objeto **estudiante2** son : [nombre = "Bryan", tipoIdentificacion = "CE", numIdentificacion = "2"].

Para acceder a los valores de las **propiedades** de los **objetos** se debe hacer uso del operador (.) como se muestra a continuación:

```kotlin
println(estudiante.nombre);
```

Para ejecutar un **método** debemos hacer uso del operador (.) como se muestra a continuación:

```kotlin
println(estudiante.dormir())
```