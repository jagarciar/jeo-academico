---
sidebar_position: 10
id: paquetes
title: Paquetes
description: ¿Qué es un paquete? ¿Cómo importo un paquete?
tags:
  - Kotlin
  - package
  - import
---

# Paquetes

Cuando escribimos código fuente, es posible que el resultado de nuestro programa sea bastante grande (hablamos de posiblemente miles de líneas de código). Y si estamos hablando de **programación orientada a objetos**, podríamos tener cientos o miles de clases distintas y relacionadas entre sí. Los **paquetes** son una forma de organizar grupos de **clases**. Un **paquete** contiene un conjunto de clases relacionadas bien por finalidad, por ámbito o por herencia. Las clases tienen ciertos privilegios de acceso a las **propiedades** y a los **métodos** de otras clases dentro de un mismo paquete.

Supongamos el siguiente ejemplo : Vamos a crear 2 archivos en nuestro entorno de desarrollo de preferencia. Cada archivo representará una **clase** con los siguientes nombres : **Persona** y **Estudiante**. 

La clase **Persona** será una **super-clase** la cuál tendrá las siguientes propiedades : **nombre**, **tipoIdentificacion** y **numIdentificacion**. Esta clase estará alojada en el **paquete** **org.jeo.academico.superclases**. 

```kotlin title="/src/Persona.kt"

package org.jeo.academico.superclases

open class Persona (open var nombre: String, 
                    open var tipoIdentificacion : String,
                    open var numIdentificacion : String ){
    
}

```

La clase **Estudiante** será una **sub-clase** la cuál tendrá las siguientes propiedades : **ID**. Esta clase estará alojada en el **paquete** **org.jeo.academico.subclases**. 

```kotlin title="/src/Estudiante.kt"

package org.jeo.academico.subclases
import org.jeo.academico.superclases.Persona

class Estudiante ( override var nombre: String,
                   override var tipoIdentificacion: String,
                   override var numIdentificacion: String,
                   var ID : String?) : Persona(nombre, tipoIdentificacion, numIdentificacion){
                       
}
```

Dado que la clase **Estudiante** se encuentra alojada en el paquete **org.jeo.academico.subclases** y la clase **Persona** se encuentra alojada en el paquete **org.jeo.academico.superclases**, la clase **Estudiante** debe **importar** el paquete donde se encuentra alojada la clase **Persona**. La importación se realiza a través de la palabra reservada **import**. 

