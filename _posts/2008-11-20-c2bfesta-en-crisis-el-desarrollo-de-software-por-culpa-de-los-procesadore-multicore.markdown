---
comments: true
date: 2008-11-20 20:27:39
layout: post
slug: '%c2%bfesta-en-crisis-el-desarrollo-de-software-por-culpa-de-los-procesadore-multicore'
title: ¿Está en crisis el desarrollo de software por culpa de los procesadore multicore?
wordpress_id: 354
categories:
- La Naturaleza del Software
- Paradigmas
- Tecnología
---

A nuestra industria le encanta [inventarse crisis](http://www.lnds.net/2006/11/humanware.html), algo que aburre, pero que entiendo porque las crisis sirven para hacer negocios.

Acá va un consejo: cuando lean un artículo, que parte con una afirmación alarmista, piensen que hay alguien detrás que quiere crear una crisis artificial, para ganar mucho dinero desarrollando alguna tecnología que resolverá un problema que probablemente no tenemos.

[![Intel multinucleo 1.jpg](file:///I:/documentos/blogs/lnds/La%20Naturaleza%20del%20Software%20%20Archivos%20Noviembre%202008_files/Intel%20multinucleo%201-thumb-400x285.jpg)](http://www.lnds.net/images/Intel%20multinucleo%201.jpg)

Es el caso de la supuesta crisis generada en el desarrollo de software, con el aumento de los [procesadores multicore](http://es.wikipedia.org/wiki/Multin%C3%BAcleo), pareciera que no existe capacidad para desarrollar programas que aprovechen estas nuevas arquitecturas, [se dice que](http://geeks.ms/blogs/jalarcon/archive/2008/10/10/procesadores-multicore-amenaza-para-la-industria.aspx):

> Al parecer, desarrollar con eficiencia para esto es tan endemoniadamente complicado que hoy en día no hay personal cualificado suficiente para poder desarrollar una industria sobre estos chips. Los propios fabricantes deCPUs como Intel reconociendo el problema está contratando programadores en masa para intentar aportar soluciones desde su parte también.

¿En serio?

En la [edición de **noviembre**](http://mags.acm.org/communications/200811/) de la Communications of The [ACM](http://www.acm.org/), Bryan Cantrill y Jeff Bonwick se cuestionan esta visión apocalíptica.

Los autores nos recuerdan que:

> _La concurrencia siempre ha sido empleada para una sola cosa: mejorar el desempeño del sistema._

A pesar de lo obvio que es esto, parece que se olvida, como si la proliferación de hardware concurrente   
hubiera despertado una ansiedad porque el software use todos los recursos disponibles.

La verdad es que no estamos obligados a usar concurrencia sólo porque el hardware lo provee.

Hay 3 razones principales para querer programar concurrentemente:

1. Reducir la latencia  
2. Esconder la latencia  
3. Aumentar el rendimiento (throughput)

El primer caso depende enormemente de la clase de problema a resolver, es muy específico. Normalmente estos problemas se dan en la computación científica, en que el trabajo puede ser dividido a priori en multiples tareas, en que además el espacio de datos puede subdividirse, y por lo tanto no se comparte la memoria durante el procesamiento.  
  
Por esta razón, es que en estos casos sale más económico ejecutarlos en grillas de pequeñas máquinas,  
en vez de tratar de ejecutarlos en pocas máquinas altamente concurrentes (muti core, o multi procesador).  
Además el costo de reducir la latencia tiene que justificar los tiempos de coordinación de los múltiples elementos.

Cuando tenemos que ejecutar operaciones largas podemos aprovechar el tiempo de latencia para ejecutar otras acciones en paralelo. Esta es la segunda razón para ejecutar procesos concurrentes. y es típico su uso cuando la operación a ejecutar puede bloquearse esperando la respuesta de entidades externas al programa, por ejemplo, un acceso a disco, resolver una dirección DNS, etc. Aunque es tentador usar concurrencia en estos casos, hay que considerarlo bien, porque tener un proceso (o thread) corrriendo en paralelo es bastante complicado de manejar.

Además la ejecución en paralelo no es la única manera de esconder la latencia inducida por el sistema, sobretodo porque podemos lograr el mismo efecto usando operaciones no bloqueantes o usar ciclos de control de eventos, piensen en las primitivas [poll](http://www.opengroup.org/onlinepubs/007908799/xsh/poll.html) / [select()](http://www.opengroup.org/onlinepubs/007908799/xsh/select.html) de Unix.

La tercera alternativa tiene por objetivo aumentar el desempeño usando concurrencia. En este caso, en vez de usar usar lógica paralela para hacer una sóla operación más rápida, podemos ejecutar múltiples operacions de lógica secuencial, para ejecutar más trabajo simultáneo. En este caso las componentes que no comparten estado pueden dejarse totalmente secuenciales, dejando que el sistema las ejecute en forma concurrente.

Para hacerlo más concreto, piensen en un servicio web, atendiendo multiples requerimientos, usando el patrón MVC(Modelo/Vista/Controlador). En este caso, la Vista, programada por ejemplo en JSP, y el Controlador (implementada como un bean J2EE), consisten de lógica puramente secuencial, y sin embargo alcanzan un alto grado de concurrencia, porque el Modelo (tipicamente implementado en la base de datos) aporta un alto grado de parelelismo.

A pesar de que no muchos escriben sus propios motores de bases de datos, y muchos menos escriben un sistema operativo, se pueden construir sistemas altamente concurrentes, y escalables (como las aplicaciones MVC) sin tener que crear explícitamente un thread. En este caso, tenemos concurrencia por arquitectura, más que por implementación.

Como pueden ver, no es necesario tener un ejercito de programadores expertos en programación concurrente, y la verdad es que estas complicaciones mejor dejársela a los que realmente los necesitan (como los programadores de frameworks como J2EE, sistemas operativos, y bases de datos).

Para la mayoría de nosotros, basta con plantear una arquitectura adecuada, para sacar el provecho a nuestros procesadores multicore.

No creo que haya tal crisis, o que sea tan grave, lo que pasa es que a lo mejor, nos quieren crear una necesidad, crearnos un problema que no tenemos realmente.



