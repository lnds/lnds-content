---
comments: true
date: 2006-02-01 12:29:34
layout: post
slug: blogmemes-y-meneame-dos-sistemas-distintos
title: blogmemes y meneame, dos sistemas distintos
wordpress_id: 2066
categories:
- Emprendimiento
tags:
- blogmemes
---

Un nuevo release de [akarru ](http://web.archive.org/web/20080426225126/http://sourceforge.net/projects/akarru/)ha sido liberado hoy.
Hay muchos errores corregidos.

Sin embargo, quienes visiten [blogmemes ](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/)verán que tenemos nuevas características que no están en este release de akarrú. Lo que pasa es que las nuevas características tienen que ver con FeedBurner, y están muy amarradas a los datos de blogmemes. Vamos a dejar ese soporte más genérico para incorporarlo después.


## Un poco de historia de Blogmemes


Uno puede leer [la historia de Meneame](http://web.archive.org/web/20080426225126/http://mnm.uib.es/gallir/posts/category/meneame/page/3/) en el blog de Ricardo Galli, y es super interesante, pues nos ha dejado documentado su proceso.
Para mi es interesante, porque no conocía a Ricardo, y no sabía de su proyecto cuando el lo estaba programando.

Lo interesante es que blogmemes publicó su [primera nota ](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/comment.php?meme_id=1)el 07/12/2005 a las 09:49 EST (tiempo del este de USA, donde está el servidor), y Meneame publicó su [primera noticia ](http://web.archive.org/web/20080426225126/http://meneame.net/story.php?id=1)más o menos al mismo tiempo.

Algunos han comentado que partimos después o [que llegamos tarde,](http://web.archive.org/web/20080426225126/http://www.cyberlatam.com/news/2006/01/blogmemes-otro-mas-y-sumando.html) cuando la verdad podrían decir que somos gemelos. De hecho, la primera mención a Blogmemes [en Ñblog ](http://web.archive.org/web/20080426225126/http://utilidades.bitacoras.com/archivos/2006/01/08/blog-memes-otro-clon-de-digg-en-espanol)fue el 8 de enero, un mes después de partir.


## Comparando las engines


Hay que decir que meneame partió con su propio código, y nosotros usamos DiggClone, el cual dejamos atrás, pero que lamentablemente provocó una serie de problemas debido a que decidimos (erroneamente en restrospectiva) mantener su modelo de datos. Eso ha llevado a tener que hacer una serie de parches y cosas bastantes feas para mantener un desempeño razonable. En ese sentido, meneame es una mejor engine que akarrú, pues tiene un desempeño mejor al tener un mejor modelamiento de datos.

Sin embargo, creo que desde el punto de vista del diseño gráfico, el uso de Smarty le da más flexibilidad a akarrú, pues cambiar las plantillas es sencillo, y lo será aún más cuando mejoremos el mecanismo de configuración. Esto permite separar la presentación del código, cosa que no veo tan fácil con meneame. De hecho, cuando configuré la v[ersión portuguesa de blogmemes la ](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/portugues)instalación fue sencilla, y la traducción la realizó[ Jorge de Sá Peliteiro](http://web.archive.org/web/20080426225126/http://www.blogger.com/profile/1497567), un usuario que no sabe nada de informática, y que sólo cambió los textos en los archivos conf, y en algunos templates (aún faltan algunas traducciones, pero ha sido por [razones de fuerza mayor](http://web.archive.org/web/20080426225126/http://www.lnds.net/2006/01/accidente.html)).


## Blogmemes y la blogosfera


Han habido [menciones interesantes a blogmemes ](http://web.archive.org/web/20080426225126/http://www.technorati.com/search/www.blogmemes.com)en la blogosfera, y mucho he leido sobre el fenomeno de los clones digg.
Pero quien se ha vuelto un experto en el tema es [bonhamled](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/profile.php?user_name=bonhamled), quien desde su blog [Recuerdos del día de mañana](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/Recuerdos%20del%20d%EDa%20de%20ma%F1ana) ha seguido el fenómeno y ha aportado interesantes descubrimientos.


## Divergencia


Pero blogmemes, que partió emulando a digg empezará a evolucionar en una dirección bastante distinta.
Nos apoyaremos en hombros de gigantes, para empezar a realizar cosas interesantes, uno de los primeros resultados es el concepto de Circulación. Gracias a FeedBurner podemos explorar que pasa con las noticias publicadas en blogmemes. Como circulan por la blogosfera, y como eso impacta en visitas a los sitios de los corresponsales de blogmemes.

Blogmemes se volverá una herramienta de exploración de la blogosfera. El núcleo de blogmemes seguirá siendo el mismo, pero innovaremos en otras vías gracias al uso de las muchas APIs disponibles para explorar la blogosfera.


## Autobombo, Spam y otras yerbas


Filosóficamente soy un amante de la libertad absoluta, para mi es el más alto valor que guía toda la ética de los seres humanos. En blogmemes confiaremos en la [sabiduría de la comunidad](http://web.archive.org/web/20080426225126/http://www.lnds.net/2006/01/una_entrevista_con_el_fundador_de_diggco.html), aunque esto cueste caro.

En blogmemes no hay restricción para publicar, tampoco nadie vota en contra de una noticia. No es obligatorio poner un url para publicar, basta el título y el texto. En ese sentido blogmemes es como un gran blog comunitario, con la diferencia que los usuarios votan por las entradas que les gustan.

Nótese, que la votación es en positivo, como en la democracia, votas por tu favorito, pero no votas en contra de las entradas que no te gustan. Tampoco las informas (me molestan los informantes) las notas que son basura, o autobombo, o cualquier otro calificativo. Eso no es necesario, y es un comportamiento que no está en las democracias, y sólo se observa cuando se instauran democracias vigiladas, dictaduras, o estados policiales, en donde los ciudadanos actúan como soplones.

Como a mí no me gustan los soplones, no hay un mecanismo para informar de estos supuestos problemas en blogmemes. Blogmemes tiene un modelo democrático, hoy muchos critican la democracia, y ponen como ejemplos la elección de Evo Morales, o de Hamas. Pero de eso se trata la democracia. Que el pueblo decida, aunque no nos guste quienes salen elegidos.

Yo creo que si alguien quiere hacer autobombo, que lo haga, de hecho he dejado una [categoría para quienes quieran hacer autobombo](http://web.archive.org/web/20080426225126/http://www.blogmemes.com/show_cat.php?cat_id=47).

Newton nos enseña que toda acción genera una reacción de la misma intensidad pero en sentido contrario. Si ponemos barreras al autobombo, la masa encontrará el mecanismo de burlar el sistema.
En lo personal estoy de acuerdo con las [críticas ](http://web.archive.org/web/20080426225126/http://almadormida.blogspot.com/2006/01/consideraciones-sobre-el-uso-de.html)a la obligación de tener que votar obligadamente en meneame, más que nada por que me da lata ser obligado a hacer algo.

En blogmemes no hay karma, pero tenemos un mecanismo de ranking de los usuarios por influencia y popularidad. La influencia tiene que ver con como vota la persona, y como participa, con comentarios. La popularidad tiene que ver con como la gente vota una nota, es decir, como esta es evaluada por los pares.

Pero el tener una alta popularidad, o influencia no te da más poderes sobre el resto, sólo te destaca, y yo quiero destacar a aquellos que hacen que blogmemes se convierta en un sitio interesante de leer y visitar.

Con la incorporación de la circulación, podremos afinar más este ranking, porque incorporaremos cómo es percibida cada noticia fuera del ámbito del sitio.

No creo que sea necesario poner mecanismos para filtrar las historias ni a las personas, el sistema debería auto regularse. Yo creo que al colocar mecanismos como un clasificador de noticias, la obligación de votar, y el karma, se logra el efecto contrario. Sería interesante saber que pasaría si meneame quitara todas las cortapisas. ¿Se llegaría a un equilibrio?

Yo creo que sí, el sistema encontrará su punto de equilibrio.

A lo mejor confío mucho en la gente, debe ser [porque soy estúpido](http://web.archive.org/web/20080426225126/http://mnm.uib.es/gallir/posts/2006/01/28/610/) ;)


