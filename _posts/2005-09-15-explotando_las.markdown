---
comments: true
date: 2005-09-15 15:03:20
layout: post
slug: explotando_las
title: Explotando las colisiones de MD5
wordpress_id: 1419
categories:
- Sin categoría
---

Escribí un programa en C# para demostrar como se puede explotar las colisiones encontradas en MD5 para crear 2 archivos con el mismo valor de hash.

Esta imagen muestra la prueba de concepto:
[![](http://www.lnds.net/blog/wp-content/uploads/2011/01/screenshot.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/01/screenshot.jpg)

Primero generamos 2 archivos binarios para distribuir, usando un programa inofensivo (good.exe), y otro programa peligroso (evil.exe).

El valor MD5 para ambos archivos es el mismo.
Posteriormente un programa extractor saca distintas versiones del programa, dependiendo del archivo de distribución que se le entrega.
En el primer caso vemos como se extrae del archivo good.bin el programa inofensivo, y se ejecuta sin problemas.
En el segundo caso, el usuario extrae del archivo evil.bin nuestro programa dañino, como el usuario está confiado de que el archivo no ha sido alterado, debido a que su hash MD5 es el correcto, ejecuta un programa, que en este caso puede hacer mucho daño, como formatear el disco.

Puedes bajar los fuentes de la prueba de concepto de este archivo:
Codigo Fuente para Visual Studio 2003.

Y la versión compilada desde acá:
Demo compilada

Este desarrollo se basó en los siguientes papers:

[http://www.cits.rub.de/MD5Collisions/](http://www.cits.rub.de/MD5Collisions/)

[http://www.doxpara.com/md5_someday.pdf](http://www.doxpara.com/md5_someday.pdf)

Un artículo mas detallado lo publiqué en [CodeProject](http://replay.waybackmachine.org/20090426080906/http://www.cits.rub.de/MD5Collisions/).
