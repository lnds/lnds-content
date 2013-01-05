---
comments: true
date: 2008-08-25 06:58:37
layout: post
slug: '%c2%bfpor-que-falla-la-calculadora-de-google'
title: ¿Por qué falla la calculadora de Google?
wordpress_id: 1158
categories:
- Sin categoría
---

Tengo una sospecha de la posible causa de la [falla de la calculadora de Google](http://www.fayerwayer.com/2008/08/segun-google-500000000000002-500000000000001-0/), prueben este programa en C:


> #include <stdio.h>
#include <math.h>




> int main()
{
char* a = "399999999999999";
char* b = "399999999999998";
float da = atof(a);
float db = atof(b);

printf("da = %f,  db = %f\n", da, db); // para ver como se almacenan los numeros
printf("%s - %s = %f\n", a, b, da-db);

a = "500000000000002";
b = "500000000000001";
da = atof(a);
db = atof(b);

printf("da = %f,  db = %f\n", da, db);

printf("%s - %s = %f\n", a, b, da-db);
}


Al ejecutar este programa obtendrán como salida lo siguiente:

399999999999999 - 399999999999998 = 0.000000
500000000000002 - 500000000000001 = 0.000000

parece que en Google están usando precisión simple, es decir, números en punto flotante en 32 bits.
prueben cambiando float por double en el programa anterior, y problema resuelto.

Es un error feo, aunque no es un tremendo misterio Mr. Chips....
