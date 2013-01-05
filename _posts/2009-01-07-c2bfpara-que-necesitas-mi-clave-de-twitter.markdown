---
comments: true
date: 2009-01-07 19:41:22
layout: post
slug: '%c2%bfpara-que-necesitas-mi-clave-de-twitter'
title: ¿Para qué necesitas mi clave de Twitter?
wordpress_id: 316
categories:
- Internet
- Privacidad
- Seguridad
---

Hace tiempo que quería escribir sobre este problema pero al leer [esta nota](http://www.manzanamecanica.org/2009/01/comportamiento_grupal_el_caso_de_twitterank.html) hoy en [Manzana Mecánica](http://www.manzanamecanica.org/), me decidí. Es cierto que una explicación sociológica (o [etológica](http://es.wikipedia.org/wiki/Comportamiento_animal)) del comportamiento de los usuarios es muy interesante, pero hay otros aspectos técnicos e incluso éticos que hecho de menos en casi todos [los análisis de estos casos](http://scobleizer.com/2009/01/01/twitter-spam-effective-or-idiotic/).

![twply.gif](file:///I:/documentos/blogs/lnds/La%20Naturaleza%20del%20Software%20%20Archivos%20Enero%202009_files/twply.gif)

Primero, este es un problema grave, porque estamos entrenando a los usuarios a que está bien que entreguen sus emails, claves, y listas de contactos en cualquier sitio. Esto es aprovecharse del comportamiento de manada, tal como[lo aclara muy bien Mig](http://www.manzanamecanica.org/2009/01/comportamiento_grupal_el_caso_de_twitterank.html).

Segundo, porque es inaceptable que [Twitter](http://www.twitter.com/), habiéndose dado cuenta [hace tiempo](http://code.google.com/p/twitter-api/issues/detail?id=2) del problema, aún no lo haya solucionado, y lo que es peor, ellos mismos diseñaron la solución de este problema, y ¡la tienen durmiendo desde hace más de un año!

  


La disponibilidad de [API](http://es.wikipedia.org/wiki/API)s es una de las características de muchos de los servicios de la Web 2.0 (como Twitter, o Facebook), y son los que les dan el dinamismo que las caracteriza (aparte de los beneficios de promoción viral, al crear un ecosistema de servicios relacionados).

Hay muchos servicios que usan estas APIs.

Un ejemplo local, el servicio [Bittr](http://www.bittr.org/), que permite enviar actualizaciones a Twitter usando mensajes de texto (SMS o MMS),  necesita que le entregues tus datos de login en Twitter. En este caso los desarrolladores, juran y rejuran que las claves están seguras (encriptadas y todo eso), y les creo, pero igual me gustaría saber como lo implementan, porque es un problema bastante complicado, pero muchachos, tomen nota, y repítanlo como mantra: **nunca hay que pedirle a un usuario su clave acceso a un sitio (o servicio) de terceros**.

Cada vez estamos viendo sitios que implementan esta mala práctica, y por lo tanto, siempre habrán historias de terror asociadas.

Porque este es un grave problema, conocido hace tiempo, es una mala práctica, o como algunos proponen, un antipatrón de diseño:[ The Password AntiPattern](http://adactio.com/journal/1357/).

La propuesta es la siguiente:

> aunque te cueste un jugoso contrato, debes negarte a implementar cualquier tipo de interfaz que involucre preguntare al usuario su clave de acceso a un sitio (o servicio) de terceros.

>   


La extensión de este problema es cuando se le solicita al usuario que además [entregue su lista de contactos](http://factoryjoe.com/blog/2007/12/19/public-nuisance-1-importing-your-contacts/).

  


[![yelp-friends-check-fail.png](file:///I:/documentos/blogs/lnds/La%20Naturaleza%20del%20Software%20%20Archivos%20Enero%202009_files/yelp-friends-check-fail-thumb-400x144-509.png)](http://www.lnds.net/assets_c/2009/01/yelp-friends-check-fail-509.html)

Me van a decir, "todo bien Eduardo, entendemos tu preocupación, pero igual necesitamos acceder a los datos del usuario".

La verdad es que la gente de Twitter se dió cuenta de este problema, y empezó a trabajar en una solución, y la encontraron, en conjunto con un montón de gente inteligente de Google, y otros servicios, y hace un año resolvieron este problema, se llama [OAuth](http://oauth.net/about/), pero por alguna misteriosa razón, aún no lo implementan en Twitter, y recién van a empezar a probarlo en beta en los próximos meses!

Este ya no es un problema técnico, porque ya es posible extender este tipo de servicios sin tener que pedirle jamás al usuario su información personal de login a servicios de terceros.

Yo no sé por qué Twitter [no implementa OAuth](http://helloform.com/blog/2009/01/on-twply-and-giving-out-your-twitter-password/), siendo que este proyecto nació de su propia preocupación por resolver el problema.

  


Me quedo con una reflexión que [leí por ahí](http://adactio.com/journal/1357/), "en esta nueva realidad de la web social, más que preguntarse de qué manera puedo estirar (o abusar de) esta herramienta o servicio, lo correcto es preguntarse en que medida lo que voy a hacer tiene un efecto positivo en mi mundo."



