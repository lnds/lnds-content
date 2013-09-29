---
comments: true
date: 2009-09-28 20:34:57
layout: post
slug: el-problema-de-paralelizar-3
title: El problema de paralelizar 3
wordpress_id: 206
categories:
- Paradigmas
- Personajes
- Programación
- Tecnología
tags:
- Amdahl
- FUD
- Gustafson
- multi core
- paralelización
- problemas
---

Aunque mucha gente cita el acrónimo [FUD](http://www.catb.org/~esr/jargon/html/F/FUD.html), no muchos saben que fue[ Gene Amdahl](http://www.lnds.net/2009/09/el-problema-de-paralelizar.html) el que inventó este famoso acrónimo:

> "FUD is the fear, uncertainty, and doubt that IBM sales people instill in the minds of potential customers who might be considering Amdahl products."
> 
> "FUD es el temor (fear), incerteza (uncertainty) y duda (doubt) que la gente de ventas de IBM instalará en las mentes de los clientes potenciales que consideren los productos Amdahl.".
> 
>   


En 1975 Gene Amdahl inventó el acrónimo para referirse a las prácticas de IBM que trataban de impedir el éxito de Amdahl Corporation, la empresa creada por él cuyo producto eran los computadores compatibles con IBM. Una maniobra coercitiva para impedir la fuga de los clientes a la competencia.

Actualmente el término FUD es usado para referirse a cualquier táctica que use la desinformación como arma competitiva.

Estas son las cosas anexas que me gusta encontrar cuando investigo sobre un tema.

Curiosamente hay un poquito de desinformación e incerteza está asociada a la Ley de Amdahl (en otro sentido, por cierto).

Primero, Amdahl nunca fomuló una ley, de hecho el no sabía que la llamaban así, y se enteró bastante después de su paper. (Si a alguien le interesa puede descargar su paper de 1967 desde  [acá](http://www.lnds.net/documentos/5_amdahl.pdf)).

Segundo, en su paper el no escribe la fórmula que expresamos anteriormente, eso fue introducido por comentaristas posteriores a su trabajo.

Tercero, al observar sus datos Amdahl observa que la curva estadística que se ajusta es que el desempeño es proporcional a la raiz cuadrada del costo, y cita la Ley de Grosch de 1965:

> "El desempeño de un computadore incrementa con el cuadrado del costo. Si un computador A cuesta el doble de un computador B, debería esperarse que el computador A fuera cuatro veces más rápido que el computador B."

  


Hoy en día la Ley de Grosch se considera una evidencia histórica de las percepciones equivocada que ha tenido la ciencia de la computación (curiosamente la Ley de Moore fue formulada ese mismo año).

Finalmente, Amdahl escribió su trabajo como parte de una disputa que tenía con Daniel Slotnick, académico de la Universidad de Illinois y arquitecto del polémico super computador [ILLIAC IV](http://en.wikipedia.org/wiki/ILLIAC_IV) (una historia que merece ser contada en otra oportunidad)

![ILLIAC_4.jpg](/images/ILLIAC_4.jpg)

  


**La polémica**

A principio de los 1960s el diseño de los computadores estaba enfrentando el límite de los rendimientos decrecientes. En ese tiempo la idea era dotar a las CPU de tantas instrucciones como fuera posible, para hacer programas lo más pequeños y eficientes en el uso de memoria. Esto, por supuesto, generaba computadores muy complejos, sobretodo en una era en que las CPUs se construían soldando transitores individuales a mano.

Una solución para problema, que se empezó a explorar en aquel tiempo, fue la sobreposición, que derivó en lo que conocemos actualmente como [instruction pipelining](http://en.wikipedia.org/wiki/Instruction_pipeline), que permite que una CPU trabaje en pequeñas partes de varias instrucciones al mismo tiempo.

La otra solución al problema era la computación paralela: constuir un computador a partir de un número de CPUs de propósito general. La idea es que el computador se encargue de mantener ocpupadas a todas las CPUs, pidiéndole a cada una que trabaje en una pequeña parte del problema y después recolectando los resultados en la respuesta final.

Este era el contexto en que Amdahl escribe su artículo, tras una discusión con Slotnick sobre el futuro de las arquitecturas de computadores.

Es por eso que no hay que ver la Ley de Amdahl como una visión pesimista, o un intento de frenar el procesamiento masivo.

En 1996 [Yuan Shi demostró](http://www.cis.temple.edu/~shi/docs/amdahl/amdahl.html) que la Ley de Amdahl y la Ley de Gustafson son la misma y que la confusión se debe a un problema de formulación. De hecho hay un pre requisito muy importante para aplicar la Ley de Amdahl (o de Gustafson), y es que los programas seriales y paralelos tomen la misma cantidad de pasos de cálculo para una misma entrada.

Hay tres posibles relaciones entre la mejora de velocidad (speedup) y la cantidad de procesadores P:

  * **_Speedup < P_**, o mejora sublineal;
  * **_Speedup = P_**, o mejora lineal;
  * **_Speedup > P_**,  o mejora super lineal.

Dado que cualquier programa parelelo práctico debe consolidar la respuesta final en un paso serial, el porcentaje serial en la ley de Amdahl nunca es cero en la práctica. Luego, en teoría no es posible alcanzar speedups lineales o super lineales.

Pero, Yuan Shi descubrió que es posible saltarse algunas de las pre condiciones de la ley de Amdahl, y se pueden alcanzar mejoras lineales o super lineales si se arma un algoritmo inteligentemente.

De hecho propone una clase de algoritmos que se pueden alterar para conseguir velocidades superlineales. Un resultado interesante es que un algoritmo de ordenamiento (sort) de O(n2) puede ser paralelizado de forma tal que tenga una mejora super lineal (rompiendo la Ley de Amdahl), mientras que no es posible hacer esto con un algoritmo de sort de O(n lg n).

Lo que pasa es que al paralelizar ciertos algoritmos podemos alterar su estructura, de modo que para ciertos datos de entrada su desempeño será mejor que la versión serial del mismo. No voy a entrar en detalles, pueden [leerlo en el paper](http://www.cis.temple.edu/~shi/docs/amdahl/amdahl.html).

Lo importante es notar que la Ley de Amdahl no puede ser usada como un argumento en contra de la paralelización masiva, porque, aunque hay un límite, y en general el desempeño es sub lineal, hay muchos problemas en que la parte serial es muy pequeña y la mejora es considerable. Los experimentos de Gustafson son una demostración de esto.

Empecé mi investigación sobre este tema inspirado por una nota en la edición de **septiembre** de [CACM](http://cacm.acm.org/). En esta nota se cita a un investigador de Intel, Tim Mattson que nos urge a programar en paralelo: "Hemos llegado a la programación en paralelo no por causa del éxito de nuestro software, sino por la falla de nuestro hardware." En esa misma nota  James Larus, investigador de Microsoft quien pide cautela cuando abordemos este tema, "la consecuencia de tener que moverse a multicore es que tenemos que imaginarnos como usar paralelismo en lugares donde necesitamos un mejor desempeño... No todo necesita ser paralelizado, ¿acaso eso hará que Word funcione más rápido?"

Y es Larus el que nos recuerda la Ley de Amdahl, porque habrá mucha presión por paralelizar aplicaciones y muchos de esos esfuerzos pueden estar mal dirigidos.

En el lado de los servidores (y del cloud computing), la paralelización funciona bastante bien, porque la clase de problemas que se pueden resolver en ese lado son paralelizables en forma casi natural. Pero si queremos mejorar el rendimiento en nuestros computadores multicore en el lado cliente, o en nuestro escritorio, nos enfrentamos a un desafío interesante.

Probablemente en muchos casos es mejor gastar el esfuerzo en mejorar un algoritmo secuencial que en tratar de paralelizarlo.

Esa es la lección que nos da la Ley de Amdahl. No basta con la voluntad y la urgencia por resolver los problemas de una forma (en este caso, paralelizar). Hay que analizar la complejidad del problema, y Amdahl con unos argumentos sencillos notó que hay un límite inherente al problema de paralelizar. Otros investigadores como Gustafson y Yuan Shi mejoraron el análisis y formularon las condiciones reales para que se aplique esta ley.

La Ley de Amhdal se puede "quebrar", cuando los problemas son "vergonzozamente paralelizables", o cuando nos encontramos con las clases de algoritmos identificados por Yuan Shi, pero en este último caso, las condiciones no siempre son fáciles de encontrar.

Este problema del parelelismo está lleno de problemas abiertos, muy interesantes, y es un área de mucha investigación de punta en estos momentos, sobretodo con mucho financiamiento de los grandes fabricantes de chips multicore.

Para finalizar les dejo, y p
ara los que les interese, les dejo este video, en que [Mark Hill](http://pages.cs.wisc.edu/~markhill) presenta el impacto de la Ley de Amdahl en el diseño de los actuales y futuros procesadores multicore:

  


2009

