---
comments: true
date: 2007-12-27 21:19:05
layout: post
slug: el-problema-de-tinyurl-y-otros-servicios-similares
title: El problema de tinyurl y otros servicios similares
wordpress_id: 387
categories:
- Evolución
tags:
- enlaces cortos
- links
- tinyurl
---

Este post estaba en borrador, y ahora lo completé como respuesta a una pregunta de [FT via twitter](http://twitter.com/Francotirador),

> Si algún día [TinyURL](http://www.tinyurl.com/) o [Dev.cl](http://www.dev.cl/) dejan de prestar servicio... ¿mueren todas las URLs cortas creadas?

La respuesta corta es Sí.

Incidentalmente, cuando traté de acortar la url de este post dev.cl me devolvio la url http://dev.cl/.

Ahora la respuesta entretenida:

Aunque las urls cortas tienen varias aplicaciones y ventajas, incluso sirven para [comprimir imágenes](http://www.lnds.net/2006/12/wpeg_el_mejor_algoritmo_de_compresion.html) ;) la verdad es que hay varios problemas:

Jeff Atwood [resume varios de estos problemas](http://www.codinghorror.com/blog/archives/000935.html):

  * Si el servicio desaparece, las urls quedan rotas para siempre. Tal como teme FT.
  * El otro problema es la calidad del servicio, efectivamente un servicio de este tipo que funcione esporádicamente (con "apagones") puede ser una situación aún peor.
  * Se pierde la cualquier pista sobre el contenido de la url, al ser todas esta homogéneas, y estar resumidas en un codigo críptico. Esto es malo para la experiencia usuario del que está haciendo click en el enlace.
  * Hay servicios de redireccionamiento de urls que han sido usados en formas cuestionables, por ejemplo spammers (fue el caso de lnk.to).

Otros problemas que Atwood no identifica son:

  * La redirección introduce latencia.
  * No es bueno usar esto para cosas como ajax, o web services.
  * Si tu firewall o proxy reverso bloquea el servicio lo hace inutilizable
  * El servicio puede estar lleno de basura, como urls que ya no estan vigentes, al perder la pista no te enteras hasta que haces el click.
  * Si una url falla no sabes si es el servicio de compresion el que falló o si la url original la que tiene problemas.
  * Tinyurl no maneja bien algunas "urls extrañas" con caracteres como la coma (',').

A pesar de esto, las urls cortas son útiles en diversos contextos, como lo demuestra su uso en twitter, o para enviarlas en emails, o en mensajes SMS.

¿Por qué Google no provee este servicio?

Esa es una buena pregunta, y como dice Atwood, probablemente esto le daría mayor seguridad al servicio.   
A lo mejor han analizado el problema y no ven el negocio para este servicio, o no quieren complicarse con el problema de los spammers.

Aunque sospecho que no quieren ponerse en una situación tan incomodamente hegemónica.

Una alternativa sería descentralizar el servicio, una especie de P2P de urls cortas, una idea que no he explorado, pero puede ser interesante.

(Lo que sí he explorado es la idea de eliminar el DNS, pero eso quedará para otro post.)

Quizás un análisis interesante sería ver que pasa con estos servicios y el principio de que las [urls cools no cambian](http://www.w3.org/Provider/Style/URI).

En primera instancia uno pensaría que al agregar un nivel de indirección esto servicios pueden ayudar a preservar este principio, pero si observamos con mayor detención, en realidad complican más el problema.   
Efectivamente, si la url inicial cambia, además hay que propagar ese cambio a todas las urls cortas de todos los servicios de este tipo.

Ahora bien, el problema de la persistencia de las URLs es más complejo aún, y la caida de servicios tipo tinyurl es sólo una clase de los problemas asociados a la [persistencia de las URLs](http://www.w3.org/DesignIssues/PersistentDomains.html).

** ¿Cómo implementar un servicio como este? **

Ahora, para finalizar, déjenme criticar la propuesta de Atwood de usar hash como mecanismo para generar URLs cortas.

Aunque a primera vista parece bueno (algoritmo O(1)), no parece la forma más práctica para implementar este servicio. Los hashes que muestra generan strings mucho más largos que los que observamos en estos servicios.

Mejor optar por un algoritmo O(N log (N)) como el siguiente:

  1. Existe una tabla URL, indexado por ID y URL_LARGA
  2. Se recibe una url y se busca por URL_LARGA obteniendo ID o NULL.
  3. Si se obtiene NULL se inserta un nuevo elemento en la tabla y la URL corta sera la raiz del sitio mas el ID expresado en base 64.

Que nos permite generar urls bastante cortas, y es facil de implementar.   
No creo que sea fácil encontrar una función hash que genere strings más cortos que los que genera este algoritmo.

Como Tip adicional, en vez de realizar la redirección usando PHP, o Python, yo optaría por escribir un modulo apache en C, o en PERL, esto aceleraría en al menos un orden de magnitud el servicio (si es que no más). O quizás creando mi propio servidor web. Y por último, trataría de mantener la tabla en memoria, o al menos un caché de las URLs más visitadas.



