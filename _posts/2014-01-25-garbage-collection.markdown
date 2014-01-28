---
layout: post
title: "Garbage collection"
date: 2014-01-25 12:31
comments: true
categories: 
---

> “Logré el sueño de todo informático, dejar la informática”. 

Me contaron que la anterior frase se la escucharon a un profesional de más o menos mi edad, al parecer está muy contento con su actual trabajo y algo fastidiado de haber perdido tanto tiempo dedicado a la computación.

“Quiero reencantarme con la informática :/“, dice el tuit de una joven publicado hace un par de días, que apareció por mi timeline. 

Acá hay una alerta, una petición de ayuda, una persona que está con angustia vocacional. 

No me queda claro,  porque no la conozco y no la seguía en Twitter,  que es lo que está pasando. Puede ser el encuentro con la realidad del trabajo versus la idealización del mundo universitario. También puede ser el choque con la mediocre realidad de mucha de la informática nacional.

{% img center /blog/images/2014/01/giphy.gif %}

<!-- more -->

Supe el caso de cierta empresa, bastante conocida, que en vez de configurar los DNS y parametrizar las aplicaciones, para que usen nombres en vez de direcciones IP, se está desarrollando un script que recorra todos los archivos de configuración necesarios cambie las IP y re inicie los sistemas cada vez que haya un cambio de direcciones (!).

He visto cosas peores. 

Dice Aquiles en la Iliada

> “Igual lote consiguen el inactivo y el que batalla con denuedo. La misma honra obtienen tanto el cobarde como el valeroso. Igual muere el holgazán que el autor de numerosas hazañas. Ninguna ventaja me reporta haber padecido dolores en el ánimo”.

La mediocridad abunda. 

Yo creo que  es de pensamiento pequeño y egoísta aquel que actúa como la persona de la frase inicial de este post. Nunca debió haber estudiado computación, y causó más daño su presencia en el campo que aportes, así que es bueno que se haya ido, “vaya con Dios amigo”.
 
Por otro lado, son las personas que chocan con la mediocridad, con la rutina, los que necesitan reencantarse.

