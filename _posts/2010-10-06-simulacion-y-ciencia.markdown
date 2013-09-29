---
comments: true
date: 2010-10-06 03:11:45
layout: post
slug: simulacion-y-ciencia
title: Simulación y ciencia
wordpress_id: 919
categories:
- Ciencia
- Credibilidad
- La Brecha Intelectual
- La Naturaleza del Software
tags:
- ajedrez
- Chaitin
- ciencia
- complejidad
- entendimiento
- simulación
---

¿Alguien podría explicarme como Tecnologías de la Información se puede abreviar TIC? así con C final. Bueno, a los académicos del DCC,   donde estudié, les ha dado por abreviarla así, en vez de TI (ver [acá](http://dccuchile.blog.terra.cl/2010/09/23/escience-el-punto-de-encuentro-entre-las-tecnologias-de-la-informacion-y-la-ciencia/)). Pero bueno, eso es un detalle menor, de poca importancia (pero preocupante).

Más me preocupa las afirmaciones de Claudio Gutierrez: _"Quienes trabajan en simulación saben que para resolver un problema complejo no se necesita mucha teoría." (tomado de [El Fin de la Ciencia](http://dccuchile.blog.terra.cl/2010/10/05/el-fin-de-la-ciencia/)) _El argumento  de Gutierrez básicamente es que dada la enorme capacidad de cómputo que se está desarrollando el razonamiento científico y el modelado quedará reducido a algo tan inútil como las discusiones metafísicsas sobre las propiedades aerodinámicas de las alas de los ángeles.

Yo no sé cuanta simulación ha hecho el profesor Gutierrez en su vida, pero si hay algo que sabemos muy bien los que practicamos la computación es el viejo principio de la simulación, GIGO, Garbage In Garbage Out, una simulación es tan buena como el conocimiento que tenga la persona que la escribió.  Sólo se puede simular lo que se entiende.

Permitanme citar a Mark Chu-Carroll, PhD en ciencias de la computación, quién trabaja como ingeniero en Google, que explica muy bien cómo es esto de la simulación (el texto es largo, pero vale la pena):


> Así que, ¿cuál es el problema con la simulación? No es que no tengamos suficiente poder computacional. La cantidad de poder computacional disponible es realmente inabordable por nuestra mente. Muchas cosas que podrían haber sido completamente imposible hace pocos años atrás se han vuelto absolutamente rutinarias. Sobre mis piernas, tengo un computador con 2 CPUs, cada una corriendo a 2.5 gigahertz. Bajo mi escritorio tengo un computador con 8 CPUs. Y rutinariamente escribo programas que usan varios _miles _de CPUs en un datacenter. Esto no es inusual hoy en día: la gente que quiere correr simulaciones puede fácilmente y con poco dinero acceder a clusters de miles de computadores.

Así que el poder computacional no es un problema. Usando computadores y software modernos, tenemos suficiente poder para correr simulaciones increiblemente complejas.

[...] El problema con usar simulaciones para hacer pruebas no tiene nada que ver con el poder computacional. No importa cuanto capacidad computacional tengas disponible, aún hay un enorme, problema fundamental con las simulaciones. No es dificil de entender: las simulaciones sólo hacen _lo que les dices que hagan_.

Comencemos desde el principio: ¿qué es una una simulación? Es un modelo de un sistema real, que intenta reproducir los efecto y/o el comportamiento de el sistema que modela. En el caso de una simulación por computador, de lo que realmente estamos hablando, podemos producir un modelo matemático y algorítmicamente describir cómo el modelo evoluciona en el tiempo. En otras palabras, escribimos un programa para computador que corre un modelo matemática de un proceso.

Y ahí está el problema. Nosotros producimos el modelo, y nosotros implementamos el modelo. Este hace exactamente lo que decimos que haga. Los programadores tenemos un dicho que aplica particularmente bien a las simulaciones: basura entra, basura sale. Los computadores hacen exactamente lo que les decimos que hagan; si lo que les dices no es lo correcto, no  hay cantidad de poder computacional  que vaya a cambiar el hecho que no les dijiste que hicieran lo correcto.

Si realmente entendemos lo que estamos simulando, podemos hacer simulaciones que son asombrosamente precisas. Por ejemplo, podemos hacer simulaciones de túneles de viento para diseño de aviones, y los resultados de estos experimentos simulados son perfectos dentro de nuestra habilidad para medirlos. Lo hemos hecho tan bien que  podemos tener resultados más precisos con un modelo computacional que con un modelo a escala en  un túnel de viento. Entendemos como los flujos de aire funcionan. Sabemos como modelarlos. Toma un montón de computación hacer un trabajo decente con eso, pero como dije antes, la falta de recursos computacionales generalmente no es el problema.

No podemos simular algo si no sabemos como funciona. [...] Si no tenemos un modelo exacto no podemos construir una simulación precisa.

[...] Hay otro aspecto importante de la simulación que es importante: la validación. Aún en las mejores simulaciones, no podemos estar seguros que la simulación es correcta hasta que la probamos. Esta pruebas es lo que se llama validación. Para validar una simulación, lo que necesitas es tomar un punto de partida en  mundo real y en la simulación, y observar por un periodo de tiempo, y luego revisar que los resultado de las simulación y el mundo real coinciden. Por ejemplo, en una simulación de flujo de aire, colocas un objeto en un tunel de viento y mides todo, entonces simulas colocando un objeto en el túnel de viento con el programa, y comparas los resultados.

Sin validación, no tienes manera de saber si tu modelo es correcto.

[...] Después de todo esto, puede sonar como si los modelos de computador son aburrido y muy útiles. Después de todo, todo lo que hacen es lo que les decimos que hagan. ¿Así que no sabemos siempre los resultados antes de empezar?

Facinantemente, no. Tenemos modelos sorprendentemente precisos de los fenómenos físico, pero el entendimiento de que significan  estos modelos cuando son escalados al tamaño de la vida es increíblemente difícil. Y de hecho, a veces simplemente no sabemos como ver lo que un modelo dice sobre como un sistema evolucionará en el tiempo sin realmente verlo progresar. Por ejemplo, mencioné el sistema de flujo de fluidos arriba. No sabemos si es posible computar el resultado de un sistema de flujo de fluidos sin simularlo a través de pasos de tiempo discretos. La simulación es increiblemente útil, porque nos deja tomar sistemas dinámicao, y mirarlos como evolucionan en el tiempo.

Así que la simulación tiene un rol. Y esperanzadoramente, puede reducir [por ejemplo] el número de animales que son usados en la experimentación médica. Pero nunca podrá reemplazarlo. No hay un substituto para la realidad.

["Experimentación Animal y Simulación"](http://scienceblogs.com/goodmath/2010/03/_in_my_post_yesterday.php)


Chu-Carroll explica todo esto en el contexto de una discusión sobre la posibilidad de reemplazar la experimentación con animales en la investigación de enfermedades, uno de los tópicos más complejos que aborda la ciencia actual.

El profesor Gutierrez plantea que todo es cuestión de poder computacional, y que este va a hacer innecesario el razonamiento, precisamente lo opuesto de Chu-Carroll. Y para sostener su punto, Gutierrez presenta el ejemplo del [ juego de ajedrez](http://www.lnds.net/blog/2008/01/ajedrez.html), confundiendo un algoritmo de cobertura y fuerza bruta, con la simulación y extrapolando audazmente a que con esto se va a acabar la ciencia. Hay otros problemas en los argumentos presentados (como la contraposición con [el modelo de Chaitin de las leyes de la naturaleza](http://www.lnds.net/blog/2010/06/todo-es-software.html)), pero lo vamos a dejar acá.

Lo que me interesa dejarles en claro es que  la afirmación "_Quienes trabajan en simulación saben que para resolver un problema complejo no se necesita mucha teoría.", _como ha quedado demostrado arriba, es totalmente  falsa.
