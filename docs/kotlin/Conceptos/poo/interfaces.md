---
sidebar_position: 4
id: interfaces
title: Interfaces
description: ¿Qué es una interface?
tags:
  - Kotlin
  - interface
  - super
  - Herencia
---

# Interfaces

Las **interfaces** en **Kotlin** pueden contener declaraciones de **métodos abstractos**, así como **implementaciones de métodos**. Lo que las diferencia de las **clases abstractas** es que las **interfaces** no pueden **almacenar** el **estado**. Pueden tener **propiedades**, pero estas deben ser **abstractas** o proporcionar implementaciones de acceso.

```kotlin
interface Dispositivo {

    var capacidadAlmacenamiento: Int

    fun conectar() : String
    fun desconectar() : Int {
      return 0;
    }
}
```

En el anterior ejemplo se creó la interface **Dispositivo** la cuál tiene definida una propiedad : **capacidadAlmacenamiento** de tipo **Int** y dos métodos : **conectar** y **desconectar**. El método **conectar** no tiene ningún parámetro pero retorna un **String**. El método **desconectar** no tiene ningún parámetro pero retorna un **Int**. 

:::tip
Una **clase** puede implementar más de una **interface** pero solo puede heredar de una **super-clase**
:::

```kotlin
class Huawei : Dispositivo {
        override var capacidadAlmacenamiento: Int = 0
            get() {
                return field
            }
            set(value) {
                field = value
            }

        override fun conectar(): String {
            return "Conectando..";
        }
}   
```

En nuestro anterior ejemplo se creó la clase **Huawei** la cuál implementa la interface **Dispositivo**. Dado esto, **Huawei** debe hacer uso del operador **override** para sobre-escribir la definición de la propiedad **capacidadAlmacenamiento** y el método **conectar**. Dado que en la interface **Dispositivo** el método **desconectar** no es **abstracto**, es decir, no solo está declarado sino también implementado, no requiere obligatoriamente del **override**. 

:::tip
Una **interface** puede derivar de otras **interfaces**, lo que significa que puede proporcionar implementaciones para sus miembros y declarar nuevos **métodos** y **propiedades**.
:::

## Resolución de conflictos

Supongamos el siguiente caso : Tenemos dos interfaces : **InterfaceA** e **InterfaceB**. Ambas interfaces van a implementar dos métodos : **metodo1** y **metodo2** los cuáles no retornan ningún valor y no tienen parámetros. Para la **InterfaceA** ambos métodos están implementados, sin embargo, para la **InterfaceB** el **metodo2** es **abstracto**.

```kotlin
interface InterfaceA {

    fun metodo1(){

    }
    fun metodo2(){

    }

}

interface InterfaceB {

    fun metodo1(){

    }
    fun metodo2()

}
```

Ahora supongamos que tenemos una clase **ClaseC** la cuál implementa la interface **InterfaceA** y la interface **InterfaceB**:

```kotlin
class ClassC : InterfaceA, InterfaceB {
    
}
```

Dado que la clase **ClaseC** implementa ambas interfaces : **InterfaceA** e **InterfaceB** debe sobre-escribir por lo menos el método **metodo2** dado que es **abstracto** para la **InterfaceB**. Para poder invocar la implementación del método **metodo1** de la **InterfaceA** e **InterfaceB** debemos hacer uso de la palabra reservada **super**. 

```kotlin
 class ClassC : InterfaceA, InterfaceB {
        override fun metodo1(){
            super<InterfaceA>.metodo1()
            super<InterfaceB>.metodo1()
        }
        override fun metodo2(){
            super<InterfaceA>.metodo2()
        }
    }
```

Tengamos presente que el **metodo2** es **abstracto** para la **InterfaceB** por lo que no se podría invocar este método desde la **ClaseC**. 