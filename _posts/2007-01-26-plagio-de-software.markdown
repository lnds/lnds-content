---
comments: true
date: 2007-01-26 20:28:45
layout: post
slug: plagio-de-software
title: Plagio de Software
wordpress_id: 1785
categories:
- Desarrollo
- Emprendimiento
- La Naturaleza del Software
tags:
- complejidad
- copia
- plagio
- replica
- software
---

Leo en un conocido blog el siguiente párrafo:


> "Cuando un programador escribe un bloque de código está creando una receta para conseguir un resultado concreto. Hay un número limitado de caminos para llegar al mismo sitio, algunos más rápidos y elegantes que otros. Dicen que el código perfecto es aquel al que no se le puede añadir ni quitar nada. Si consideramos la naturaleza misma de los lenguajes de programación, cuanto más perfecto sea ese código, más posiblidades hay de que otro programador con el mismo propósito y el mismo talento llegue a la misma conclusión. Esto no se considera un robo, salvo que la longitud de la coincidencia sea estadísticamente inverosímil. En la literatura y en el arte, ese tipo de coincidencia es prácticamente imposible. Puede que un mono inmortal tecleando infinitamente una máquina de escribir acabe firmando un HAmlet pero, de momento, no se sabe de ningún escritor que tenga tanto tiempo. "1


El texto citado es parte de un artículo muy interesante, sobre el cual poco puedo opinar, pues el plagio literario no es algo que domine, ni que me interese particularmente. Pero las afirmaciones de este párrafo en particular sí me interesan, porque vale la pena analizar su validez, y porque desde un punto de vista profesional me parece interesante saber qué es el plagio de un programa computacional.

[1] [Tomado de La Petite Claudine](http://www.lapetiteclaudine.com/archives/010582.html)


## Los autores de Hamlet


Uno de los problemas del infinito es que es un concepto muy difícil. Sabemos que Shakespeare escribió Hamlet, pero la afirmación de que un "mono inmortal tecleando infinitamente una máquina de escribir acabe firmando Hamlet " también es cierta.

O sea, desde un punto de vista lógico, Hamlet tiene más de 1 autor, de hecho tiene infinitos autores, basta con pensar en infinitas realidades alternas, necesariamente en una de estas yo tengo que ser el autor de Hamlet, y en otra **tú **eres autor de Hamlet.

Aunque esto es lógico, no necesariamente es cierto, porque sabemos que el tiempo tiene un principio, y por lo tanto la eternidad como tal no es tal. No voy a entrar a filosofar sobre la naturaleza del tiempo, pero baste con saber que la física, tal como es conocida hasta ahora, nos dice que el mono no tiene infinito tiempo para escribir las obras de Shakespeare.

Sin embargo, hay que tener cuidado con la interpretación de esta afirmación, lo que se nos quiere decir es que si el mono tuviera infinito tiempo, entonces la probabilidad de que termine escribiendo Hamlet es 1 (o del 100%). Pero si ponemos realmente un mono a escribir frente a un teclado, la probabilidad de que escriba Hamlet es muy baja, pero hasta donde sé, no es cero, por lo tanto es algo que sí puede pasar. Desde un punto de vista probabilístico, dos autores pueden terminar escribiendo el mismo poema, lo que pasa es que desde un punto de vista estadístico eso no se ha dado.


## La copia funcional


La otra afirmación, más interesante, es la que dice que si un programa es como una receta, entonces dos programadores pueden llegar a soluciones similares, pero a la larga, en la medida que se _perfeccione el programa_, el resultado debe ser único.

Esa afirmación es falsa. Si bien puede ser cierta a nivel funcional, no es cierta a nivel de la implementación. Tomemos como ejemplo [Meneame ](http://www.meneame.net/)y mi proyecto [BlogMemes](http://www.blogmemes.com/). Ambos son similares, pero Menéame tiene muchas más funciones, y Blogmemes es un proyecto incompleto aún.

Sin embargo, si quisiera, podría reproducir toda la funcionalidad de Menéame sin repetir el código de sus autores. Es cosa curiosa que ambos proyectos [nacieran en las mismas fechas](http://www.lnds.net/2006/02/blogmemes_y_meneame_dos_sistemas_distint.html).

Supongamos que se me ocurriera copiar la funcionalidad de Menéame, es totalmente factible, puede tomar tiempo, y puede que los desempeños de ambos sistemas sean distintos, pero lo interesante es que sí se puede escribir código que replique exactamente el comportamiento observable.

Sin embargo, si copiara los gráficos, y el estilo, eso sería considerado sin lugar a dudas un plagio (y la verdad que [no me gustaría agarrarme de nuevo con Galli](http://mnm.uib.es/gallir/)) pero, si copiara la funcionalidad, ¿que pasaría?

Hay muchos casos de este tipo, por ejemplo el [famoso caso Lotus vs Borland](http://digital-law-online.info/cases/30PQ2D1081.htm). La corte suprema estableció que Borland había desarrollado un método de operación que no es posible de proteger con copyright. Eso es interesante, y probablemente sea la causa por la que nadie dice nada porque hayamos tantos clonadores de la interfaz de [digg](http://www.digg.com/).


## El programa perfecto


La tercera afirmación interesante es:


> "Dicen que el código perfecto es aquel al que no se le puede añadir ni quitar nada. Si consideramos la naturaleza misma de los lenguajes de programación, cuanto más perfecto sea ese código, más posiblidades hay de que otro programador con el mismo propósito y el mismo talento llegue a la misma conclusión"


**¿Qué significa encontrar el código perfecto?**

En realidad depende de los criterios que pongamos. Para algunos el código perfecto sería el más compacto. Para otros el más eficiente en uso de tiempo y espacio de ejecución. Lo interesante es que para un programa podemos medir si el el programa es correcto, si es eficiente, y si es compacto. Pero parafraseando a [Donald Knuth](http://www.lnds.net/2006/09/knuth_responde_a_todas_las_preguntas.html), "podemos demostrar que un programa es correcto, pero no de que está libre de errores".

Así que un tercer criterio sería que el programa esté libre de errores.

El programa perfecto sería aquel que cumple las especificaciones funcionales, es eficiente en la ejecución, en tiempo y espacio, y es compacto.

Sin embargo, y para terminar este post, hay un resultado paradójico que hace que probablemente la búsqueda del programa perfecto sea imposible, a menos que, como el mono, tengamos infinito tiempo a nuestra disposición.

En la teoría algorítmica de la información existe una función llamada la [complejidad de Kolmogorov](http://en.wikipedia.org/wiki/Kolmogorov_complexity): K.

Supongamos que el resultado de la ejecución del "programa perfecto" P que recibe como entrada una cadena de bits E, es la cadena de bits S, es decir, P(E) = S. Entonces la complejidad de Kolmogorov de la cadena S, denotada como K(S) es igual al tamaño del programa más compacto que arroje como resultado S, es decir K(S) = |P(E)|, donde las barras denotan el tamaño del programa.

Uno de los resultados de la teoría algorítmica de la información es que la función K(S) **no es computable**. Esto en términos generales, implica que no hay un atajo para encontrar el programa más compacto para resolver un problema.

No hay una manera automática de calcular el programa más compacto, de hecho demostrar que un programa es el más compacto puede ser una tarea formidable, y poco práctica.

El ingeniero resuelve un problema, corrige los errores y optimiza el código, usando "mediciones en terreno", y rara vez se preocupa de si ha construido el programa perfecto, sólo el más eficaz y que tenga la mínima cantidad de errores posibles. No tenemos tiempo para la perfección.

