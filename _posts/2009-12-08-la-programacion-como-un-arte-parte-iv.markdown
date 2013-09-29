---
comments: true
date: 2009-12-08 21:15:10
layout: post
slug: la-programacion-como-un-arte-parte-iv
title: La programación como un Arte (Parte IV)
wordpress_id: 220
categories:
- La Naturaleza del Software
- Personajes
- Programación
tags:
- arte
- Dijkstra
- Knuth
- programación
---

**

**La programación de computadores como un arte**

Por Donald Knuth, 1974

(Lee las partes [I](http://www.lnds.net/2009/12/la-programacion-como-un-arte-parte-i.html), [II](http://www.lnds.net/2009/12/lla-programacion-como-un-arte-parte-ii.html), y [III](http://www.lnds.net/2009/12/la-programacion-como-un-arte-parte-iii.html))

  


Obras de Arte

**

**  
**Cuando estoy sentado en la audiencia escuchando una larga charla, mi atención usualmente empieza a desvanecerse en este punto, cerca de la hora. Así que ¿me pregunto si se están cansando de mi arenga sobre "ciencia" y "arte"? Realmente espero que sean capaces de escuchar atentamente el resto de esto, de todos modos, porque ahora viene la parte sobre la cual tengo sentimientos más profundos.

  


Cuando hablo de programar computadores como un arte, estoy pensando primariamente al respecto como una _forma de arte, _en un sentido estético. La principal meta de mi trabajo como educador y autor es ayudar a la gente a aprender como escribir _programas hermosos_. Es por esta razón que me he sentido satisfecho que mis libros actualmente aparezcan en la Biblioteca de Bellas Artes de la Universidad de Cornell. (Aunque, los tres volumenenes permanecen en la librera, sin ser usados, así que me temo que el bibliotecario pueden haber cometido un error al interpretar mi título literalmente.)

  


Mi sentimiento es que cuando preparo un programa, es como componer poesía o música, como dijo una vez Andrei Ershov, programar nos puede dar ambas una satisfacción intelectual y emocionale, porque es un verdadero logro dominar la complejidad y establecer un sistema de reglas consistentes.

  


Más aún, cuando leemos los programas de otras personas, podemos reconocer algunos de ellos como genuinas obras de arte.  Puedo aún recordar la gran emoción que fue para mí leer el listado del programa en assembler de Stan Poley SOAP II en 1958, probablemente ustedes pensarán que estoy loco, y los estilos ciertamente han cambiado grandemente desde entonces, pero en ese tiempo era un gran asunto para mí ver cuan elegante un programa de sistema podía ser, especialmente al compararlo con los pesados códigos que encontré en otros listados que estudiaba en ese tiempo. La posibilidad de escribir un programa hermoso, aún en lenguaje ensamblador, es lo que me dejó enganchado con la programación en primer lugar.

  


Algunos programas son elegantes, algunos exquisitos, otros son chispeantes.

Some programs are elegant, some are exquisite, some are sparkling. _¡Mi afirmación es ue es posible escribir grandes programes, programas nobles, algunos realmente magníficos!_

  
**Gusto y Estilo**  
  


La idea del _estilo _en programación está apareciendo al fin, y espero que muchos de ustedes ya han visto el excelente pequeño libro sobre _Los Elementos del Estilo de Programación, de _Kernighan and Plauger. En esta conexión es importante para todos nosotros recordar que no hay un "mejor" estilo, todos tienen sus propias preferencias, y es un error tratar de forzar a la gente a adaptarse aun molde no natural. A menudo escuchamos decir, "No se nada sobre arte, pero sé lo que quiero." Lo importante es que a tí realmente te guste el estilo que estás usando, debería ser la mejor manera en que prefieres expresarte.  
  


Edsger Dijkstra hizo hincapié en este punto en el prefacio a su _Corta Introducción al Arte de Programar:_

__

>   


> Es mi propósito transmitir la importancia del buen gusto y estilo en la programación, [pero] los elementos específicos de estilo presentados sirven sólo para ilustrar los beneficios que pueden ser derivados del "estilo" en general. Al respecto me siento afin al profesor de composición en el conservatorio: el no les enseña a sus pupilos como componer una sinfonía particular, el debe ayudar a sus pupilos a encontrar su propio estilo y debe explicarles las implicancias de esto. (Es esta analogía la que me hace hablar del "Arte de la Programación".)

Ahora debemos preguntarnos, ¿qué es buen estilo, y qué es mal estilo? No deberíamos ser demasiados rígidos sobre esto cuando juzguemos el trabajo de otras personas. El filósofo de principios del siglo diecinueve Jeremy Bentham lo puso de esta manera:

>   


> Los jueces de la elegancia y del gusto se consideran a si mismos como benefactores de la raza humana, cuando en realidad sólo son los interruptores del placer... No existe el gusto que merezca el epíteto de bueno, a menos que sea un gusto empleado de tal forma, que el placer actualmente producido por este, al unirlo con algo contingente o futuro sea de utilidad; no hay gusto que merezca ser llamado malo, a menos que sea un gusto ocupado para algo ue tenga una tendencia perjudicial

Cuando aplicamos nuestros prejuicios para "reformar" el gusto de alguien más, estamos inconcientemente negándole algo de su enteramente legítimo placer. Es por esto que no condeno un montón de las cosas que hacen los programadores, aunque nunca disfrutaría haciéndolas yo mismo. Lo importante es que ellos están creando algo que ellos sienten que es hermoso.

  


En el pasaje que he citado, Bentham nos da algunos consejos sobre ciertos pincipios de estética que son mejores ue otros, principalmente la "utilidad" del resultado. Tenemos algo de libertad al definir nuestros estándares personales de belleza, pero es especialmente agradable cuando las cosas que consideramos bellas son también consideradas por otra gente como útiles. Debo confesar que realmente disfruto escribiendo programas computacionales, y especialmente disfruto escribiendo programas que hacen el más grande bien, en algún sentido.  
  


Hay muchos sentidos en los cuales un programa puede ser "bueno", por cierto. En primer lugar, es especialmente bueno tener un programa que opera correctamente. En segundo lugar es a menudo bueno tener un programa que no sea dificil de modificar, cuand llegue el tiempo de las adaptaciones. Ambas metas se pueden lograr cuando el programa es facilmente legible y entendible por una persona que conoce el lenguaje apropiado.

  
Otra forma importante para que un programa en producción sea bueno es que interactúe  amablemente con sus usuarios, especialmente cuando se recupera de los errores humanos en el ingreso de los datos.  Es un real arte componer mensajes útiles o diseñar formatos de entrada flexibles que sean a prueba de errores.

  


Otro aspecto importante de la calidad de un programa es la eficiencia con la cual los recursos del computador son usados. Lamento decir que mucha gente en estos días están condenando la eficiencia de los programas, dicéndonos que es de mal gusto. La razón para esto es que ahora estamos experimentando una reacción al tiempo en que la eficiencia era el único criterio reputable de calidad, y los programadores en el pasado estaban tan preocupados con la eficiencia que produjieron código innecesariamente complicado, el resultado de esta complejidad innecesaria ha sido que la eficiencia neta ha disminuido, debido a las dificultadoes de depurar y mantener.

  


El problema real es que los programadores han gastado mucho tiempo preocupándose de la eficiencia en los lugares equivocados en los momentos incorrectos,** la optimización prematura es la raiz de todos los males **  
(o al menos de la mayoría de ellos) en programación.

  


No deberíamos recompensar al sabio y aporrear al tonto, ni estar pensando siempre en términos cuanto porcentaje ganamos o perdimos en el tiempo total de ejecución o espacio. Cuando compramos un auto, muchos de nosotros ignoramos una diferencia de $50 o $100 en el precio, mientras que si somos capaces de hacer un viaje especial a una tienda particular para comprar un objeto de 50 centavos, en oferta a 25 centavos. Mi punto es que hay un momento y un lugar para la eficiencia, he discutido su rol en mi artículo sobre la programación estructurada, que aparecerá en la edición actual de Compu_ting Surveys_ [Knuth, Donald E. Structured programming with go to statements. Computing Surveys 6 (Dec. 1974)].



