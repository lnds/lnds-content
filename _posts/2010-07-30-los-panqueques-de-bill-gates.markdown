---
comments: true
date: 2010-07-30 15:00:00
layout: post
slug: los-panqueques-de-bill-gates
title: Los panqueques de Bill Gates
wordpress_id: 471
categories:
- Ciencia
- Paradigmas
- Personajes
tags:
- ADN
- algoritmos
- Bill Gates
- biología
- ciencia
- evolución
---

El [problema de ordenar](http://es.wikipedia.org/wiki/Algoritmo_de_ordenamiento) es uno de los temas básicos en  la formación de todo programador. Pero quizás este  conocido problema encierre la clave para entender como funciona la evolución de la vida. ¿Cómo? Esa es una historia que involucra nada menos que Bill Gates, pero antes de contarla repasemos este clásico problema informático.

¿Cómo ordenamos una serie de datos? Esta es una tarea tán básica, que la damos casi por sentada, incluso viene incluida en nuestros lenguajes, sistemas operativos, o incorporada como función estándar en todo programa  de planillas de cálculos.

Un ejercicio que se ha vuelto popular es: ¿cuál es la manera más eficiente de ordenar un millón de enteros de 32 bits? incluso como prueba de selección. La respuesta por supuesto depende de muchos supuesto. Al menos [Barack Obama sabe que bublesort no es el mejor algoritmo](http://www.lnds.net/blog/2010/07/obama-sabe-computacion.html), pero ¿un algoritmo "eficiente", como quicksort, o heapsort son  la mejor manera de resolver este problema?

¿Cómo mides la eficiencia de un algoritmo? ¿Por el tiempo que toma ejecutar, o por la memoria que ocupa? Por eso que hay variantes de este problema, como una bastante popular que dice: ¿cómo ordenas un millón de enteros de 32bits en 2 megabyte de memoria?, pregunta con trampa, porque un millón de enteros de 32bit ocupan 4 megabytes. Aunque no lo crean, hasta los más grandes se complican con esta pregunta, como el gran Guido Van Rossum (creador de python), como pueden apreciar [en este artículo](http://neopythonic.blogspot.com/2008/10/sorting-million-32-bit-integers-in-2mb.html).


[![](http://www.lnds.net/blog/wp-content/uploads/2010/07/41ETT7KQRRL._SL160_.jpg)](http://www.amazon.com/gp/product/0201657880?ie=UTF8&tag=lanaturaledel-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0201657880)![](http://www.assoc-amazon.com/e/ir?t=lanaturaledel-20&l=as2&o=1&a=0201657880)


Otra forma clásica de este problema aparece en el primer capítulo de  ese maravilloso libro que todo desarrollador debe tener en su biblioteca: [Programming Pearls (2nd Edition)](http://www.amazon.com/gp/product/0201657880?ie=UTF8&tag=lanaturaledel-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0201657880)![](http://www.assoc-amazon.com/e/ir?t=lanaturaledel-20&l=as2&o=1&a=0201657880), escrito por Jon Bentley. Afortunadamente el artículo de Bentley se encuentra [disponible online](http://www.cs.bell-labs.com/cm/cs/pearls/cto.html), y recomiendo su lectura (pero compren el libro y guárdenlo bajo su almohada).

El problema de Bentley es ordenar un archivo de números en el rango que va de 0 a 999.999, con sólo 1 megabyte de memoria. Lo interesante del artículo de Bentley es que enseña la importancia de precisar la especificación, para llegar a una solución adecuada.  En el caso de Bentley no sólo logra una solución que funcione en un espacio reducido de memoria, sino que logra además un algoritmo eficiente O(n), usando una estructura de datos muy eficiente.

![](http://www.lnds.net/blog/wp-content/uploads/2010/07/gates-217x300.jpg)

Pero vamos a la historia sorprendente sobre ordenamiento, que involucra a un millonario, y a unos panqueques.

**Bill Gates Ordena Panqueques**

Quizás lo que no muchos de ustedes saben es que Bill Gates  hizo una contribución científica al problema de ordenamiento escribiendo un paper (el único artículo matemático conocido que lleva su nombre) describiendo el oscuro algoritmo [Pancake Sorting](http://en.wikipedia.org/wiki/Pancake_sorting), si no me creen [aquí tienen el enlace al paper ](http://www.cs.berkeley.edu/~christos/papers/Bounds%20For%20Sorting%20By%20Prefix%20Reversal.pdf)publicado en Discrete Mathematics en 1979.

La idea es ordenar una pila de panqueques de acuerdo a su tamaño, usando una espátula. Las únicas operaciones permitidas son insertar la espátula y girar los panqueques.

Para que se hagan una idea de la operación este es el dibujo que acompaña la explicación en wikipedia del algoritmo:

[![](http://www.lnds.net/blog/wp-content/uploads/2010/07/Pancake_sort_operation-150x150.png)](http://www.lnds.net/blog/wp-content/uploads/2010/07/Pancake_sort_operation.png)En la parte superior vemos como se ha insertado la espátula entre medio, y luego se gira dando vuelta los primeros tres panqueques.

El problema consiste en encontrar el algoritmo que permita ordenar los panqueques dejando los más grandes abajo y los más chicos arriba, usando la menor cantidad de operaciones (giros de la espátula).

Lo interesante es que una variación de este algoritmo, conocido como el problema de los panqueques quemados (**Burnt Pancake Problem)** fue desarrollado por uno de los creadores de futurama David X. Cohen y fue implementado en 2008 mediante un "computador" compuesto de bacterias de E. Coli, que giraban segmentos de ADN, el problema quedaba resuelto cuando las bacteria generaban resistencia a los antibioticos (¿?).

La verdad es que es complicado,  pero [aquí les dejo otro enlace](http://plus.maths.org/issue54/features/colvatter/) para cuando decidan investigar bio informática y jugar con bacterias que revuelven segmentos de ADN.


Lo importante es que el ADN evoluciona a partir de pequeñas mutaciones, en el entendimiento de estas mutaciones, los biólogos encontraron que este oscuro problema matemático puede dar luces en la forma en que la vida evoluciona mediante mutaciones.




Quien sabe, quizás un día Bill Gates pase a la historia no por ser el super empresario agresivo, sino que el descubridor accidental de un mecanismo fundamental para enteder como funciona la vida.


![](http://www.lnds.net/blog/wp-content/uploads/2010/07/chromosome-150x150.jpg)