Si el trabajo vale la pena, si lo que haces tiene sentido, y estás con gente comprometida en el resultado, si te encuentras entre [constructores de catedrales](http://www.lnds.net/blog/2009/12/motivacion-personal.html) y no simple picapiedras, entonces trabajar será un agrado. 

Como [dije hace poco](http://www.lnds.net/blog/2013/11/satisfaccion.html), lo que buscamos como seres humanos es trascender. No queremos recompensas económicas tanto como ser reconocidos. 

Si tu trabajo no te da eso, entonces en vez de [quejarte](http://www.lnds.net/blog/2012/03/filoctetes.html), ¡[déjalo](http://www.lnds.net/blog/2009/03/nada.html)! 

Abandona el miedo. Twitter es el muro de los lamentos, deja de tuitear y hazte cargo de tu vida. No pidas que los demás te re encanten, ¡si la respuesta la tienes tu mismo! Hay muchos trabajos que valen la pena, que necesitan gente comprometida. Si realmente amas tu profesión, el trabajo adecuado aparecerá. 

Quizás no has encontrado el sentido a tu trabajo, a lo mejor no sabes por qué haces lo que haces. ¿Se lo preguntaste a tu jefe? Si él no sabe tampoco, entonces huye de ese sitio ¡por favor!

Para finalizar, y para dejarlos con algo más concreto, los voy a dejar con las palabras de uno de mis héroes personales, Donald Knuth:

> A veces nos asignan una tarea de programación que es casi irremediablemente aburrida, lo que no nos exige en absoluto nada de creatividad, y en esos momentos las personas suelen venir a mí y me dicen: “¿Así que la programación es hermosa? Está muy bien que usted declame que uno debería tener el placer de la creación de programas elegantes y encantadores, pero ¿cómo se supone que voy a hacer de este desastre una obra de arte? ”

> Bueno, es cierto, no todas las tareas de programación van a ser divertidas. Tengan en cuenta a la “ama de casa atrapada”, que tiene que limpiar la misma mesa cada día: no hay espacio para la creatividad o el arte en cada situación. Pero incluso en esos casos, hay una manera de hacer una gran mejora: todavía es un placer hacer trabajos de rutina, si tenemos cosas bellas para trabajar. Por ejemplo, una persona puede realmente disfrutar el limpiar la mesa del comedor, día tras día, si es una mesa hermosamente diseñada, a partir de madera de fina calidad.

> Por lo tanto, quiero dirigir mis palabras de clausura a los programadores de sistemas y los diseñadores de máquinas que producen los sistemas conque el resto de nosotros debe trabajar. Por favor, déjennos herramientas que sean un placer de usar, especialmente para nuestras tareas de rutina, en lugar de ofrecer algo con lo que tengamos que luchar. Por favor, déjennos herramientas que nos animen a escribir mejor los programas, mediante la mejora de nuestro placer cuando lo hacemos.

> Es muy difícil para mí convencer a jóvenes universitarios de que la programación es hermosa, cuando tengo que decirles que es como “slash slash JOB es igual a esto y esto”. Aún los lenguajes de control pueden ser diseñados de modo que sea un placer usarlos, en vez de ser estrictamente funcionales.

> Los diseñadores de hardware de computador pueden hacer que sus máquinas sean mucho más agradables de utilizar, por ejemplo, proporcionando aritmética de coma flotante que cumpla las leyes matemáticas simples. Las instalaciones disponibles en la actualidad en la mayoría de las máquinas hacen el trabajo de análisis de errores de manera rigurosa e irremediablemente difícil, pero las operaciones de diseño adecuado sería alentar a los analistas numéricos que proporcionaran una mejor subrutina que haya certificado la exactitud.

> Vamos a considerar también lo que los diseñadores de software pueden hacer. Una de las mejores maneras de mantener arriba el espíritu de un usuario del sistema es proporcionar las rutinas con las que se pueda interactuar. No debemos hacer que los sistemas sean demasiado automáticos, por lo que la acción va siempre detrás de las escenas, debemos dar el programador-usuario la oportunidad de dirigir su creatividad hacia canales útiles. Una cosa que todos los programadores tienen en común es que les gusta trabajar con las máquinas, así que vamos a mantengámoslo en el ciclo. Algunas de las tareas se hacen mejor con la máquina, mientras que otros se hacen mejor con la supervisión humana, y en un sistema bien diseñado se encuentra el equilibrio adecuado. 

{% img center /blog/wp-content/uploads/2011/01/knuth1.jpg %}

** Garbage collection **

Es bueno a veces hacer el ejercicio de recolectar basura espiritual. Voy a citar a uno de mis filósofos favoritos Cioran:

> …escribir, por poco que sea, me ha ayudado a pasar los años, pues las obsesiones expresadas quedan debilitadas y superadas a medias. Estoy seguro de que si no hubiese emborronado papel, me hubiera matado hace mucho. Escribir es un alivio extraordinario. Y publicar también. Esto les parecerá ridículo y, sin embargo, es muy cierto. Pues un libro es es vuestra vida, o una parte de ella, que os hace exterior. Se desprende uno de todo lo que ama y sobre todo de todo lo que detesta de uno mismo. 

> Iré más lejos, si no hubiese escrito, hubiera podido convertirme en un asesino. La expresión es una liberación. Les aconsejo que hagan el ejercicio siguiente: cuando odien a alguien y sientan ganas de liquidarle, cojan un trozo de papel y escriban que Fulano es un puerco, un bandido, un crápula, un monstruo. En seguida advertirán que ya lo odian menos. Es precisamente lo mismo que yo he hecho respecto de mi mismo. He escrito para injuriar la vida y para injuriarme. ¿Resultado? Me he soportado mejor y he soportado mejor la vida.

Así es, también me topo con mediocridad, con frustración, y aburrimiento. Mi solución, es hacer garbage collection de mi alma, como aconseja el bueno de Emile, escribiendo.

Ahora es tu turno, recolecta tu basura, y aléjala de tu mente y tu espíritu, para que enfrentes la vida con más energía.

Artículos relacionados:

- [Knuth responde a todas las preguntas](http://www.lnds.net/blog/2011/01/knuth-responde-a-todas-las-preguntas-2.html)

- [¿Qué es programar?](http://www.lnds.net/blog/2012/05/que-es-programar.html)

- [La práctica de la programación](http://www.lnds.net/blog/2007/07/la-practica-de-la-programacion.html)

- [Marte necesita mujeres](http://www.lnds.net/blog/2013/09/marte-necesita-mujeres.html)

- Por supuesto, la cuarta parte de mi libro [La Naturaleza Del Software](http://www.lnds.net/books/)
