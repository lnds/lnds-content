---
comments: true
date: 2009-01-11 15:21:41
layout: post
slug: el-programador-y-el-calentamiento-global
title: El programador y el calentamiento global
wordpress_id: 313
categories:
- La Naturaleza del Software
- Programación
- Tecnología
---

A través de [una nota de Luis Ramirez](http://luisramirez.cl/blog/?p=2049) llego a este [artículo](http://technology.timesonline.co.uk/tol/news/tech_and_web/article5489134.ece), en que se muestra el impacto en uso de energía, y por ende en el calentamiento global, de Google, y otras empresas TI.

Se estima que una búsqueda en Google consume la mitad de lo que consume hervir una tetera con agua. O que mantener un Avatar en Second Life, de acuerdo al cálculo de Nicholas Carr, cuesta 1,752 kilowatt hora de electricida al año, es decir, el consumo medio de un brasileño.

Estos números están dados por el gasto en energía de los datacenters.  
Pero una cosa que falta mencionar es el enorme gasto energético que los usuarios generamos.

Cuando yo empecé a trabajar, a fines de los 80, existían muy pocos computadores, en ese tiempo aún reinaban los mini computadores, o los mainframes, con algunos terminales. La llegada del PC cambió todo, y con esto aumento el gasto energético asociado a la computación.  
Ahora casi todos los empleados de las empresas tienen PCs en sus escritorios, aunque se usan en un 80% para enviar y recibir emails, y ver LUN o Facebook.

En nuestras escuelas se están instalando computadores que gastan mucha energía, sin considerarse un aumento en el presupuesto de electricidad, y menos el impacto en el calentamiento global, y sin embargo uno de los computadores más "verdes" que existe en este momento es el XO, de OLPC ([con gastos que apenas bordean los 3 watts](http://www.lnds.net/2007/05/xo-energia-medio-ambiente-y-el-mito-de-l.html)).

Es relativamente fácil medir el gasto de Google, y la industria TI a nivel de Datacenters, pero ¿qué pasa en el otro extremo?, me pregunto yo,

**El programador y su responsabilidad en el calentamiento global**

El otro día revisé el código fuente de unos rutinas en javascript, pertenecientes a un sitio que genera cientos de miles de transacciones diarias en nuestro país.

En esas funciones javascript, se encontraban algunas de los peores algoritmos de validación que he visto en mi vida, creo que escribiré algo al respecto más adelante.

Lo que importa es que ese código mal programado, distribuido en cientos de miles de equipos, ejecutándose al mismo tiempo, en horas peak, resulta en un consumo de muchos gramos de carbono, el equivalente a hervir muchas teteras de agua.

Antes los programadores teníamos que preocuparnos por usar en forma eficiente los pocos recursos que teníamos disponible en nuestros sistemas (menos de 1 Mega Byte de RAM, discos lentos, de 20 Megabytes o menos, cpus con ciclos de 10 Hertz, etc). Esto nos obligaba a escribir código eficiente, que aprovechara estos pocos recursos.

Ahora ese conocimiento es nuevamente necesario, pero por otras razones, debemos escribir código que consuma menos energía.

Durante los últimos años, las escuelas que enseñan programación, lamentablemente han dejado de lado la enseñanza de esta técnicas.

Ahora nadie se preocupa de usar menos RAM, total, tenemos muchos Gigabytes disponibles en nuestros computadores. El problema, es que acceder a la memoria primaria, es decenas de veces más caro, en términos energéticos, que comparar el valor de un par de registros al interior de la CPU.

Además, hoy en día escribimos código que finalmente termina ejecutándose en miles de CPUs, distribuidas, en distintas partes del mundo, o en la [nube](http://www.lnds.net/la-nube/). Cuando escribes un loop, ya no debes pensar que está corriendo sólo en tu PC, imagina ese código, replicado millones de veces. Cuando te das cuenta de eso, empiezas a recordar tus viejas clases de programación de sistemas (o lenguajes orientados a la máquina), si es que tuviste la suerte de tener esas clases.



