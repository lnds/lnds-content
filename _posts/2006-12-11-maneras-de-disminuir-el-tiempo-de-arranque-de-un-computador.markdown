---
comments: true
date: 2006-12-11 08:01:29
layout: post
slug: maneras-de-disminuir-el-tiempo-de-arranque-de-un-computador
title: Maneras de disminuir el tiempo de arranque de un computador
wordpress_id: 1387
categories:
- Sin categoría
---

> "Los computadores demoran mucho en arrancar, y para mí eso no tiene sentido. El mío demora unos 30 segundos; es el doble o triple de lento que los de mis amigos que he usado. ¿Por qué no puedo prender y apagar mi computador igual que con un televisor? El 99% de las veces que arranca mi computador hace lo mismo. Lo que obtengo es un Windows XP con unos 50 a 75 megas de memoria ocupados. Mi coimputador deberías ser lo suficientemente inteligente para tomar esa información directamente desde el disco duro y colocarla en memoria. Se podría colocar esta información en la parte inicial del disco duro. Siempre que hagas algo que realmente cambie la configuración deberías repetir el proceso de arranque y grabar los resultados. Esto debería darnos unos re inicios instantáneos. Bastaría apretar el botón de reinicio y comenzar a trabajar. ¿O estoy equivocado? ¿Por qué las compañías no han hecho de los computadores o laptops de encendido instantáneo una prioridad?"


Fuente [Slashdot](http://replay.waybackmachine.org/20071029153224/http://ask.slashdot.org/askslashdot/06/12/11/0142212.shtml)
h2. Hibernación

El lector de slashdot no conoce el proceso de hibernación (hibernating). Lo que pasa es que este proceso no se encuentra habilitado por defecto en los sistemas operativos. Pero existe hace mucho tiempo, y funciona bastante bien. Claro que a veces demora la secuencia de apagado, y eso depende de la cantidad de memoria RAM que debes preservar.

Mi notebook tiene 1 Giga byte de memoria, eso significa que debo reservar un gigabyte de disco duro para guardar el estado de hibernación de mi máquina. Considerando además que tengo otro gigabyte reservado para memoria swap, el uso es de 2 Gigabytes, como mi notebook es "viejito", esos 2 gigabytes corresponden al 5% del espacio disponible (en realidad es más porque los Gigabytes de RAM no son lo mismo que los gigabytes de disco).

Una solución sería contar con memorias flash, que guarden el estado de memoria, pero probablemente sería caro, y requeriría un rediseño de los computadores personales.

La verdad es que el proceso de bootstraping nunca fue pensado para ser ejecutado a cada rato, lo recomendable es no apagar los computadores muy seguido. De hecho, normalmente yo mantengo mi notebook encendido por varios días, y aprovecho otra característica que se llama stand by.

El stand by mantiene el computador en un modo de bajo consumo de energía, los discos duros se detienen, y la memoria se conserva en el mismo estado. Por supuesto, esto requiere energía, a diferencia del modo de hibernación. Si tu computador es de escritorio o tienes un laptop con una buena batería, este es un mecanismo razonable.
