---
comments: true
date: 2011-04-13 00:35:45
layout: post
slug: buggy-nights
title: Buggy nights
wordpress_id: 1679
categories:
- Desarrollo
- La Naturaleza del Software
- Programación
tags:
- automatización
- bugs
- debugging
- desarrollo
- programación
---

Un pequeño error de tipeo y se puede perder mucho tiempo, e incluso dinero, o quien sabe, vidas.

Sucede que decidí optimizar cierto programita que estaba tomando unos 10 minutos para cargar un archivo de unos 50.000 registros, eso es bastante para el tipo de operación que se realizaba (solo había que ingresar los datos a dos tablas). Decidí modificar el código para usar un patrón típico de procesamiento de archivos en modo batch, pero como estaba apurado fui poco cuidadoso y el proceso terminó con un tiempo horrible (iba por la hora cuando lo detuve). Y aunque miraba el código no podía percibir el problema. Así que lo dejé para después y en la noche recién lo pude  revisar. La solución era tan simple como correr una inserción a una lista al interior de un if, y con esto el tiempo del proceso se redujo a 26 segundos (!).

No es el primer error de este tipo que un programador ha enfrentado. En enero de 1990 los sistemas de telefónicos en Nueva York  de AT&T tuvieron un fallo que provocó que la red telefónica completa de Estados Unidos colapsara.

El error tiene un cierto parecido al bug en mi código.

    
         do {
    	switch expression {
              	...
                    case (value):
    
                        if (logical) {
                           sequence of statements
                           <span style="color: #ff0000;"><strong>break</strong></span>
                       }
                      else  {
                         another sequence of statements
                      }
    
                     statements after if...else statement
    
            }
            statements after case statement
       } while (expression)


El código está tomado de [acá](http://www.soft.com/AppNotes/attcrash.html).

El programador tenía poca experiencia programando en C, asumió que la instrucción break (que puse en rojo)  aplicaba a la sentencia if y esperaba que la secuencia de instrucciones después del if..else se ejecutara, lo que nunca sucedió.

En mi caso es un programa que por ahora sólo estoy ocupando yo, pero en el caso de AT&T el costo fue millonario, y el problema de imagen bastante grave.

Hay que tomarse el tiempo para leer el código, y estar en un estado de concentración para evitar errores de este tipo, y por supuesto desarrollar un buen hábito de probar el código antes de pasar a producción.

El error de AT&T pudo haberse evitado con el uso de herramientas automatizadas de análisis de código. Si les interesa el tema los dejo con este video con una charla de Ira Baxter, de Semantics Design sobre herramientas de este tipo:


