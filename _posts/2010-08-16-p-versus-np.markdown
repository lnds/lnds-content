---
comments: true
date: 2010-08-16 17:22:46
layout: post
slug: p-versus-np
title: P versus NP
wordpress_id: 628
categories:
- Cultura
- La Naturaleza del Software
- Programación
tags:
- algoritmos
- complejidad
- P vs NP
---

El problema de P versus NP se considera el problema abierto más importante en la ciencia de la computación. De hecho el Instituto Clay lo incluye entre los 7 [“problemas del milenio”](http://www.claymath.org/millennium/), que corresponden a los problemas matemáticos abiertos más importantes según ese instituto.

El premio por resolver alguno de estos problemas es de un millón de dólares. La descripción del Instituto Clay sobre el problema P versus NP es más o menos la siguiente:


> Supongamos que estás organizando el alojamiento para un grupo de cuatrocientos estudiantes universitarios. El espacio es limitado y sólo cien de los estudiantes recibirán lugares en los dormitorios. Para complicar las cosas, el Decano te ha proporcionado una lista de parejas de estudiantes que presentan incompatibilidad entre sí, y pidió que ningún par de la lista aparezca en la distribución final.

Este es un ejemplo de lo que los científicos en computación llaman un problema NP, porque es fácil comprobar si una determinada lista de cien  estudiantes propuestos es satisfactoria (es decir, ningún par tomado de lista aparece en la lista de incompatibilidades entregadas por el decano).  Sin embargo la tarea de generar una lista desde el principio parece ser tan  difícil, como completamente impracticable.

De hecho, el número total de maneras de elegir un centenar de estudiantes procedentes de los cuatrocientos solicitantes ¡es mayor que el número de átomos en el universo conocido! Así que ninguna civilización futura podría esperar construir un supercomputador capaz de resolver el problema por fuerza bruta, es decir, revisando cada posible combinación de 100 estudiantes.

Sin embargo, esta aparente dificultad sólo podría reflejar la falta de ingenio del programador. Uno de los  problemas pendientes en ciencias de la computación es determinar si existen problemas cuya respuesta puede ser rápidamente verificada, pero que requieren un tiempo imposiblemente largo para resolver, por cualquier procedimiento directo.  Problemas como el mencionado al principio parecen ser de este tipo, pero hasta ahora nadie ha logrado probar que algunos de ellos son realmente tan difíciles como parecen, es decir, que realmente no hay forma viable de generar una respuesta con la ayuda de un computador. Stephen Cook y Leonid Levin formularon en 1971, de forma independiente el problema de  P versus NP.


La pregunta, en esencia, que propone el problema P versus NP es la siguiente:


> Supongan que la solución a un problema puede ser verificada rápidamente con un computador. Entonces, ¿es posible que la solución en si misma pueda ser computada rápidamente?


Ustedes dirán, ¡estos son problemas de los matemáticos, o de los _computólogos _y si se resuelven no tiene ninguna importancia práctica!. Les sugiero que lo reconsideren, porque un problema matemático, más abstracto aún, propuesto hace unos 110 años atrás, llevó a la creación del computador, y generó todos los adelantos tecnológicos que disfrutamos en la actualidad gracias a la informática.
