---
comments: true
date: 2008-02-25 21:03:15
layout: post
slug: '%c2%bfjava-o-net'
title: ¿Java o .Net?
wordpress_id: 48
categories:
- Desarrollo
- Programación
---

Hace casi un año atrás tuve que revisar un desarrollo que hice durante el año 2002, para una empresa en la que trabajé hace unos 4 años atrás, era un pituto interesante ($$$) pero tenía poco tiempo para hacerlo, así que tuve que tomar algunas decisiones que resumí en una respuesta en una lista de discusión privada.

Decidí compartir esa respuesta con ustedes, remozarla un poco, y aprovechar con este post de partir, después de vacaciones, además de aprovechar para responder [una pregunta](http://www.antiteoricos.cl/2008/02/17/%c2%bfjava-o-net/) planteada en [antiteóricos](http://www.antiteoricos.cl/).

El año pasado, cuando me ofrecieron este trabajo (pituto), yo ya llevaba 3 años trabajando casi totalmente en .Net, y me pedían que retocara un proyecto abandonado a principios del 2003, escrito totalmente en java.

La aplicación en cuestión corresponde a una plataforma de juegos y aplicaciones para SMS (mensajes cortos por celular), construida en [Java J2EE](http://java.sun.com/javaee/), con varios **archivos** XML de configuración (varios mapeos de Hibernate), unas 3000 lineas sólo en la interfaz de usuario que hice en java con [Hibernate](http://www.hibernate.org/), otras 3000 lineas en código java, que correspondían a los beans que enceraban la lógica de negocios. Todo montado sobre [RESIN](http://www.caucho.com/) que corresponde al servidor de aplicaciones usado para soportar esta aplicación. (En ese tiempo parecía una buena idea, y la plataforma ha operado durante 5 años con este servidor sin problemas).

Como tenía que meterme a modificar muchas cosas para agregar lo que me pedían, y tenía muy poco tiempo para hacerlo, decidí que todo lo nuevo lo construiría en [Python](http://www.python.org/) usando [DJANGO](http://www.django-project.com/) como framework, esta decisión implicaba escribir un pequeño servlet para enganchar lo que había con la nueva interfaz de usuario.

Era más corto escribir código nuevo en python y escribir un pequeño servlet de pasarela, que escribir lo equivalente en java, en parte porque tenía que recordar muchas cosas, bucear algunas partes no documentadas del código (documentación? nunca me pidieron documentación), y no tenía ganas de escribir java (lenguaje que no me gusta mucho en realidad).

Todo el trabajo me tomó el equivalente a 3 fines de semana, reemplacé varias partes de lo que estaba en java, y al terminar la plataforma terminó con un 30% de su código en python.

La verdad es que quedé con las ganas de tirar todo lo que estaba en java y migrarlo a python, algo que probablemente emprenda cuando haya tiempo y mi cliente decida financiarlo.

Pero vamos a enumerar algunas observaciones de esta experiencia.

  * Desempeño, aunque java es más rápido, con django + python obtengo mucho más de lo que se necesita para esta aplicacion. Midiendo, noté que si con java y resin podía atender 120 request por segund (rps), con python+django obtuve 80 rps, pero la verdad es que necesito cubrir no más de 40 rps (que es lo que tenemos comprometidos con los operadores de telefonía celular).
  * El cuello de botella está en la base de datos (como siempre).
  * El codigo en python es considerablemente menos. En parte porque no tuve que crear mantenedores para administrar varias de las nuevas entidades que definí, simplemente usé el administrador estándar incluido en Django.
  * Puedo hacer cosas en runtime de forma mucho mas simple que con java, por ejemplo, para implementar cierta funcionalidad que me pidieron habría tenido que usar reflection, o algo parecido (algo que en mi opinión es más fácil de hacer en .Net) pero con python salió natural.
  * Con python pude meter "logica de negocios" dentro de un campo TEXT en la BD, un recurso que use para poder hacer cambios en linea sobre el servidor de produccion, por ejemplo, el operador puede cambiar el flujo de un juego para ajustarse a los requerimientos del usuario, antes eso significaba modificar o crear un servlet específico.
  * doctest es una herramienta extraordinaria. Estoy usando java 1.4, así que no podría usar las nuevas caracteristicas de junit (anotaciones), pero doctest de python es muy superior.
  * El ORM de Django es superior a Hibernate desde el punto de vista de la programación.
  * La prueba de fuego estuvo en un concurso por TV, en un momento la plataforma recibió unos 9.000 mensajes en 15 minutos, 6.000 fueron procesados completamente en python, y 3.000 pasaron por un servlet java que los pasaba a un backend en python. Cero problemas.

Ahora hay más recursos disponibles para hacer desarrollo rápido en Java, y SEAM por ejemplo, es un excelente framework para montar algo como lo que describo, pero no tenía tiempo para aprender SEAM, ni menos para reconfigurar el ambiente de producción para usar Java 1.5, cambiarme a JBoss, y otras cosas.

Por eso cuando me preguntan, ¿qué es mejor para desarrollar un nuevo proyecto, Java o .Net?, habiendo programado en ambas plataformas, con sistemas similares mi respuesta es: si vas a partir de cero, prueba hacerlo todo en Python.

Funciona muy bien con aplicaciones de verdad, como la descrita en este post.

Conclusiones

Al final, lo que importa son las decisiones de arquitectura, y el lenguaje de programación no es tan importante.

¿Si te piden 40 rps, y eres capaz de dar 80 rps, para que buscar los 120 rps?   
Hay veces que optimizar demasiado es innecesario.

Hay que balancear las restricciones de tu proyecto: presupuesto, tiempo, calidad y/o falta de documentación.

En mi caso el tiempo disponible era el principal factor, a mi cliente le daba lo mismo en que plataforma esté montado todo, lo que importa es la calidad del servicio. Eso me dió libertad, pero también tuve esa libertad porque confiaba en las herramientas que escogí, esta podría haber sido la oportunidad de usar Ruby On Rails, por ejemplo, o PHP, pero el primero no lo conocía, y en el segundo no confío tanto.



