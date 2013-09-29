---
comments: true
date: 2005-09-16 14:51:24
layout: post
slug: me-leeran-en-redmond
title: Me leerán en Redmond? :)
wordpress_id: 140
categories:
- Seguridad
---

Agradezco la elogiosa mención en [Kriptópolis](http://www.kriptopolis.org/node/1126), acerca de mi anterior post: [Explotando las colisiones de MD5](http://www.lnds.net/archives/2005/09/explotando_las.html).

Pero me entero a través del mismo sitio que Microsoft ha decidido abandonar el uso de las funciones de hash bajo ataque, e incluso la función criptográfica DES, mas detalles aquí: [http://www.kriptopolis.org/node/1126](http://www.kriptopolis.org/node/1126) y aquí:[http://www.eweek.com/article2/0,1759,1859751,00.asp](http://www.eweek.com/article2/0,1759,1859751,00.asp).

Me habrán leido en Redmond? :)

Como saben, escribí un par de artículos en [CodeProject](http://64.233.163.132/www.codeproject.com), el primero, [Good Bye MD5](http://www.codeproject.com/useritems/GoodbyeMD5.asp), lleva menos de un mes y ya ha tenido cerca de 20.000 lecturas, incluso con un interesante debate.  
Mi segundo artículo "Exploiting MD5 collisions" en que muestro como explotar el ataque a MD5 para perturbar los sistemas de distribución de software, lleva cerca de las 2000 lecturas en menos de 48 horas.

No es que me las quiera dar de genio, pero la verdad es que esto se sabe desde casi un año, y la base del ataque:
    
    <code style="margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; ">MD5(x)==MD5(y) => MD5(x+q) == MD5(y+q)</code>

desde hace mucho más tiempo.

Las bases de datos, y el algoritmo de las tablas Rainbow se conoce desde el 2003.

Lo que pasa es que ahora, tenemos las bases para crear esquemas para romper la seguridad basada estos algoritmos.

De hecho el esquema que presenté, es un tanto burdo, pero el [paper de Kaminsky](http://www.doxpara.com/md5_someday.pdf) , en que describe el script en perl[stripwire](http://www.doxpara.com/stripwire-1.1.tar.gz), me lleva a pensar, que es posible construir un ejecutable auto extraible, con un MD5 confiable, pero con un comportamiento dañino.

Es cuestión de tiempo...

Piensen por ejemplo, que la distribución de los **archivos** .RPM RedHat usan MD5 checksum, que tal si un hacker quiebra el utilitario RPM.  
O si uno coloca código malicioso en utilitarios como tar, o gzip, y con eso se deja vulnerable los MD5 de Apache, solo por mencionar algunas consecuencias.  
De hecho el ejemplo de los 2 **archivos** postscript, es un ejemplo de un autoejecutable atacado con la colision de MD5.



