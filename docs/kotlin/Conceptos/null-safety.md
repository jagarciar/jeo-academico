---
sidebar_position: 8
id: null-safety
title: Null Safety
description: ¿Cómo asingar una variable nula? ¿Cómo comparar el valor de una variable con null? ¿Qué es el operador Elvis?
tags:
  - Kotlin
  - nulo
  - Elvis
---

# Null Safety

**Null Safety** es una combinación de varias características como:

- Declare explícitamente cuándo se permiten valores **nulos** en su aplicación.
- Compruebe valores **nulos**.
- Utilice llamadas seguras a **propiedades** o **funciones** que puedan contener valores **nulos**.
- Declare acciones a tomar si se detectan valores **nulos**.

## Asigne valores nulos

**Kotlin** admite **tipos de datos** que aceptan valores **nulos**, lo que permite que el tipo declarado tenga valores **nulos**. De forma predeterminada, un tipo no puede aceptar valores **nulos**. Los tipos que aceptan valores **nulos** se declaran añadiendo explícitamente un signo **?** después de la **declaración** del tipo.

```kotlin
var nombre : String = "Jeyson Andrés García Rodríguez";
nombre = null;
```

En el anterior ejemplo a la variable **nombre** no se le puede asignar el valor **null**. Esto dado que en su declaración no se mencionó que la variable podria aceptar valores nulos. Su corrección se muestra a continuación:

```kotlin
var nombre : String? = "Jeyson Andrés García Rodríguez";
nombre = null;
```

## Compruebe valores nulos

La palabra reservada **null** puede ser comparada con el valor de una variable. Si la comparación es exitosa, el valor de la variable comparada es nulo. De lo contrario, es diferente de nulo. 

```kotlin
var nombre : String? = "Jeyson Andrés García Rodríguez";
if(nombre == null){
    println("La variable nombre es nula");
}
```

En el anterior ejemplo estamos comparando el valor de la variable **nombre** con **null**. Si el valor de la variable **nombre** es **nulo**, imprimirá por consola la frase **La variable nombre es nula**. 

## Llamadas seguras

Se recomienda que las **propiedades** de una **clase** permitan también valores **nulos** para que las llamadas a dichas propiedades sea segura. Esto aplica también para los **métodos**.

Supongamos el siguiente ejemplo:

```kotlin
class Estudiante(var nombre: String, 
                 var tipoIdentificacion: String = "CC", 
                 var numIdentificacion: String){
  
  fun estudiar(nuevoNombre : String) : String{
    nombre = nuevoNombre;
    return "El estudiante con nombre $nombre va a estudiar";
  }
  
}
```

En el anterior ejemplo se creó la clase **Estudiante** la cuál tiene las **propiedades** : **nombre**, **tipoIdentificacion** y **numIdentificacion**. Según su declaración, las propiedades no permiten valores **nulos**. La clase **Estudiante** tiene definido un **método** llamado **estudiar**. El método **estudiar** tiene un **parámetro** llamado **nuevoNombre** de tipo **String** que tampoco permite valores **nulos**. El método **estudiar** debe retornar un **String** (ningún otro valor). 

Si quisieramos cambiar un poco las restricciones de los valores nulos sobre los métodos y las propiedades de la clase **Estudiante** tendriamos que incluirle el operador **?** como se muestra a continuación:

```kotlin
class Estudiante(var nombre: String?, 
                 var tipoIdentificacion: String?, 
                 var numIdentificacion: String?){
  
  fun estudiar(nuevoNombre : String?) : String?{
    nombre = nuevoNombre;
    return "El estudiante con nombre $nombre va a estudiar";
  }
}
```

Con esta definición de una **clase**, podemos realizar llamadas seguras a las **propiedades** o a sus **métodos**:

```kotlin
var estudiante : Estudiante? = Estudiante("Jeyson", "CC", "1");
println(estudiante?.estudiar("Josue"));
```

En este caso, la llamada segura es la inclusión del operador **?** después de invocar o usar una variable, propiedad o método que recibe o retorna valores nulos. 

## Operador Elvis

Puede proporcionar un valor predeterminado para devolver si se detecta un valor nulo utilizando el operador **Elvis** :  **?:**.

Escriba en el lado izquierdo del operador **Elvis** lo que se debe **verificar** en caso de detectar un valor **nulo**. Escriba en el lado derecho del operador **Elvis** lo que se debe **devolver** si se detecta un valor **nulo**.

```kotlin
var estudiante : Estudiante? = Estudiante("Jeyson", "CC", "1");
var mensaje : String = estudiante?.estudiar("Josue") ?: "Sin resultado"; 
```

En el anterior ejemplo se usó nuestra clase **Estudiante** para crear la variable **estudiante**. Se creó una segunda variable llamada **mensaje** la cuál no permite valores **nulos**. El valor de la variable **mensaje** depende del resultado de la ejecución del método **estudiar** de la clase **Estudiante**. El operador **Elvis** valida si el retorno del método **estudiar** es **nulo** para asignarle a la variable **mensaje** el valor **Sin resultado**. 
