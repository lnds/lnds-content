---
comments: true
date: 2011-11-12 23:03:04
layout: post
slug: comprensin-de-lectura
title: Comprensión de lectura
wordpress_id: 2424
categories:
- Destacados
- Evolución
- La Brecha Intelectual
- La Naturaleza del Software
- Paradigmas
- Programación
tags:
- caos
- cascada
- crisis
- desarrollo
- ingeniería de software
---

Resulta que el modelo de cascada es quizás uno de los mayores errores de comprensión de lectura en toda la historia de la ingeniería de software. En 1970 Winston Royce escribe un [paper](http://www.cs.umd.edu/class/spring2003/cmsc838p/Process/waterfall.pdf) donde, desafortunadamente, usa las palabras “grandiosa aproximación” para referirse a la siguiente figura:

[![waterfall](http://www.lnds.net/blog/wp-content/uploads/2011/11/waterfall_thumb.png)](http://www.lnds.net/blog/wp-content/uploads/2011/11/waterfall.png)

En realidad Winston Royce escribió este [paper](http://www.cs.umd.edu/class/spring2003/cmsc838p/Process/waterfall.pdf) para criticar este modelo, pero terminó siendo citado una y otra vez por la comunidad “científica” como un modelo clásico y establecido.

Es típico encontrar referencias del tipo: “el modelo de cascada es un modelo probado (Royce, 1970)”. Pero en realidad Royce inventa este diagrama en su artículo para ilustrar como se han manejado proyectos en los que él participaba y para posteriormente proponer su propio modelo de desarrollo iterativo.

El modelo de Royce, no sólo es iterativo incremental, sino que propone 5 elementos fundamentales para el éxito de un proyecto.



	
  1. Diseñar primero.

	
  2. Documentar el diseño.

	
  3. Construir dos veces: una primera versión que es revisada por los usuarios, una suerte de prototipo funcional, y una segunda versión que es el producto terminado.

	
  4. Planificar, controlar y monitorear las pruebas.

	
  5. Involucrar al cliente.


Lamentablemente todo lo que decía Royce se perdió. Cuando el departamento de defensa de USA tenía que definir el estándar de desarrollo de software adoptó el modelo de cascada, simplemente porque “Royce ya inventó el modelo correcto, usémoslo”, y nació el [DoD-2167](http://www.product-lifecycle-management.com/download/DOD-STD-2167A.pdf). Y cuando la OTAN enfrentó el mismo problema, adivinen a quienes le preguntaron que se debía hacer.

Cero comprensión de lectura. Incluso hasta nuestros días, todavía vemos consultores que consideran el modelo de cascada como un modelo establecido y tradicional (peor aún, todavía es enseñado como un buen modelo para desarrollar software en las universidades).

Ahora, lo interesante de esta historia, y de redescubrir el paper de Royce es que los modelos ágiles de desarrollo de software no son nuevos, que tampoco está probado científicamente que el modelo de cascada haya sido exitoso alguna vez, y que no es buena idea colocar un diagrama de una mala idea al principio de un artículo, probablemente la gente no lee más allá de la primera página.

Fuentes:



	
  * [Don't draw diagrams of wrong practices – or: Why people still believe in the Waterfall model](http://tarmo.fi/blog/2005/09/dont-draw-diagrams-of-wrong-practices-or-why-people-still-believe-in-the-waterfall-model/)

	
  * [Managing the development of large software systems](http://www.cs.umd.edu/class/spring2003/cmsc838p/Process/waterfall.pdf), Dr Winston W. Royce

	
  *  [Defense System software development, DoD-2167](http://www.product-lifecycle-management.com/download/DOD-STD-2167A.pdf).


