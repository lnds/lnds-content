---
comments: true
date: 2010-05-07 16:58:23
layout: post
slug: peor-es-mejor
title: Peor es mejor
wordpress_id: 344
categories:
- Desarrollo
- Evolución
- La Naturaleza del Software
- Paradigmas
tags:
- mejor
- paradigmas
- peor
- perfección
---

En 1989 [Richard P. Gabriel](http://dreamsongs.com/) introdujo el concepto de Peor es Mejor (Worse is better), o el estilo New Jersey, que  

corresponde a una filosofía de diseño del software en que la simplicidad de la interfaz, y sobretodo de la implementación  

es más importante que cualquier otra propiedad (incluyendo la correción, consistencia y completitud).




Este concepto fue introducido como un capítulo de una presentación que Gabriel hizo aen una coferencia de Lisp, y pueden  

leerlo en la siguiente dirección: The Rise of [Worse is Better](http://www.jwz.org/doc/worse-is-better.html)




En el ensayo Richard Gabriel plantea que existe un estilo de diseño de software que el denomina el estilo MIT/Stanford   

(es decir, un estilo académico) que básicamente tiene las siguientes características:






    * Simplicidad: el diseño debe ser simple, tanto en implementación como interfaz. Es más importante que la interfaz sea simple que la implementación.
    * Correctitud: el diseño debe ser correcto en todos los aspectos observables. La incorrectitud simplemente no está permitida.
    * Consistencia: el diseño no puede ser inconsistente. Se permite que un diseño sea ligeramente menos simple y menos completo para evitar incosistencia. La consistencia es tan importante como la correctitud.
    * Completitud: el diseñ debe cubrir tantas situaciones importantes como sea práctico. Todos los casos razonablemente esperados deben estar cubiertos.  A la simplicidad no se permite reducir excesivamente la completitud.




Como ven estas son características que se consideran buenas y positivas. 




Por otro lado, la filosofía **Worse Is Bette**r, Peor es mejor, o estilo New Jersey, en referencia a los Bell Labs, la cuna de C y Unix es ligeramente diferente en los siguientes aspectos:






    * Simplicidad: el diseño debe ser simple,tanto en implementación como interfaz. Es más importante que la implementación sea simplea que la interfaz. La simpliciddad es la consideración más importante en el diseño.
    * Correctitud: el diseño debe ser correcto en todos los aspectos observables. Es ligeramente mejor ser simple que correcto.
    * Consistencia: el diseño no debe ser demasiado incosistente. La consistencia puede ser sacrificada por la simplicidad en algunos casos, pero es mejor eliminar partes del diseño que tienen que ver con circunstancias menos comunes que introducir complejidad en la implementación o inconsistencias.
    * Completitud: el diseño debe cubrir tantas situaciones importantes como sea práctico. Todos los casos razonablemente esperados deben estar cubierntos. La completitud puede ser sacrificad en favor de cualquier otra cualidad.  

De hecho, la completitud puede ser sacrificada siempre que la simplicidad de implementación esté amenazada. La consistencia puede ser sacrificada para alcanzar completitud si se mantiene la simplicidad, especialmente la inconsistencia de la interfaz no tiene valor.




Según Gabriel el enfoque "peor es mejor" produce software más exitoso, porque permite una difusión viral.

Si uno desarrolla con este principio parte por una base que es básicamente buena, que quizás implementa entre un 50% a un 80% de las funcionalidades requeridas, no tiene que tener todo implementado. Lo importante es liberar el producto como si fuera n virus, de modo que cuando este "virus" se difunde se generan presiones para mejorar y llevar la funcionalidad al 90%,  

pero por otro lado los usuarios han sido condicionados a aceptar algo que no cumple todo lo esperado ("lo correcto").


Con el software peor-es-mejor ocurre que "primero gana aceptación, luego condiciona a los usuarios es esperar menos, y finalmente será mejorado al punto que es casí _lo correcto_". Hay un beneficio adicional del estilo New Jersey, y es que al no ser piezas de software complejas y monolíticas, los sistemas más grandes deben ser diseñados de modo que reusen componentes, lo que genera una tradición de integración.




Ustedes pueden optar por no seguir el camino de "peor es mejor", pero se van a encontrar con 2 escenarios desagradables y frustrantes, en que tienen que definir un "gran sistema complejo", que requiere elaborados diseños, complejas implementaciones, y probablemente una infraestructura especial para poder operar, o un escenario en que el diseño es eterno, los avances de implementación son siempre pequeños pasos en yna serie infinita que no termina nunca, y donde es imposible implementar "lo correcto".




La lección es que a menudo no es deseable ir por "lo correcto". Es mejor tener primero la mitad de lo que se necesita de modo que se difunda como un virus. Una vez que la gente se ha enganchado, tomarse el tiempo para mejorar y llegar al 90% de "lo correcto".




Yo lo he hecho, he implementado servicios en que hemos partido con la mitad del desarrollo completado (o menos), pero el servicio ha ganado aceptación, y ha crecido y evolucionado con el uso y la retroalimentación de los usuarios. Al principio todo parece caótico, pero finalmente, llega un día en que el sol brilla y sin darte cuenta estás dando un servicio mucho mejor  

de lo que pensaste, completamente automatizado y funcionando al 90% de lo que se suponía, pero te has dado cuenta que era eso o que necesitabas.

También he ido por el camino contrario, en que nos hemos tomado todo el tiempo del mundo para construir algo perfecto, un producto ideal, pero sin lograr nada, ni siquiera una venta.




En mi experiencia esta aproximación es mejor, y funciona, aunque, como todo en la vida, debe usarse con moderación.

  




