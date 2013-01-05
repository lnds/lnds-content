---
comments: true
date: 2005-12-02 14:44:23
layout: post
slug: pinvoke-net-la-web-2-0-tambien-es-para-los-programadores
title: 'PInvoke.Net: La Web 2.0 también es para los programadores'
wordpress_id: 185
categories:
- La Naturaleza del Software
- Paradigmas
- Usabilidad
---

¿Qué es exactamente una aplicación Web 2.0?

Hay muchas ideas de lo que es y de lo que no es, pero creo que [PInvoke.Net](http://www.pinvoke.net/) es un gran ejemplo de lo que una aplicación Web 2.0 debe ser. En esta caso se trata de un servicio orientado a los programadores.

## ¿Qué es PInvoke.Net?

La definición de lo que es está en su propio sitio:

> PINVOKE.NET intenta disminuir la dificultad de invocar funcionalidades (APIs) de Win32 u otro tipo de codigo no manejado desde aplicaciones que escritas en código manejado (en lenguajes como C# y VB .NET). Definir las firmas de una función para usar PInvoke (también conocido como sentencias de declaración en VB) es un proceso propenso a error que puede introducir bugs (errores) extremadamente sutiles. Las reglas son complejas, y su usted comete un error probablemente corromperá la memoria.

En términos simples, los programadores de .Net tienen que llamar ciertas funciones disponibles en windows, para hacerlo se debe seguir un estricto protocolo, cuya declaración es compleja y propensa a errores.

En este sitio, lo que se hace es que los programadores que ya hayan resuelto una de estas llamadas publican el código adecuado para que otros lo puedan usar. La comunidad de programadores usa el Wiki como herramienta para compartir experiencia de programación.

## ¿Qué es la Web 2.0?

La mejor descripción de este concepto es el artículo de Tim O'Reilly: What is web 2.0?.  
Una forma de visualizarlo es en el Mapa del Meme incluido en ese artículo:  
![](http://www.oreillynet.com/oreilly/tim/news/2005/09/30/graphics/figure1.jpg)

## ¿ Por qué PInvoke.Net es una aplicación Web 2.0?

Basados en el Mapa del Meme Web 2.0 podemos identificar las siguientes características que hacen de PInvoke.Net una aplicación Web 2.0.

  * PInvoke confía en sus usuario, programadores en este caso, que colaboran escribiendo el código adecuado para cada API.
  * Tiene una experiencia de usuario enriquecida, incluso existe un plugin que permite integrar este servicio con Visual Studio.
  * Granularidad del contenido, cada API publicada puede ser usada para los usuarios de acuerdo a sus requerimientos.
  * Mejora en la medida que la gente usa la aplicación, esta es una propiedad natural de los wikis, en este caso en la medida que los programadores agregan nuevas APIs la información se enriquece, pero también es la misma comunidad la que mejora la calidad de la información. Incluso algunos usuarios informan porque no es bueno usar cierta API en determinadas condiciones, con lo que se agrega un valor mayor que lo pensado originalmente.
  * Es hackeable, el plugin es un ejemplo de esto, el hecho de que los usuarios incorporen tips y experiencia es otro, pero ya hay una serie de herramientas que se están desarrollando alrededor de este servicio.
  * La Data como el Intel Inside, toda la data en PInvoke es útil y valiosa para los programadores que la necesitan, este servicio ahorra horas de investigación, pruebas y depuración.
  * La larga cola (The Long Tail), este es un servicio para un nicho muy específio, los programadores que necesitan manejar código no manejado usando PInvoke en Microsoft.Net en Windows. Esta es una fracción relativamente pequeña de todos los programadores que usan Microsoft.Net.

Este es un buen ejemplo de como se pueden crear aplicaciones Web 2.0 para nichos específicos, una subcomunidad de programadores en este caso.

¿Qué esperan para crear sus propios servicios Web 2.0?



