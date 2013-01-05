---
comments: true
date: 2007-09-11 23:56:12
layout: post
slug: '%c2%bfgiga-o-gibi-bytes'
title: ¿giga o gibi bytes?
wordpress_id: 708
categories:
- Ciencia
- Cultura
tags:
- almacenamiento
- computación
- matemáticas
- memoria
---

Si ejecuto el comando df en mi notebook actual me informa que tengo 141+81 Giga


> Filesystem Size Used Avail Use% Mounted on
c: 141G 62G 80G 44% /cygdrive/c
d: 8.1G 6.1G 2.0G 76% /cygdrive/d


Eso da 149.1 gigabytes, bastante menos que los 160GB que declara la descripción de mi equipo.

Pero la verdad es que los fabricantes de discos duros usan correctamente el prefijo Giga, que corresponde a 10 elevado a 9, mil millones, o en cifras 1.000.000.000.

Los fabricantes de discos duros usan la notación de prefjos definidos por la [Oficina Internacional de Pesos y Medidas](http://www.bipm.org/). El [sistema internacional de unidades](http://es.wikipedia.org/wiki/Sistema_Internacional_de_Unidades) define los prefijos para las potencias de 10:








Factor


Prefijo


Símbolo


Factor


Prefijo


Símbolo






10E24


yotta


Y


10E-24


yocto


y






10E21


zetta


Z


10E-21


zepto


z






10E18


exa


E


10E-18


atto


a






10E15


peta


P


10E-15


femto


f






10E12


tera


T


10E-12


pico


p






10E9


giga


G


10E-9


nano


n






10E6


mega


M


10E-6


micro


µ






10E3


kilo


k


10E-3


mili


m






10E2


hecto


h


10E-2


centi


c






10E1


deca


da


10E-1


deci


d




De este modo, 160 Gigabytes corresponde a 160E9 bytes, 0 160.000.000.000 bytes.

Pero en la tradición en informática un Gigabyte corresponden a 1024 mega bytes, y un mega byte son 1024 kilobytes, los que a su vez corresponden a 1024 bytes. Como todo se expresa en potencias de 2, un kilobyte correspondía a 2 elevado a 10, un mega a 2 elevado 20, y un gigabyte corresponde a 2 elevado a 30.

Los sistemas operativos, y las herramientas que trabajan con discos duros (como el comando df), siguen esta costumbre, y todo se expresa en potencias de 2, pero usando los prefijos del sistema decimal.

Con el fin de evitar confusiones la [IEEE](http://www.ieee.org/) definió el estándar IEEE-1541, el que fue incluido en el estandar de la Comisión Electrotécnica Internacional IEC 60027 que define los símbolos y letras usados en electrónica.

Este estándar define nuevos prefijos para las potencias de 2:








kibibyte


KiB


2e10






mebibyte


MiB


2e20






gibibyte


GiB


2e30






tebibyte


TiB


2e40






pebibyte


PiB


2e50






exbibyte


EiB


2e60






zebibyte


ZiB


2e70






yobibyte


YiB


2e80







	
  * Acá use la notación 2eXX para indicar 2 elevado a XX.


Por lo tanto, mi disco duro de 160 Gigabytes, tiene una capacidad de 149.1 Gibibytes.

Aunque las abreviaciones son usadas en algunas publicaciones y software, el uso de este estándar es bajo, y tal como [apunta Jeff Atwood](http://www.codinghorror.com/blog/archives/000950.html) las razones serían que: los prefjios suenan ridículos, los fabricantes de discos duros no los usan, y la tradición prevalece.

Estas confusiones sobre como designar las medidas de los discos duros han llevado a [juicios bastante notorios](http://en.wikipedia.org/wiki/Binary_prefix#Legal_disputes), y muchos usuarios se disgustan cuando compran un disco duro y al visualizarlos con sus sistema operativos notan que "han perdido" muchos megabytes. Hoy en día con discos duros con más de 80 Giga bytes las diferencias, entre lo informado por el fabricante y lo reportado por el sistema operativos, pueden llegar al 7%.
