---
comments: true
date: 2007-10-30 18:40:54
layout: post
slug: mi-mayor-aporte-a-la-seguridad-informatica
title: Mi mayor aporte a la seguridad informática
wordpress_id: 1112
categories:
- La Naturaleza del Software
- Programación
- Seguridad
tags:
- criptografía
- hash
- MD5
- seguridad
---

Escribo este artículo con orgullo y preocupación. Orgullo por el impacto que logró mi trabajo y preocupación porque, bueno ya van a ver porque.[![md5_name.jpg](file:///I:/documentos/blogs/lnds/La%20Naturaleza%20del%20Software%20%20Archivos%20Octubre%202007_files/md5_name-thumb-100x133.jpg)](http://www.lnds.net/md5_name.html)

El año 2005 escribí un [artículo en codeproject](http://www.codeproject.com/dotnet/HackingMd5.asp) donde mostré un esquema práctico que explotaba una de las vulnerabilidades encontradas en ese tiempo al algoritmo MD5. El artículo alcanzó notoriedad al ser destacado en [Slashdot](http://it.slashdot.org/article.pl?sid=05%2F09%2F23%2F0618252&tid=172&tid=93&tid=218), y en [Kriptópolis](http://www.kriptopolis.org/explotando-las-colisiones-de-md5).

Mi artículo original está en inglés y hay un (muy breve) [resumen](http://www.lnds.net/2005/09/explotando_las_colisiones_de_m.html) en este mismo blog.

La verdad es que no me preocupé much más del tema, y no estaba enterado de los derroteros que siguió esta prueba de concepto, pero haciendo una investigación reciente encontré el [trabajo de Peter Selinger](http://www.mathstat.dal.ca/~selinger/md5collision/), profesor e investigador de la [Universidad de Dalhouse](http://www.dal.ca/) en Canada que extendió mi esquema aprovechando el resultado de [Patrich Stach](http://www.stachliu.com/md5coll.c), que permite aprovechar los posteriores descubrimientos sobre las fallas de este algoritmo.

Otra sorpresa es que este trabajo ha sido mencionado como una [herramienta anti forense](http://ws.hackaholic.org/slides/AntiForensics-CodeBreakers2006-Translation-To-English.pdf) en círculos de hackers éticos.


### ¿De que se trata todo esto, y que implicancias tiene?


Les voy a dar un ejemplo.

Cuando ustedes van a un sitio donde se encuentran las imágenes de disco de Ubuntu encontrarán un archivo llamado MD5SUMS que en el caso de Ubuntu 7.10 contiene lo siguiente:


> ebf7ad055bc39634065daa10de980d7e *ubuntu-7.10-alternate-amd64.iso
9a4ae3cfd68911a861d094ec834c9b48 *ubuntu-7.10-alternate-i386.iso
61c87943a92bc7bf519da4e2555d6e86 *ubuntu-7.10-desktop-amd64.iso
d2334dbba7313e9abc8c7c072d2af09c *ubuntu-7.10-desktop-i386.iso
43ff753b260729b12c7d21d3a6db8c73 *ubuntu-7.10-server-amd64.iso
7d88cd87df509a740d9f47b9bbf1375e *ubuntu-7.10-server-i386.iso
5308a79f5e652edba5be84644ee14b09 *ubuntu-7.10-server-sparc.iso


La serie de numeros y letras a la izquierda de cada nombre nos indica el valor resultante al aplicar el algoritmo MD5 al archivo de la derecha.

En este caso, para la imagen del CD ubuntu-7.10-desktop-i386.iso el valor MD5 es d2334dbba7313e9abc8c7c072d2af09c.

Para validar de que nuestra imagen es la correcta, lo más seguro es aplicar un cálculo del hash MD5 en el archivo descargado y comprobar que coincida con lo informado en el sitio oficial de Ubuntu. Si estos valores coinciden sabemos que el disco no ha sido saboteado ni alterado por nadie.

Esto impide que un hacker malicioso pueda infectar Ubuntu con un virus o un trojano, ya que el hacker tendría que crear una imagen iso similar, reemplazarla en el servidor y asegurarse de que que el valor MD5 de su archivo coincida con lo informado por Ubuntu.

Hasta ahora eso parecía imposible, pero como demostré en el 2005 es muy sencillo escribir un programa extractor que burlara este mecanismo de verificación, aprovechando los fallos al algoritmo MD5 (descubiertos en ese tiempo por Xiaoyun Wang and Hongbo Yu de la Universidad de Shandong en China).

El problema con mi esquema es que requiere la distribución del programa extractor, pero la prueba de concepto de Selinger elimina esta traba.

Selinger es capaz de crear un programa "auto extractor", con lo que deja inutilzable la "firma MD5" como medio de validación de la integridad de los **archivos**.

Si pensamos en los **archivos** ISO con que se distribuyen las imagenes vivas de Ubuntu, y otros sistema operativos, estos **archivos** son "auto ejecutables", y por lo tanto aplica el esquema propuesto por Selinger.

La puerta está abierta para distribuir troyanos infectando cualquier distribución de linux que use MD5 como **único mecanismo de validación**.[1](http://www.lnds.net/2007/10/mi-mayor-aporte-a-la-seguridad-informati.html#fn1)

No es dificil imaginar una extensión al programa de Salinger para genera imagenes ISO maliciosas de muchos sistema operativos distribuidos de esta manera.

Por supuesto esta prueba de concepto también inhabilita el uso de MD5 como base para construir MAC (Message Autentication Code) en registros, transacciones o documentos digitales.

En este caso es más sencillo romper este mecanismo de control, porque los MACs siempre son ejecutados por programas externos, y para esto basta usar un esquema como el que describí en mi artículo original.

Han pasado 2 años de que sabemos estas cosas y aún me encuentro con implementaciones en que usan MD5 como un mecanismo de autenticar transacciones.[2](http://www.lnds.net/2007/10/mi-mayor-aporte-a-la-seguridad-informati.html#fn2)

Pero lo peor, es que todavía me topo con sistemas que proclaman su alto nivel de seguridad porque las claves de sus usuarios son almacenadas en MD5, algo no recomendado antes del 2005, y que aún sigue usándose.

¿Entienden ahora por qué aparte de orgullo siento preocupación?

[1] Insisto en lo de único mecanismo de verificación, porque en muchos casos se usan otras códigos de autenticación adicionales o complementarios, como firmas PGP o dos valores de hash, uno MD5 y otro SHA-1 por ejemplo.

[2] Lamentablemente muchos usuarios no saben o no se preocupan de verificar la integridad de las imágenes de los **archivos** descargados, así que muchas veces los hackers no necesitan algo tan complicado para vulnerar la distribución de sofware.
