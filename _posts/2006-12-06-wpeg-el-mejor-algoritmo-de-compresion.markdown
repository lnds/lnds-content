---
comments: true
date: 2006-12-06 12:13:49
layout: post
slug: wpeg-el-mejor-algoritmo-de-compresion
title: WPEG, el mejor algoritmo de compresión
wordpress_id: 1380
categories:
- Humor
---

Esto es un artículo humorístico)


## WPEG


WPEG es un algoritmo de compresión, superior en todos los aspectos a cualquier algoritmo existente de compresión de archivos (o ficheros).


## Principios de Diseño





	
  * Lograr la máxima razón de compresión sin pérdida para cualquier archivo

	
  * Proveer archivos comprimidos en un formato ASCII legible para los humanos.

	
  * Permitir a un software común, como un navegador web pueda descomprimir el archivo sin requerir de plug-ins adicionales.




## Descripción del Algoritmo


**Algoritmo Compresión**

El programa de compresión carga el archivo en un servidor web, luego entrega la URL a[http://tinyurl.com/](http://replay.waybackmachine.org/20071028215435/http://tinyurl.com/) para obtener una URL corta donde enlazar.. La parte de la URL despúes de "http://tinyurl.com/" es retornada como un archivo comprimido. Esta es una cadena ASCII.

**Algoritmo de Descompresión**

Cualquier explorador web puede descomprimir el archivo comprimido, simplemente ingresando en la barra de direcciones "[http://tinyurl.com/](http://replay.waybackmachine.org/20071028215435/http://tinyurl.com/)" seguido por el contenido del archivo comprimido. El navegador recupera el archivo desde el servidor, descomprimiendo la corta cadena ASCII en el archivo original, sin pérdidad de datos.


## Análisis


Para analizar el desempeño, varios archivos de 100 Giga Bytes fueron comprimidos usando el algoritmo. El programa retornó versiones comprimidas de los archivos consistente de sólo 5 caracteres ASCII. Dado que 5 bytes, representa una tasa de compresión ligeramante de 2×10 elevado a 11. Con archivos más grandes se pueden lograr tasas de compresión mayores.

(Esto es un artículo humorístico)
(fuente original en inglés: [Esoteric Algorithms: WPEG](http://replay.waybackmachine.org/20071028215435/http://www.dangermouse.net/esoteric/wpeg.html))
