---
sidebar_position: 11
id: visbilidad
title: Visibilidad
description: ¿Qué es public? ¿Qué es private? ¿Qué es protected? ¿Qué es internal?
tags:
  - Kotlin
  - public
  - private
  - protected
  - internal
---

# Modificadores de visibilidad

Las **clases**, los **objetos**, las **interfaces**, los **constructores** y las **funciones**, así como las **propiedades** y sus definidores, pueden tener **modificadores de visibilidad**. Los **métodos** **get** siempre tienen la misma visibilidad que sus propiedades.

Hay cuatro modificadores de visibilidad en Kotlin: **private**, **protected**, **internal** y **public**. La visibilidad predeterminada es **public**.

**public** define una visibilidad pública, es decir, la **clase**, **función**, **propiedad**, etc pueden ser accedidas desde cualquier parte de la aplicación. Es el modificador de visibilidad por defecto, es decir, si no se incluye, todo lo que se cree  será de tipo **public**.

```kotlin
public open class Persona (public open var nombre: String,
                    protected open var tipoIdentificacion : String,
                    internal open var numIdentificacion : String,
                    private var apellido :String){

}
```

En el anterior ejemplo se creó la clase **Persona** con cuatro **propiedades** : **nombre**, **tipoIdentificacion**, **numIdentificacion** y **apellido**. La propiedad **nombre** es de tipo **String** y es **public**, es decir, puede ser accedida desde cualquier componente de nuestra aplicación. La propiedad **tipoIdentificacion** es de tipo **String** y es **protected**, lo cuál quiere decir que solo será visible por las **sub-clases**. La propiedad **numIdentificacion** es de tipo **String** y es **internal**. El modificador de visibilidad **internal** está relacionado con la visibilidad de la propiedad a nivel del **módulo**. Finalmente tenemos la propiedad **apellido** de tipo **String** y que tiene un modificador de visibilidad **private**. Las propiedades con el modificador de visibilidad **private** no pueden tener la palabra reservada **open**, por tal razón, no puede ser sobre-escrita por la **sub-clase**. 

```kotlin
private class Estudiante ( override var nombre: String,
                   override var tipoIdentificacion: String,
                   override var numIdentificacion: String,
                   var ID : String?) : Persona(nombre, tipoIdentificacion, numIdentificacion, ""){

}
```

En el anterior ejemplo creamos la clase **Estudiante** la cuál es una **sub-clase** de la **super-clase** **Persona**. La clase **Estudiante** sobre-escribe la definición de las propiedades : **nombre**, **tipoIdentificacion** y **numIdentificacion**. Dado que la clase **Persona** tiene una propiedad **apellido** la cuál es **private**, el constructor de **Persona** lo solicita, pero la clase **Estudiante** no puede sobre-escribirla por lo que debe enviar un valor por defecto. 