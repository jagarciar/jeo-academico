---
sidebar_position: 1
id: multiplatform
title: Multiplataforma
description: ¿Qué es una List? ¿Qué es un Set? ¿Qué es un Map?
tags:
  - Kotlin
  - Android
  - iOS
  - Web Development
  - Cross Platform
---

# Conceptos básicos

## Kotlin Multiplatform

**Kotlin Multiplatform** es una tecnología que te permite crear aplicaciones 
para varias **plataformas** y **reutilizar código** de manera eficiente en ellas, 
al tiempo que conserva los beneficios de la **programación nativa**. 
A través de **Kotlin** podemos desarrollar una aplicación que se ejecute en **iOS**, **Android**, **macOS**, 
**Windows**, **Linux** y más. 

## Common code

El **código común** es el código de **Kotlin** compartido entre diferentes plataformas
que generalmente se encuentra en el directorio **commonMain**. La ubicación de los archivos
de código es importante ya que afecta a la lista de plataformas en las que se compila 
este código. El **compilador** de **Kotlin** obtiene el **código fuente** como entrada y 
como resultado produce un conjunto de **binarios** específicos según las 
**plataformas** deseadas.

## Target

Los **target** definen las **plataformas** en las que **Kotlin** compila el **código común**. 
Estos podrían ser por ejemplo **JVM**, **JS**, **Android**, **iOS** o **Linux**. 


