---
comments: true
date: 2005-08-25 01:37:57
layout: post
slug: usando-one-way-hash
title: Usando one-way hash
wordpress_id: 123
categories:
- Seguridad
tags:
- criptografía
- hash
---

En [codeproject](http://www.codeproject.com/useritems/GoodbyeMD5.asp), escribí sobre este tema, voy a empezar escribir sobre lo mismo, pero en cristiano (como decía mi abuelita), en este blog.

La razón, es que hay muchas malas implementaciones y aplicaciones de de la criptografía, y como mucha documentación está en inglés, muchos programadores no tienen un acceso fácil a estos temas (aprendan inglés muchachos).

La crísis de las funciones de hash

Se puede leer sobre la crisis de populares funciones de hash en toda la internet, esto debido a los recientes descubrimientos en el campo de la criptología, por ejemplo, en el sitio del [Gurú Bruce Schneier](http://www.schneier.com/blog/archives/2005/08/new_cryptanalyt.html), se ha dado una interesante discusión sobre los resultados que permiten "quebrar" los algoritmos como MD5 y SHA-1.

Anteriormente, sugerí que no se debe almacenar las claves en una base de datos en texto plano, y escribí que:

[No guarde la clave en claro en su sitio, no importa cuanto empeño le pongas, no existe sistema de seguridad perfecto. Lo mejor es hacer un hash con la clave.](http://www.lnds.net/archives/2005/08/no_comprometas.html)

Funciones de Hash en una dirección

Las siguientes definiciones vienen del libro de Bruce Schneier, ["Applied Cryptography Second Edition":](http://64.233.163.132/search?q=cache:PAxf6qcSFiUJ:www.lnds.net/2005/08/+Archivos+Agosto+2005+site:www.lnds.net&cd=1&hl=en&ct=clnk#libro)

> Una función de hash de una sola vía (one-way hash function) H(M), opera en sobre un mensaje M, de un largo arbitrario, y retorna un valor de un largo fijo, h.
> 
> h = H(M)
> 
> donde h es de largo m.
> 
> Muchas funciones pueden tomar una entrada de largo arbitrario y retorna un valor de largo fijo, pero las funciones de hash de una via tienen las siguientes características adicionales:
> 
> Dado M, es fácil computar h.  
Dado h, es dificil computar M, de modo tal que H(M) = h.  
Dado M, es dicil encontrar otro mensaje, M', tal que H(M) = H(M').   
....
> 
> En algunas aplicaciones, que sea de una vía es insuficiente; se requiere, una requerimiento adicional llamado resistencia a las colisiones:
> 
> Es dificil encontrar dos **mensajes aleatorios**, M y M', tal que H(M) = H(M').

Funciones de hash usadas para almacenar claves

Las definciones anteriores, nos lleva al desarrollo de un esquema de almacenamiento seguro de claves.

Este uso se describe con el siguiente algorimo:

1. Para almacenar una clave, solicite que el usuario ingrese una clave en texto plano (plain_password), luego aplique una función de hash de una vía H sobre plain_password y almacenela.   
En código:  
stored_message = H(plain_password)

3. Para verificar las claves, solicite una clave al usuario, aplique H a esta clave de prueba (probe_password), y compare con el valor almacenado, es decir:  
check ::= H(probe_password) == stored_password

Este esquema es tan bueno, dependiendo de la fortaleza de la función H.

El problema, es como elegir una función de hash adecuada, una de la más usadas es la función **MD5**, la cual se encuentra bajo un ataque masivo, por ejemplo en el sitio [http://passcracking.com/ ](http://passcracking.com/)uno ingresa, un hash en MD5 y despues buscar dentro de la base de datos de valores que colisionan con el valor dado.

Más adelante veremos como mejorar los hash, agregándole sal :)



