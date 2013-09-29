---
comments: true
date: 2005-12-30 10:47:19
layout: post
slug: proteccion-contra-la-ultima-vulnerabilidad-de-windows
title: Proteccion contra la ultima vulnerabilidad de Windows
wordpress_id: 2034
categories:
- Seguridad
tags:
- Microsoft
- vulnerabilidades
- Windows
---

Hay gente que dice que la mejor protección contra las múltilples vulnerabilidades en windows, es no usar windows.
Eso es como este viejo chiste:

Paciente: Doctor, me duele cuando levanto los brazos.
Doctor: entonces no levante los brazos.

Como mucha gente usa Windows (la mayoría en realidad) voy a darles una receta [contra la última vulnerabilidad de windows](http://web.archive.org/web/20090426080921/http://www.blogmemes.com/akarru/comment.php?meme_id=302).


## La vulnerabilidad de los archivos WMF


Los archivos con extensión WMF son archivos gráficos, en Office se usan mucho en los famosos cliparts. Estos archivos contienen instrucciones y se reportó que es posible ejecutar código en modo privilegiado en máquinas con WIndows 2003 y Windows XP.Esto permitiría instalar spyware, troyanos, virus, etc.

Para deshabilitar la ejecución de los archivo WMF, mientras no aparezca el último parche de WIndows, se sugiere hacer lo siguiente:



	
  1. Click en el botón Inicio (Start)

	
  2. Click en Ejecutar (Run...)

	
  3. Ingresar el siguiente comando:"regsvr32 /u shimgvw.dll"

	
  4. Click en Aceptar (OK) cuando aparezca la ventana de confirmación.


Eso es todo.

Que lo pasen bien, por si no alcanzo a escribir algo antes de fin de año.


