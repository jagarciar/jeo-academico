---
sidebar_position: 3
id: herencia
title: Herencia
description: ¿Qué es una superclase? ¿Qué es una subclase?
tags:
  - Kotlin
  - open
  - Herencia
---

# Herencia

La **herencia** es un mecanismo que permite crear una nueva clase, conocida como **clase hija** o **sub-clase**, a partir de una clase existente llamada **clase padre** o **super-clase**.

La **clase hija** hereda las **propiedades** y los **métodos** de la **clase padre**, lo que permite reutilizar el código existente y extender la funcionalidad de la clase original.

Veamos un ejemplo : Vamos a implementar la clase **Persona**. Una persona tiene las siguientes propiedades : **tipoIdentificacion**, **numIdentificacion** y **nombre**. Todas las propiedades son de tipo **String** y deben permitir valores **nulos**. Una persona tiene un método : **caminar**. El método **caminar** recibe un parámetro de tipo **Int** nombrado **kilometros**. El método **caminar** debe retornar un **String** con el mensaje **La persona $nombre va recorrer $kilometros kilometros**.

```kotlin
open class Persona(open var nombre: String?, 
                 open var tipoIdentificacion: String?, 
                 open var numIdentificacion: String?){
    
    fun caminar(kilometros : Int) : String {
        return "La persona $nombre va recorrer $kilometros kilometros";
    }
}
```

:::tip
De manera predeterminada, las clases de **Kotlin** son **finales**, es decir, no se pueden heredar. Para que una clase sea heredable, márquela con la palabra clave **open** (aplica también para **propiedades** y **métodos**).
:::

Vamos a crear una segunda clase : **Estudiante**. La clase estudiante es una **sub-clase** de **Persona**. Por tal motivo, la clase **Persona** es una **super-clase**. La clase **Estudiante** tendrá una **propiedad** nombrada **ID** de tipo **Int**, el cuál no debe permitir valores **nulos**. La clase **Estudiante** debe implementar un método : **estudiar**. El método **estudiar** recibe un parámetro de tipo **Int** nombrado **horas**. El método debe retornar un **String** con el mensaje **El estudiante $nombre va estudiar $horas horas**.

:::tip
Si la **clase hija** tiene un constructor primario, la **clase padre** debe inicializarse en ese constructor primario de acuerdo con sus parámetros.

Si la **clase hija** no tiene un constructor principal, entonces cada **constructor secundario** debe inicializar el tipo base utilizando la palabra clave **super** o debe delegar en otro constructor que lo haga. 
:::

```kotlin
class Estudiante(
        override var nombre: String?,
        override var tipoIdentificacion: String?,
        override var numIdentificacion: String?,
        var ID : Int) : Persona(nombre, tipoIdentificacion, numIdentificacion){

    fun estudiar(horas : Int) : String {
            return "El estudiante $nombre va estudiar $horas horas";
    }
}
```

En el anterior ejemplo se visualiza una nueva palabra reserva : **override**. Esta palabra clave debe ser usada siempre que se quiera heredar de la **clase padre** un conjunto de **propiedades** y/o **métodos** a las **clases hijas**.

Teniendo en cuenta lo anterior podemos hacer lo siguiente:

```kotlin
var estudiante : Estudiante = Estudiante("Jeyson","CC","1", 1);
println(estudiante.caminar(10));
```

La variable **estudiante** de tipo **Estudiante** esta ejecutando el **método** **caminar** de la **super-clase** **Persona**. 

Ahora, supongamos que al método **caminar** le adicionamos la palabra reservada **open**. Esto permite que la **clase hija** **Estudiante** pueda realizar un **override**. 

```kotlin
open class Persona(open var nombre: String?, 
                 open var tipoIdentificacion: String?, 
                 open var numIdentificacion: String?){
    
    fun caminar(kilometros : Int) : String {
        return "La persona $nombre va recorrer $kilometros kilometros";
    }
}
 class Estudiante(
        override var nombre: String?,
        override var tipoIdentificacion: String?,
        override var numIdentificacion: String?,
        var ID : Int) : Persona(nombre, tipoIdentificacion, numIdentificacion){

    fun estudiar(horas : Int) : String {
            return "El estudiante $nombre va estudiar $horas horas";
    }
        
    override fun caminar(kilometros : Int) : String {
        return "El estudiante $nombre va caminar $kilometros kilometros";
    }
}
```

En el anterior ejemplo, la **sub-clase** **Estudiante** hizo un **override** del método **caminar** de la **super-clase** **Persona**. Es decir, si una variable de tipo **Estudiante** ejecuta el método **caminar** el resultado será **El estudiante $nombre va caminar $kilometros kilometros**. 

Pero, si quisieramos invocar el método **caminar** de la **super-clase** **Persona** y concatenarla al resultado que retorna el método **caminar** en la **sub-clase** **Estudiante**, ¿cómo se deberia hacer?. En este caso se debe hacer uso de la palabra reservada **super**. 

```kotlin
override fun caminar(kilometros : Int) : String {
    var padre : String = super.caminar(kilometros);
    return padre + " El estudiante $nombre va caminar $kilometros kilometros";
}
```

En el anterior ejemplo, en el método **caminar** de la **sub-clase** **Estudiante** se ejecuta previamente el método **caminar** de la **super-clase** **Persona**. 