---
comments: true
date: 2012-02-24 18:45:01
layout: post
slug: seguridad-y-oportunidad
title: Seguridad y oportunidad
wordpress_id: 2567
categories:
- Seguridad
- Tecnología
tags:
- criptografía
- criterio
- desarrollo
- MD5
- tiempo
---

En 2005 [publiqué](http://it.slashdot.org/story/05/09/23/0618252/practical-exploits-of-broken-md5-algorithm) una [prueba de concepto](http://www.codeproject.com/Articles/11643/Exploiting-MD5-collisions-in-C) que mostraba lo vulnerable que es MD5 para ser usado como "firma digital", en 2007 [Peter Selinger ](http://www.mathstat.dal.ca/~selinger/md5collision/)basándose en mi trabajo crea un mecanimos para automatizar el proceso de generar firmas falsas. En [2009 comenté](http://www.lnds.net/blog/2009/01/md5-las-vulnerabilidades-siguen-ahi.html) que la vulnerabilidad seguía ahí. Y estamos en 2012 y aún MD5 está disponible y sigue siendo usado para generar claves y como mecanismo de firma electrónica. Incluso todavía sigue siendo recomendado por instituciones gubernamentales como mecanismo de verificación de integridad de archivos. De hecho hay muchos más usos de este algoritmo en distintos protocolos usados en diversos ambientes productivos en nuestro país.

Sabemos desde hace años que la firma MD5 puede ser a duplicada, técnicamente esto se llama una colisión, de modo que podemos reemplazar el archivo original por un archivo distinto y la firma se va a mantener intacta.

¿Por qué sigue usándose este algoritmo de hash, siendo que está archi demostrado que es vulnerable?

Razones hay muchas, por ejemplo, es muy dificil cambiar una normativa. Muchas veces implementar  esa modificación puede tener un costo total para  la industria altísimo, y probablemente es más sencillo implementar mecanismos alternativos, u otras capas de seguridad que permitan mitigar el riesgo. (Lo malo que en el caso chileno, muchas de esas normativas se crearon alreededor de 2008, ¡3 años después de que estas vulnerabilidades quedaran expuestas!, de  esto sólo hay que culpar al poco rigor técnico de los autores de estas normas).

¿Desaparecerá el uso de MD5 alguna vez? Es difícil saber, pero sospecho que mientras estén allí disponibles esas funciones, se seguirá usando.

En [mi post de 2009 ](http://www.lnds.net/blog/2009/01/md5-las-vulnerabilidades-siguen-ahi.html)comentaba como Ben Laurie, fundador de Apache, y miembro del core de OpenSSL, estaba considerando eliminar estas funciones de ese proyecto, pero que era muy dificil hacerlo sin romper SSL y TLS. Otra alternativa era cambiar el nombre a las funciones, para que de ese modo disminuyera su uso. Bueno, han pasado más de 3 años y no se ha hecho nada. Incluso el repositorio de openssl sigue usando MD5 como signature para sus archivos (claro que también incorporan sha-1).

En 2005 yo estaba ocupado e interesado en este tipo de problemas, después de todo mi negocio en ese tiempo tenía que ver con sistemas de verificación de identidad. Fue en ese tiempo que investigué este asunto  y contribuí en la difusión del problema. Hoy estoy dedicado a otros temas, y tengo muy poco tiempo para investigar sobre criptografía (aunque el tema es apasionante). Escribo este post porque quiero decir que entiendo la frustración de muchas personas preocupadas de la seguridad informática, que ven como sus descubrimientos no son considerados por los desarrolladores, o las instituciones.

Lo que se debe entender, en mi opinión, es que no hay desinterés por parte de los desarrolladores. El ejemplo del caso de Ben Laurie es significativo. Los desarrolladores pueden estar conscientes del problema, pero muchas veces es muy dificil, y a veces simplemente no es práctico llevar a cabo un cambio. Es probable que en 3 años más vuelva a escribir sobre esto y MD5 va a seguir vivito y coleando, a pesar de [los intentos que se han hecho por matarlo](http://www.eweek.com/c/a/Security/Microsoft-Scraps-Old-Encryption-in-New-Code/).

Hay mil factores que explican la aparente desidia ante estos temas, pero si uno se pusiera a analizar internamente, si conociera la estructura interna, o la política interna de estas organizaciones entendería que muchas veces cuesta  mover los recursos, o que hay muchas prioridades antes. Por eso es que a veces los "shocks" tienen éxito, no es que la gente de esas organizaciones no quiera arreglar los problemas, pero cuando ocurre un incidente grave, que expone públicamente la vulnerabilidad las organizaciones corren para arreglarla. Lo malo es que esa doctrina de choque estresa a la organización, pospone otros proyectos. Esa es la razón por la que no me gusta ese modo de exponer riesgos, a la larga es destructivo.

Por otro lado, las organizaciones deben invertir en educar a sus cuadros técnicos para incorporar la seguridad desde el principio en el desarrollo. En este sentido hay que explicar a la dirección de la empresa de la importancia, y del valor que tiene este tipo de soluciones. Pero debemos recordar que finalmente "money talks", si el costo del riesgo multiplicado por la probabilidad de que ocurra es baja, entonces muchas veces las empresas optarán por otro mecanismo, para utilizar los recursos en otros elementos que aporten más valor a los negocios. Lo que un desarrollador, y un asesor de seguridad deben entender son los conceptos básicos de microeconomía, siempre está **el costo de oportunidad**.

Si quiere vender seguridad, aprenda del negocio, su mensaje será mejor recibido.

Por mi parte, realmente espero que este sea el último post sobre MD5 de este blog, pero sospecho que no va a ser así.


