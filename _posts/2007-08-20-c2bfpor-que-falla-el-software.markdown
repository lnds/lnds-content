---
comments: true
date: 2007-08-20 20:16:35
layout: post
slug: '%c2%bfpor-que-falla-el-software'
title: ¿Por qué falla el Software?
wordpress_id: 1826
categories:
- Sin categoría
---

Leía la interesante nota de Christian los problemas que provoca OOXML, y encontré un comentario que me llamó la atención:

pareciera que Microsoft hubiera acostumbrado a los usuarios a que los programas fallan, mucho y es normal.

La verdad, es que como cualquier cosa hecha por el hombre, el software no está libre de errores.
Pero pareciera que la calidad del software, comparado con otras construcciones humanas, es pésima.
Algunos dirán que en el caso de Microsoft es aún peor.

¿Acaso el software es tan complejo que su tasa de errores siempre será mayor?

La realidad es que no.

El software puede construirse libre de fallas. Cuando decimos libre de fallas, queremos decir que la tasa de errores es tan baja como en otras actividades humanas, incluso más.

Software correcto y software libre de errores

"Beware of bugs in the above code; I have only proved it correct, not tried it."

Donald Knuth

Existen métodos formales (es decir, matemáticos) que permiten demostrar que una pieza de software es correcta. Estos método por supuesto son trabajosos, pero se han hecho avances para automatizar estos problemas.

Muchos lenguajes de programación contienen una serie de directivas que permiten demostrar que el software es correcto de acuerdo a las especificaciones.

Esto no significa que el software esté libre de fallos, porque pueden pasar varias cosas:

El hardware puede tener alguna falla
Los recursos necesarios no están disponibles, por ejemplo, no hay suficiente memoria RAM porque está siendo usada por otro proceso, o el espacio en disco no es suficiente.
El software fue dimensionado para cierta carga de trabajo, y los usuarios han decidido aumentar las demandas sobre el mismo.
Y un largo etcétera.

Pero, ¿si uno puede establecer esta lista de posibles fallasa a priori, qué nos impide tomar las medidas para evitar estas fallas?

La verdad es que nada.

Errores aceptables

Cada vez que nos encontramos ante una falla, estamos aprendiendo algo nuevo, algo que no sabíamos sobre el sistema.

Esta ignorancia puede originarse porque no fuimos rigurosos en el análisis de requerimientos, o porque nadie conocía las condiciones que provocaron el fallo.

Los errores revelan nueva información sobre el sistema. La corrección del bug es responder a una nueva pregunta que nos plantea el sistema.

El único bug aceptable es aquel que nos revela algo que no sabíamos, todos los demás se pueden prevenir, ya sea programando en forma defensiva, o manejando las excepciones de manera adecuada.

Cada vez que enfrentamos la corrección de un bug debemos realizar las pruebas de regresión adecuadas, agregar nuevos tests, que nos permitan asegurar que si arreglamos un bug no dejemos sin funcionar algo que estaba bien.

Entonces ¿por qué falla tanto el software?

Los usuarios han sido engañados todo este tiempo, el software no es más complejo que construir edificios, o automóviles.

Lo que pasa es que los equipos de desarrollo del software comercial sufren de una serie de presiones del mercado que hacen que no se hagan todas las pruebas exhaustivas.

Se insiste en sacar nuevas versiones anualmente, que agregan más y más características al software.
Mientras más grande y complejo el software, más puntos de falla puede tener.

La verdad, es que el software bien hecho no debería tener fallas.
