---
comments: true
date: 2009-07-12 20:19:13
layout: post
slug: fuerza-bruta
title: Fuerza bruta
wordpress_id: 252
categories:
- Seguridad
tags:
- privacidad
- seguridad
---

Hay que [ser muy torpe](http://www.codinghorror.com/blog/archives/000631.html) para intentar un ataque de fuerza bruta sobre SHA-256. Cuando Leo Prieto intenta minimizar los alcances [de la intrusión a los sitios de Betazeta](http://leo.prie.to/2009/07/incidente-de-seguridad/) de este viernes, en realidad hunde más sus pies en el barro, y le [da más argumentos a los que justifican este ataque](http://www.antronio.com/comunidad/f7/fayerwayer-hackeado-betazeta-owen-503370/index10.html#post15579254).

Antes de seguir, quiero decir que condeno estos defacement y ataques sitios web, como lo que le ocurrió a[BetaZeta](http://www.betazeta.com/) este fin de semana. /* Fayerwayer en todo caso ha [sido bastante sarcástico cuando esto le pasa a otros](http://www.fayerwayer.com/2008/08/alerta-se-filtran-datos-personales-de-los-alumnos-de-la-usach/), pero dejemos esa polémica hasta acá. */

>   


Es un dato que hay delincuentes allá afuera, entonces debemos tomar las medidas para protegernos, y cuidar la seguridad de nuestras casas. Betazeta ha crecido a un punto en que tiene muchos sitios importantes expuestos, pero también maneja la información de muchos usuarios, entonces eso implica que debe ser más profesional en la administración de su seguridad.

No basta con usar un super algoritmo de hash, porque solo los estúpidos intentarán un ataque de [fuerza bruta](http://en.wikipedia.org/wiki/Brute_force_attack) a tus claves,  lo primero que hará un hacker es un ataque de diccionario.

Cuando un desarrollador dice que sus claves son seguras porque las almacena usando un hash avanzado, en realidad está resolviendo el problema usando fuerza bruta, y sólo los idiotas usan la fuerza bruta para resolver los problemas de seguridad.

Más importante que el algoritmo de cifrado, es tener un esquema de seguridad o política de seguridad en la administración de claves:

    1. Exigir el cambio de las claves con frecuencia.
    2. No permitir el uso de palabras comunes, o que estén en un diccionario.
    3. Exigir un mínimo de caracteres para la clave (10 o más).
    4. Exigir la combinación de letras, números y símbolos en las claves.
    5. Nunca almacenar las claves en texto plano, o con algoritmos débiles de criptografía.
    6. No almacenar sólo el hash de la clave, usar un mecanismo que genere algo de entropía en la clave almacenada (salt, o algo similar).

Lo más importante, es no tratar de inventar tu propio esquema de seguridad, porque es probable que lo hagas mal.



