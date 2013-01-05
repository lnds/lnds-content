---
comments: true
date: 2006-01-19 15:10:19
layout: post
slug: influencia-popularidad-y-relevancia
title: Influencia, Popularidad y Relevancia
wordpress_id: 2040
categories:
- Emprendimiento
- Internet
- Programación
tags:
- blogmemes
- influencia
- meneame
- popularidad
- relevancia
---

He estado enfrascado en 2 problemas:



	
  * El primero es el problema de la promoción de los posts en [blogmemes ](http://web.archive.org/web/20090426080926/http://www.blogmemes.com/)hacia el tope de la cola.

	
  * El otro problema es como incentivar la participación de los usuarios.


El primer problema tiene que ver con la **Relevancia**, y el segundo problema tiene que ver con la **influencia **y la **popularidad**.

Me explico. Una historia publicada en blogmemes debe ser interesante para estar en la primera página. Pero no basta que sea interesante por si misma, blogmemes es un sistema democrático, por lo tanto lo que importa es el grado participación activa y pasiva de los usuarios con la noticia. Por lo tanto la popularidad de un artículo, no es suficiente. El concepto adecuado para ordenar las noticias en la primera página tiene que ver con la relevancia.


## relevancia


El diccionario de la [RAE ](http://web.archive.org/web/20090426080926/http://www.lnds.net/2006/01/www.rae.es)define relevancia como:


> 1. f. Cualidad o condición de relevante, importancia, significación.


y relevante se define como:


> (Del lat. relĕvans, -antis, part. act. de relevāre, levantar, alzar). 1. adj. Sobresaliente, destacado.
2. adj. Importante, significativo.


¿Cómo podemos medir lo significativo de una historia?

En us sistema tipo Digg, como Meneame o Blogmemes contamos con estas variables medibles:



	
  1. La cantidad de votos recibidos por un artículo o noticia

	
  2. La cantidad de comentarios recibidos por la misma

	
  3. La cantidad de veces que los usuarios han seguido el enlace a la historia original

	
  4. La antiguedad de la historia


Por último, yo he considerado otro factor, que es el instante en que un meme ha sido afectado por un voto, un comentario o un click en el enlace.

Por eso que el modelo de promoción de blogmemes es el siguiente:

	
  * Un meme pasa a primera página si la cantidad de votos recibidos sobrepasa un umbral. Actualmente ese umbral es 7 votos, pero puede variar en el futuro.

	
  * Una vez promovido, un meme es ordenado por su grado de relevancia.


El grado de relevancia, R, es una funcion proporcional a la suma de los votos+comentarios+clicks, pero que "decae" en función de la antiguedad de la noticia.

Actualmente tenemos que R se mide con esta formula:


> R = (1000+log(votos+comentarios+clicks+horas_promovido)* 1/(1+log(horas_publicado) * 10/(1+log(horas_promovido)) * log(Votos);


Las razones de usar el logaritmo es que es una función creciente pero con una pendiente decreciente (la derivadad de log es 1/x). Esto tiende a achatar la importancia de los votos+comeentarios+clicks+horas_promovido.
Al dividir por el logaritmo de las horas publicado y horas promovido hacemos que la historia vaya decayendo en el tiempo.
¿Por qué se multiplica por log(Votos) ? Porque ese factor resuelve el problema de los memes publicados casi al mismo tiempo, donde queremos que el que tiene mas popularidad se vea primero que el de menos popularidad.

¿Es este un buen modelo para la relevancia?

No lo sé. Es muy experimental, y algo arbitrario, pero hasta ahora parece funcionar de acuerdo a lo que necesito.
Someto el modelo a vuestra consideración.


## Popularidad e Influencia


Nuevamente, el diccionario define popularidad como:


> popularidad. (Del lat. popularĭtas, -ātis).
1. f. Aceptación y aplauso que alguien tiene en el pueblo.


y la influencia como:


> influencia. (Del lat. inflŭens, -entis, part. act. de influĕre).
1. f. Acción y efecto de influir.
2. f. Poder, valimiento, autoridad de alguien para con otra u otras personas o para intervenir en un negocio.
3. f. Persona con poder o autoridad con cuya intervención se puede obtener una ventaja, favor o beneficio. U. m. en pl.
4. f. desus. Gracia e inspiración que Dios envía interiormente a las almas.


Bien, he decidido promover estos dos atributos entre los usuarios de akarrú, o blogmemes.

Un usuario influyente es uno que logra que las historias cobren relevancia.
Un usuario popular es aquel que recibe el voto de los demás usuarios.

En estos casos los cálculos son más simples, y en el caso de la influencia, esta es proporcional a la cantidad de memes publicados multiplicado por el logaritmo de los votos y comentarios emitidos por el influenciador.
En el caso de la popularidad, es el logaritmo de la cantidad de votos recibidos menos la cantidad de historias publicadas (asumo que cada autor vota por si mismo), multiplicado por la cantidad de historias publicadas.

La influencia es más neutra en este caso porque depende del total de memes en la base de datos. En cambio la popularidad depende de la cantidad de memes publicados. Es decir, un usuario que publica mucho tiende a ser más popular.

Si asumimos que las democracias reales no son perfectas, y que efectivamente hay grupos (partidos) o personas (lideres, caudillos) que mueven a la población, entonces me pareció que blogmemes debe reflejar eso.
Por otro lado, la popularidad es importante en una democracia, que se caracteriza por el voto de la mayoría.

¿Que consecuencias tendrán estos parámetros en [blogmemes](http://web.archive.org/web/20090426080926/http://www.blogmemes.com/)?

Yo veo las siguientes consecuencias:



	
  1. Se formarán grupos de usuarios que se voten entre sí.

	
  2. Estos grupos que provocarán que las historias pasen a primera plana

	
  3. Se respetan las mayorías, y son estas las que llevan a que alguien sea popular

	
  4. Hay que ver si el incentivo de ser influyente o popular genera más participación de los usuarios.


De todas maneras quiero evitar los problemas de [Ricardo Galli](http://web.archive.org/web/20090426080926/http://mnm.uib.es/gallir/) ha tenido con meneame. El tomó decisiones de diseño que han provocado molestias. Personalmente no me gusta que uno tenga que estar obligado a votar para poder publicar una historia, y estoy de acuerdo en parte con [algunas de las críticas](http://web.archive.org/web/20090426080926/http://almadormida.blogspot.com/2006/01/consideraciones-sobre-el-uso-de.html), pero prefiero no polemizar pues el equipo de meneame es soberano en las decisiones de su proyecto.

Por ahora, blogmemes es una anarquía en busca de auto organización. Si esto resulta en algo positivo, o un paraiso para los spammers, entonces tendremos que invocar nuestros poderes divinos para establecer un estado de excepción. Pero mientras eso no pase, blogmemes [está abierto al autobombo y a la auto moderación](http://web.archive.org/web/20090426080926/http://milugar.net/actualidad/meneame-barrapunto-y-libertonia-2.html), glup.


