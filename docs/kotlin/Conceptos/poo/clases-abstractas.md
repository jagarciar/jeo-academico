---
sidebar_position: 5
id: clases-abstractas
title: Clases abstractas
description: ¿Qué es una clase abstracta?
tags:
  - Kotlin
  - Data abstract
  - open
  - abstract
  - Herencia
---

# Clases abstractas

Una **clase abstracta** es una **clase** que no puede ser **instanciada** directamente. Es decir, no se pueden crear **objetos** directamente a partir de ella. Para utilizar una **clase abstracta**, es necesario **heredar** de ella y proporcionar una **implementación** completa para todos los **métodos abstractos** definidos en la **clase abstracta**.

¿Para qué puedes querer una clase que no puede ser instanciada? Una **clase abstracta** se utiliza para definir una **estructura común** que puedo reusar mediante **herencia**, pero que no está lista para ser utilizada directamente en el código.

## Métodos abstractos

Los **métodos abstractos** son **métodos declarados**, pero que no tienen una implementación en la **clase** donde se declaran. Al no tener una implementación, ninguna clase que tenga un **método abstracto** puede ser instanciada. Por tanto, inmediatamente pasará a ser una **clase abstracta**.

Supongamos el siguiente ejemplo:

```kotlin
abstract class Dispositivo {
    abstract fun conectar() : String
    abstract fun desconectar() : String
}
```

Se creó la **clase abstracta** **Dispositivo** la cuál tiene definido dos **métodos abstractos** : **conectar** y **desconectar**. El **método abstracto** **conectar** no tienen ningún parámetro pero retorna un **String**. El **método abstracto** **desconectar** no tienen ningún parámetro pero retorna un **String**. 

```kotlin
class Huawei : Dispositivo(){
    override fun conectar : String (){

    }
    override fun desconectar : String (){
        
    }
}
```

Se creó la clase **Huawei** la cuál **hereda** de la **clase abstracta** **Dispositivo** los métodos **conectar** y **desconectar**. Al heredar estos métodos, la clase **Huawei** debe hacer uso de la palabra reservada **override** para sobre-escribir su implementación. 