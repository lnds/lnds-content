---
comments: true
date: 2007-09-27 23:07:20
layout: post
slug: errores-de-redondeo
title: Errores de Redondeo
wordpress_id: 703
categories:
- La Naturaleza del Software
- Programación
tags:
- cálculo numérico
- matemáticas
- precisión
---

Aunque el bug de Excel **2007** ha tenido mucha cobertura, no es primer error de redondeo de la historia, y tampoco el más catastrófico. Y aunque todavía no sabemos que consecuencas pueda tener este nuevo bug de Excel, por lo menos todavía muere nadie por este error.

Pero durante la primera guerra del golfo hubo un error de similar origen, que le costó la vida a 28 marines norteramericanos.

El origen del bug de excel y del error que mató a los marines es el mismo.

Para los que no lo saben, el error en Excel **2007** consiste en que si ustedes multiplican 77,1 por 850 en vez de obtener 65.535, como debería ser, en la celda se refleja el valor 100.000.

El problema no está en el almacenamiento interno del número, sino que en el despliegue de la cifra en pantalla. [Joel Spolsky explica muy bien el error](http://www.joelonsoftware.com/items/2007/09/26b.html), y sugiero que la lean para ver los detalles.

Pero, en forma breve, tenemos que la representación binaria de 77,1 es la siguiente:

0100 0000 0101 0011 0100 0110 0110 0110
0110 0110 0110 0110 0110 0110 0110 0110

Si se fijan bien la secuencia 0110 0110 0110 se repite. Esto es porque el 0,1 no se puede representar en forma exacta en notación binaria. Es lo mismo que pasa en decimal cuando queremos representar 1/3, que queda 0,333333333333333.....

Esta es una cifra decimal periódica, y tiene infinitos 3 "hacia la derecha", bueno, lo mismo pasa con el 0,1 en binario. Por eso que hay que tener cuidado cuando se trabaja con números en punto flotante.
Examinemos las consecuencias trágicas de un bug de este tipo.

El 25 de febrero de 1991 una batería de misiles patriot en Dharan, Arabia Saudita, no pudo detener un misil SCUD Iraquí impactando directamente en una barraca con 28 marines.

[![](http://www.lnds.net/blog/wp-content/uploads/2010/08/patriot-photo1-300x195.jpg)](http://www.lnds.net/blog/wp-content/uploads/2010/08/patriot-photo1.jpg)

De acuerdo a un [informe oficial](http://www.fas.org/spp/starwars/gao/im92026.htm) sabemos que el misil patriot falló debido a un error acumulado en el cronómetro interno. Resulta que el software usaba un contador que debía incrementarse cada 0,1 segundos para sus cálculos. La batería de misiles patriot llevaba operando 100 horas, lo que acumuló un error de 0,34 segundos, dado que el misil scud se mueve a 1.676 metros por segundo, el misil patriot al ser lanzado ya estaba "desplazado" en casi medio kilómetro del objetivo.

El tipo de error de Excel **2007** y el del misil patriot es de la misma clase, un problema de redondeo, claro que las consecuencias son bien distintas. Sólo esperemos que nadie esté usando Excel **2007** para controlar algún sistema crítico, o del que dependan vidas humanas.
