---
layout: post
title: "La Notación Big O"
date: 2013-11-23 14:30
comments: true
categories: 
---

**Un juego de adivinanzas**

Supongan el siguiente juego: "un jugador piensa un número que está entre 1 y 1.000, el otro debe tratar de adivinarlo haciéndole preguntas al primero, a las que sólo se puede responder con un Sí o un No."

Una manera de hacerlo es preguntando por cada número secuencialmente: "¿es el 1?", respuesta: "No". "¿Es el 2?", "No". "Es el 3", "No". etc.

Si la persona pensó en el 999 o en el 1.000 esta no es la forma más eficiente de adivinar el número. Podemos preguntar en forma "saltada" o aleatoria: "¿Es el 523?", "No". "¿Es el 256?", "No"...

<!-- more -->

Esa forma requiere que anotemos en algún cuaderno o libreta cuales números hemos preguntado. El problema de hacer eso es que al generar los números de forma aleatoria tendríamos que ir revisando la lista que llevamos escrita para evitar repetirlos. 

Una mejora sería tener una hoja de papel con los números del 1 al 1000 donde vamos tachando los ya preguntados, esto permite ver de forma directa lo preguntado sin tener que revisar nuestra libreta de notas.

Tanto si hacemos las preguntas de forma secuencial, como si las hacemos de forma aleatoria, la cantidad de preguntas puede ir entre 1 a 999. Haremos sólo 1 pregunta si adivinamos el número a la primera, si tenemos mala suerte tendremos que hacer 999 preguntas. A menos que estemos muy desconcentrados nunca haremos más de 1.000 preguntas. Si el juego consiste en adivinar un número entre 1 y N, la cantidad de preguntas que haremos también será un número entre 1 y N, y nunca haremos más de N preguntas.

Pero hay otra manera de resolver este problema. Podemos partir por el medio y hacer la siguiente pregunta: "¿El número que piensas es menor que 500?", el otro jugador podría responder "Sí", lo que significa que el número tiene que estar entre 1 y 499, con esta simple pregunta hemos reducido el universo de valores posibles a adivinar a la mitad. Podemos volver a preguntar: "¿El número es menor que 250?", un "Sí" como respuesta reduce el universo al rango 1 a 249. Preguntamos por tercera vez: "¿es el número menor que 125?", y si la respuesta es un "No", sabemos que el número tiene que estar entre 125 y 249 y podemos seguir así, siempre dividiendo el rango por la mitad.

Lo interesante es que de esta forma nunca haremos más de 10 preguntas para adivinar el número. Si tenemos que adivinar un numero entre 1 y un millón tendremos que hacer a lo más unas 20 preguntas. En general, para cualquier número N haremos a lo más una cantidad de preguntas menor o igual al logaritmo en base 2 de N. Esto, porque siempre dividimos el rango de búsqueda en dos. Además con esto hemos descubierto un algoritmo eficiente para adivinar el número.

**La notación Big O**

Cuando hablamos de algoritmos, en particular cuando los analizamos, los informáticos usamos una notación particular para designar la eficiencia de estos. Es la notación Big O (Gran O), una técnica matemática usada para expresar aproximaciones de funciones. En algunos artículos y en algunos capítulos de [mi libro](http://www.lnds.net/books) he usado esta notación, pero nunca la he explicado, y claro no todo el mundo que lee estos artículos entiende esa parte, la que por supuesto se saltan, o simplemente ignoran, en muchos casos no es relevante para entender lo expuesto. Sin embargo, creo que no está demás conocerla un poco.

En el ejemplo anterior, del juego de adivinanza de un número entre 1 y N, cuando usamos el primer "algoritmo", de ir preguntando en forma secuencial, o el segundo algoritmo, en que preguntamos al azar, tenemos que la cantidad de preguntas a realizar es a lo más N, en ese caso decimos que el algoritmo es de "orden N", y lo denotamos: O(N).

En el segundo caso, en que acotamos el rango de búsqueda dividiéndolo en dos partes, decimos que el algoritmo es O(lg N), donde lg denota el logaritmo en base 2.

La notación O(f(N)) denota, en general, que la cantidad de operaciones básicas del algoritmo es una función de N. Por ejemplo, un algoritmo de ordenamiento conocido como el método de la burbuja requiere de N al cuadrado operaciones para ordenar una lista de N números, decimos entonces que ese algoritmo es O(N^2), donde N^2 es una notación para designar N elevado a 2.
Hay otras formas de ordenar más eficientes, como QuickSort, que divide el problema sistemáticamente en dos grupos, en este caso el algoritmo es O(N lg N), es decir, N multiplicado por el logaritmo base 2 de N. 

Los informáticos tienen técnicas para estimar las complejidades de sus algoritmos, las que se pueden llegar a dominar con la práctica. Estas técnicas les permiten discriminar entre distintos algoritmos, o evaluar los propios. A veces calcular la eficiencia de un algoritmo resulta desafiante. Lo importante es que esta notación resulta muy útil para discriminar ante un problema que algoritmo usar.

Sin embargo, no se debe confundir este valor que entrega la notación big O con el tiempo efectivo en la ejecución de un algoritmo, este dependerá de otros detalles particulares de la máquina en que se opera.

Por último, normalmente estas estimaciones que se entregan con esta notación consideran un escenario en que existe una única CPU ejecutando la tarea. Supongamos que tuvieras que implementar el juego de adivinación, y que cuentas con N personas preguntando al mismo tiempo (y que el que responde es capaz de contestar a la misma vez a todos), entonces en ese caso tu algoritmo que con una CPU es O(N), se convierte en O(1). 

Pero el algoritmo de división se hace más complejo de manejar en un ambiente de muchos procesadores paralelos, de hecho, no es posible ejecutar el segundo paso sin tener la respuesta del primer paso, así que en ese caso contar con N "preguntadores" no beneficia a este algoritmo en particular.

Esa es precisamente la discusión que plasmo en los tres artículos sobre el problema de paralelizar, en la [tercera parte del libro](http://www.lnds.net/books). Lo que es muy interesante  hoy en día, en una época donde contamos con un alto poder de computación mediante los procesadores multi core.
