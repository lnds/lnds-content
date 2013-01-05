---
comments: true
date: 2007-10-10 18:43:11
layout: post
slug: precision
title: Precisión
wordpress_id: 1110
categories:
- Programación
tags:
- cálculo
- cálculo numérico
- matemáticas
- precisión
- punto flotante
---

Esta nota está "impulsada" por algunos [comentarios](http://www.lnds.net/2007/09/errores_de_redondeo.html#comments) a mi post anterior con respecto al [Bug de Excel **2007**](http://www.lnds.net/2007/09/errores_de_redondeo.html), el primero es un [enlace a una discusión en Kriptópolis](http://www.kriptopolis.org/explorer-aprueba-matematicas) sobre la precisión numérica de javascript. El segundo es para preguntarme si sabía que Visual Basic rendondea hacia abajo.

La verdad es que no sé cómo redondea Visual basic, porque afortunadamente nunca he tenido que programar en ese lenguaje ;).

Pero lo que me sorprende es leer [otros comentarios](http://www.kriptopolis.org/explorer-aprueba-matematicas#comment-24031) que demuestran una ignorancia sobre la precisión de los computadores que es sorprendente en profesionales de la informática.

Todo programador debería saber que la precisión de las operaciones matemáticas está dada por la manera en que se representan los números.

Hoy en día la forma más aceptada para el almacenamiento de números es la representación estándar IEE de Punto Flotante, o [IEE754](http://es.wikipedia.org/wiki/IEEE_754).

Esta representación, a pesar de ser bastante buena y precisa, no permite representar todos los números reales posibles, los que son infinitos.

Como no podemos tener infinitos dígitos para representar un número, debemos adoptar alguna convención, y para eso usamos una cantidad de bits para almacenar los números.

La representación típica usa 64 bits para almacenar un número real. Excel y muchos programas que requieren alta precisión, usan la denominada "representación doble extendida", en que cada número se representa en 80 bits.

Esta representación tiene algunas propiedades curiosas, como por ejemplo, que hay 1.000 veces más números entre 0 y 0,5 que entre 0,5 y 1,0. Es decir, la precisión es mayor cuando más nos acercamos a 0.

Hay consecuencias asociadas a la decisión de usar esta representación. Una de las más impactantes es la no asociatividad de los números.

Si recuerdan del colegio la asociatividad es una propiedad que nos permite decir que podemos agrupar 3 o más números de distintas maneras y los resultados van a ser los mismos.

Por ejemplo, si tenemos los números 0,1;0,56 y 0,78 para sumarlos los podemos agrupar de las siguientes maneras: (0,1+0,56)+0,78 o 0,1+(0,56+0,78). En general, da lo mismo como los ordenemos, el resultado va a ser el mismo.

Sin embargo esto no ocurre en los computadores.

Por ejemplo, este código en javascript demuestra lo que digo:


> var n = new Array(1001);
var i;
for (i = 1; i <= 1000; i++) {
n[i] = i * 1.19;
}




> s0 = 0;
for (i = 1; i <= 1000; i++)
{
s0 = s0 + n[i];
}




> s1 = 0;
for (i = 1000; i >= 1; i--) {
s1 = s1 + n[i]
}




> delta = s1 - s0;




> alert('s0 = ' + s0 + ' s1 = ' + s1 + ' s1-s0 = ' + delta);


Pueden probar este código en [esta página](http://www.tlarson.com/script)

Lo que hace este código es crear un arreglo de 1000 numeros, desde 1 a 1000, donde cada numero es multiplicado a su vez por 1,19 (esto es como aplicarle el IVA a cada numero).

Luego suma los numeros en orden ascendente (s0) y luego en orden descendente (s1).

Al final muestra el resultado de ambas sumas, y la diferencia entre ambas (delta).

Lo interesante es que delta, es decir, s1-s0 debería ser 0, pero como la suma no es asociativa el resultado no es el esperado.

Esta diferencia puede parecer insignificante, pero la verdad es que me he topado con muchas aplicaciones prácticas en que esta diferencia se nota.

Cuando uno empieza como programador se topa con problemas del tipo: "sume el monto de 1.000 facturas aplicándoles el IVA."

Tradicionalmente para sumar un arreglo de N cifras usamos el siguiente algoritmo:


> def Suma(A[1..N])
suma := 0
for i := 1 to N do
suma := suma + A[i]
return suma


Sin embargo esta no esa la manera más precisa de hacer este cálculo.

Una mejor manera de sumar es usando la Fórmula de Kahan:


> def SumaKahan(A[], 1 a N)
S := A[1](http://www.lnds.net/2007/10/precision.html#fn1);
C := 0;
for j := 2 to N do
Y = A[j] - C;
T = S + Y;
C = (T - S) - Y;
S = T;
return S


Esta formula tiene una precisión altisima[1](http://www.lnds.net/2007/10/precision.html#fn1).

Para los que estén interesados en experimentar en la continuación de este artículo hay un programa en C que demuestra la precisión de este algoritmo.

Este es sólo un ejemplo de las cosas que [todo programador debe saber sobre punto flotante](http://docs.sun.com/source/806-3568/ncg_goldberg.html).

[1] Los detalles se pueden encontrar [acá](http://docs.sun.com/source/806-3568/ncg_goldberg.html#1262), la perturbación en el algoritmo es del 2*epsilon, mientras que en el algoritmo tradicional es proporcional a N*epsilon, donde epsilon es el error de aproximación dado por la representación numérica.

[](http://www.lnds.net/images/float1.html)[](http://www.lnds.net/images/float1.html)
