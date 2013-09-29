---
comments: true
date: 2005-12-05 10:12:47
layout: post
slug: el-paradigma-de-las-aplicaciones-web
title: El paradigma de las aplicaciones web
wordpress_id: 1498
categories:
- Sin categoría
---

La idea de que se sólo se deben construir aplicaciones web, y de que esta es la forma moderna de resolver todas las necesidades de las empresas está provocando más problemas que soluciones. Es un paradigma que uno debe tratar de evitar.

He visto aplicaciones de ingreso de formularios con 100 campos para llenar, con dos o tres pestañas que apuntan a páginas con más campos. Después de digitar penosamente estos formularios, los usuarios presionan el botón submit y sus requerimientos quedan en el [Limbo](http://www.lnds.net/2005/12/dante_se_equivocaba_el_limbo_no_existe.html), o donde sea que se vayan ahora.

¿Por qué pasa esto?


## SmartClients


Hay ciertos mitos que han sido destacados en un interesante artículo por Paul Ballard, en su articulo [No Rob, Dumb Terminals are a Dumb Idea](http://weblogs.asp.net/paulballard/archive/2005/12/05/432323.aspx). En ese artículo Paul Ballard le responde a su colega Rob Howard q[quien escribe en contra de los llamados smart clients](http://weblogs.asp.net/rhoward/archive/2005/11/03/429355.aspx), en favor del uso dumb terminals (browsers) y aplicaciones web, usando Ajax como soporte para aumentar la riqueza de la experiencia de usuario.

Los [smartclients ](http://msdn.microsoft.com/smartclient/)son una tecnología introducida por Microsoft recientemente, esencialmente son aplicaciones escritas sobre .Net que son distribuidas a través de la red. Estas aplicaciones pueden trabajar offline, y realizar actualizaciones sobre los servidores en forma posterior, es un concepto similar a las [aplicaciones tropicalmente tolerantes](http://www.lnds.net/2005/11/tropicalmente_tolerante.html), pero más sofisticadas, y mejor "marketeadas". :)


## Mitos de las aplicaciones web


Sin embargo, olvidemonos de esa tecnología en particular y pensemos que estamos comparando aplicaciones tradicionales, escritas para operar en un sistema de ventanas, como windows, KDE, Gnome, OSX o cualquiera por el estilo, versus aplicaciones AJAX o aplicaciones web puras.

El problema es que hay una de mitos que Paul Ballard destaca muy bien, y de los cuales voy a mencionar los más relevantes, sobre todo para la realidad chilena o latino americana.


### Mito 1: Las aplicaciones web son más fáciles de construir


"¿Son más fáciles? ¿ con respecto a qué?"

Consideremos la cantidad de tecnologías que se deben dominar, no basta con el lenguaje de programación (java, visual basic, o c#). Para crear una página web medianamente útil hay que conocer de HTML, DOM, CSS,Javscript, controles en el cliente, controles en el servidor, ASP.NET o JSF, PostBacks, validaciones en el cliente, validaciones en el servidor, XML, XSLT, y las cosas empeoran si hay que integrar algún applet java o activex, o peor, flash.

Muchas aplicaciones no siguen el esquema simple de request-response. El gran problema es que las aplicaciones web no mantienen estado, entonces hay que inventar tecnicas para mantener el estado de la aplicación, sesiones, variables de sesión, cookies, viewstate, application caching, etc, etc.

Otro gran problema es probar el funcionamiento en diversos browsers, incluso en versiones distintas de los mismos. Ajustar fonts, tamaño de las páginas y un largo etc. Al final muchos optan (optamos) por probar en los browsers más populares y sólo para versiones actualizadas. Lo que nos lleva al segundo mito


### Es más fácil distribuir aplicaciones web.


El típico ejemplo es la aplicación que debe ser distribuida en 1.000 escritorios. Se supone que si la aplicación está basada en web, entonces la distribución es tan simple como publicar una nueva url.

El problema está en que antes hay que tener los 1.000 escritorios preconfigurados con el browser apropiado. De acuerdo al punto anterior, si decides que tu aplicación operará sólo con IE, o con Firefox, tienes que asegurarte que los 1.000 escritorios se mantengan en ese estado. Pero lo más probable, es que tengas que forzar tus políticas de operación y congelar el estado de los PCs. Sin embargo actualizar los browsers es una necesidad del día a día, por las vulnerabilidades de seguridad que se descubren todo los días. Se produce una situación en que el equipo de sistemas está preocupado de que los browsers estén al día para evitar la propagación de virus, y el equipo de desarrollo no quiere que los browsers cambien para no tener que depurar sus aplicaciones en la nueva versión del browser.

¿No es mejor pedirles a los usuarios que descarguen el instalador de la última versión del programa?

Lo malo con las aplicaciones web, es que la publicación de las aplicaciones es todo o nada, si publicas la aplicación, las 1.000 estaciones estarán usándola al segundo después, eso se ve bien, pero ¿ qué pasa si hay un bug en la aplicación? este afectará a los 1.000 usuarios en forma instantánea. Con el esquema tradicional, tu puedes hacer una distribución más controlada de tu software, quizás a un grupo más reducido de usuarios, por ejemplo 10 escritorios. Este grupo puede probar la aplicación en producción y una vez que los errores han sido corregidos publicas la aplicación para que los demás usuarios puedan descargarla e instalarla.

Con todo, las aplicaciones web obligan a tener una infraestructura central costosa, que debe mantenerse permanentemente actualizada para poder soportar las demandas de la organización.


### No todo puede ser web


Hay aplicaciones que por su naturaleza no deben ser construidas como aplicaciones web, el mejor ejemplo son las aplicaciones de atención de clientes en el front end. Imaginen que se usaran web browsers en el frente de cajas de una gran tienda. Probablemente la cola sería 4 o más veces más larga de lo que es hoy. Los sistemas transaccionales de una caja son rápidos porque las pantallas no cambian, y los mensajes entre el servidor y el cliente son cortos, es muy raro que excedan un kilo byte de información.

Una simple página puede significar descargas de 40 kilo bytes, o más. Incluso las validaciones y la usabilidad de una aplicación puede verse afectada si el browser no descarga los scripts de validación correctamente.


## Es bueno el cilantro, pero no tanto


Un blog, una tienda virtual, un servidor de búsqueda como google, tienen infraestructuras distintas de acuerdo a las necesidades de cada uno. Por ejemplo, se pueden tener cientos de blogs instalados en un servidor de bajo costo, no así un buscador como google, donde una granja de servidores soporta este servicio.

Si alguién no puede cargar una de las páginas de este blog no es crítico. Pero cuando uno está cobrando un cheque, que falle la aplicación es una molestia enorme. Ningún arquitecto de software serio plantearía que los frentes de caja fueran construidos por aplicaciones web.

Pero en ese espacio intermedio entre las aplicaciones corporativas, las decisiones no son tan obvias.

Pienso que el mejor criterio es el siguiente:

- ¿ Es la aplicación crítica? ¿Afecta a la operación de la empresa, a tal punto que un par de minutos sin sistema provoca pérdidas (de cualquier tipo, imagen, dinero, calidad de atención)? Mida esa pérdida probable, y considere que una aplicación web es más propensa a fallas que una aplicación que puede trabajar off line si es necesario.
Dentro de la organización usar aplicaciones web no siempre es lo mejor, quizás algunos servicios, cómo la intranet, o una base de conocimientos.

Por supuesto, si tu servicio será público, entonces hay que implementarla como aplicación web, pero considera que debes preocuparte de la usabilidad, de la compatibilidad de browsers, del tiempo de respuesta, etc. Eso implica tener una buena infraestructura de servidores, y un buen nivel de pruebas de carga y de usabilidad en diversos ambientes.

Si programas una aplicación web pública, por favor, no asumas que todo el mundo usará Internet Explorer 6.0+, no sólo es una falta de respeto, sino que muestra lo poco profesional que eres para desarrollar aplicaciones web (lo mismo aplica para el que desarrolla sólo para Firefox).
