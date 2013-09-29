---
layout: post
title: "Expectativas"
date: 2013-03-23 10:20
comments: true
categories: 
- Desarrollo
- Ingeniería de Software
- Arquitectura
- Metodología
---

{% blockquote Steve Jobs, WWDC 1997 %}
"You‘ve got to start with the customer experience and work back toward the technology - not the other way around." 
{% endblockquote %}

Casos de Uso, les cuento lo que pensaba una amiga de los casos de uso. "Esha" es argentina, ¿viste? En una ocasión me contó un típico diálogo con uno de sus programadores: "¡Che! y le pregunto que cómo era posible que una factura tuviera fecha de vencimiento menor a la fecha de emisión, y ¿sabés que me contesta el boludo? ¡Que esa situación no estaba contemplada en el caso de uso! ¡¿Sabés que podés hacer con tus casos de uso?! le contesté…"

{% img center /blog/images/2013/03/usuaria.jpg %}

:-) Suele suceder, con bastante frecuencia en realidad, hasta yo mismo en alguna ocasión he usado ese argumento, si no está en el caso de uso, entonces no tiene por que estar implementado, ¿verdad?

Pues no es así, y ese es el gran problema con la toma de requerimientos. Siempre partimos de la base de preguntarle al usuario qué quiere, que desea que le "construyamos". Cuando en realidad deberíamos tratar de comprender que es lo que **espera** del sistema.

¿Cómo es eso? ¿No son los requerimientos lo que espera el usuario del sistema? ¿Y no se refleja eso en los casos de uso?

<!-- more -->

**¿Qué quieren los usuarios?**

{% blockquote  Steve Jobs http://www.inc.com/magazine/19890401/5602.html "An interview with Steven Jobs, Inc.'s Entrepreneur of the Decade, Abril 1989" %}
You can't just ask customers what they want and then try to give that to them. By the time you get it built, they'll want something new.
{% endblockquote %}

Algo de razón tenía  Steve Jobs cuando dijo que cuando le preguntas a tus clientes que quieres y tratas de dárselos, en el momento que lo hayas construido ya quieren algo nuevo. Es una rueda sin fin en la que nos involucramos desarrolladores y usuarios, nunca parecen alinearse las expectativas con los resultados.  ¿Qué es lo que falla entonces? ¿Cómo solucionarlo?

{% img center /blog/images/2013/03/todopoderoso.jpg %}

> Bruce: Eran tantos. Sólo les di lo que querían.
>
> Dios: Sí. Pero, ¿desde cuando alguien tiene idea de lo que realmente quiere?
>
>               -- Jim Carrey y Morgan Freeman en Todopoderoso

El enfoque tradicional, la aproximación al desarrollo en cascada, recoge los requerimientos y trata de plasmarlos a través de una cadena de actividades meticulosamente detallada y documentada:  Toma de Requerimientos -  Análisis Funcional - Análisis No Funcional - Diseño General - Diseño de Detalle - Diseño de Arquitectura  - Programación - Diseño de Pruebas - Pruebas Unitarias - Pruebas de Integración - Pruebas de Aceptación de Usuario - Correcciones - Paso a Producción.

Cuando al fin logramos de pasar a producción ya nadie quiere el sistema, y a veces termina siendo descartado. Con el tiempo se convoca un nuevo proyecto, o entramos en un eterno ciclo de "mantenciones".

**La respuesta ágil**

Ante esta situación la respuesta del movimiento ágil es privilegiar las interacciones entre los individuos, por sobre los procesos y las herramientas.

La propuesta ágil es agnóstica a la tecnología, no es relevante, lo que importa es satisfacer el requerimiento. La idea es la siguiente: el usuario no tiene claro que desea, nosotros tampoco, así que descubrámoslo en el hacer. Construyamos una funcionalidad, e iteremos. La cascada desaparece, aparece un molino de agua: recoger funcionalidades, priorizarlas e iterar, mejoras sucesivas hasta que descubramos juntos lo que se necesita.

{% img center /blog/images/2013/03/molino-de-agua.jpg %}


Lo que importa en el manifiesto ágil es el hacer: "Working Software". Pero ahí parten los problemas, esta solución privilegia el "Working Software"(software funcionando), pero no habla del "Usable Software" (software útil).

El agilismo es esencialmente reactivo. Propone colaboración con el cliente, "responder al cambio por sobre seguir un plan". Construimos software, el usuario lo prueba, no es lo que esperaba, iteramos nuevamente….

{% img center /blog/images/2013/03/Scrum.png %}


No es que esté en contra del movimiento ágil, pero después de años de intentar adherirme a sus principios, y observando los resultados obtenidos, creo que le falta algo. Llevo tiempo   reflexionado al respecto y creo que he visto algunas de las falencias de esta aproximación, y algo de eso es lo que intento explorar en este texto.  
 
**Requerimientos vs Expectativas**

Si se fijan todas la metodologías tienen que ver con cómo plasmar los requerimientos del cliente en un producto. En términos simples, todo se trata de elaborar una lista de lo que tenemos que hacer y después hacerlo. El orden, la forma en que nos aproximamos es la que varía, ya sea que ejecutemos las tareas en forma secuencial una tras otra, de forma iterativa incremental, o de forma reactiva, como se propone en las formas más extremas de agilismo.

Lo que yo digo es que el problema no está tanto en la forma, sino en el fondo. El problema es que todas esta metodologías tratan sobre el manejo de los requerimientos, cuando en realidad deberían preocuparse del manejo de las expectativas.

¿Cómo es eso?


{% pullquote %}

Una expectativa no es un deseo casual, es algo tácito que va más allá de los supuestos conscientes, es algo que reside parcialmente en el inconsciente del usuario. 

{" "Muchos usuarios pueden expresar lo que quieren, algunos pueden justificar sus necesidades, y cuando usan tu producto todos pueden decirte si este hace lo que ellos esperaban" "}[1]


En muchos proyectos se elaboran listas de funcionalidad potenciales, elegidas y motivadas por la visión de negocios de que es lo que el cliente está dispuesto a pagar (o sea, lo que el cliente quiere). Esta descripción por si misma no nos dice mucho sobre cómo serán usadas estas funciones, o por qué se usarán.

{% endpullquote %}


Una lección que aprendieron los autores del libro [Lean Architecture](http://amzn.to/11uAEJX) fue la siguiente:

{% blockquote %}
"Aprendimos una lección sobre las expectativas de los usuarios a partir de un cliente nuestro. El cliente construye sistemas de análisis de ruido para todo tipo de artefactos, desde automóviles hasta aspiradoras. Algo que aprendimos que sus clientes productores de aspiradoras insistían en que una buena aspiradora hace un ruido sustancial cuando está trabajando a tope. Para el mercado alemán este ruido debe ser un rugido grave, para otros mercados un chillido agudo. La meta no es minimizar el ruido, a pesar de que es posible construir aspiradoras bastante silenciosas sin reducir su efectividad.
{% endblockquote %}

**Anticipación**

Uno de los problemas con la toma de requerimientos es que no es posible anticipar todos los escenarios que pueda concebir un usuario. Así que debemos profundizar en la percepción del usuario sobre la forma del sistema. Esto se conoce como el **modelo cognitivo del usuario final**.

"Los casos de uso	capturan las interacciones con el sistema que los usuarios finales pueden anticipar. Si los usuarios finales pueden anticipar todas las interacciones para todos los valores posibles de entrada, entonces la especificación es completa. Esto hace que construir el programa sea innecesario porque hemos delineado toda posible respuesta a partir de toda posible entrada, y bastaría con revisar la respuesta en las especificaciones en vez de ejecutar el programa. Por supuesto, esto es absurdo. Los buenos sistemas de software tienen valor porque pueden, hasta cierto grado, manejar lo no anticipado."[1]

Supongamos que nos piden construir un procesador de textos. Un requerimiento sería poder mover una tabla dentro del documento. Veamos posibles escenarios o casos de uso posibles: mover la tabla de una página a otra; mover la tabla justo entre dos párrafos ya existentes; o mover la tabla dentro de otra tabla. Las posibilidades son interminables. ¿Cómo abordamos eso con el enfoque tradicional de casos de uso?

En vez de eso, es mejor orientar nuestros esfuerzos a definir algo más importante: el modelo cognitivo del usuario final. Los usuarios tienen modelos en su cabeza de los detalles internos del programa que utilizan. Confían que el programa "sabe" qué es una tabla, un párrafo, una figura, etc. El usuario confía en que los programadores han prestado atención a la necesidad de que haya un espacio en blanco entre la tabla y los párrafos adyacentes. Estos elementos del modelo mental del usuario final, aunque sean estáticos, son útiles para poder razonar sobre los posibles escenarios que modelamos en los casos de uso.

En el caso que les relaté al principio, el de mi amiga y sus sistema de facturación, la falla está en que el requerimiento no capturó adecuadamente el modelo mental del usuario, "en una factura la fecha de vencimiento no puede ser menor a la fecha de emisión", esto es algo evidente, pero por eso mismo es muy raro que vaya a surgir de una toma de requerimiento, es algo que suponemos que el desarrollador domina, o que al menos ha investigado.

Este modelo cognitivo debe capturarse dentro de la arquitectura de la solución. Si lo capturamos bien, podemos garantizar que podremos satisfacer lo que el usuario quiere y necesita, pero de paso haremos nuestra solución más resiliente cuando nos pidan implementar un escenario razonable pero no anticipado.

**Problemas y Soluciones**

Jerry Weinberg define problema como "la diferencia entre el estado actual y un estado deseado". Así que cuando vamos a enfrentar un desafío de programación (sea una simple rutina, o un sistema completo), debemos empezar por aclarar la noción de qué queremos resolver. Teniendo clara esta noción sabremos que significa que algo esté listo (done). 


{% blockquote %}
"Sin una definición del problema, es difícil saber cuando has terminado. Claro, puedes señalar una lista de tareas que has completado y que fueron diseñadas inicialmente para acortar la brecha entre el estado actual y el estado deseado, pero eso no significa que hayas terminado. Los requerimientos emergentes provocan que el paisaje se desplace durante el desarrollo, y aún así los caminos mejor planeados no te llevan a los destinos mejor concebidos." [1]
{% endblockquote %}

A esto lo llamamos *visión*. La visión es la brújula que nos guía. ¿Por qué estamos haciendo lo que estamos haciendo? Esa es la pregunta esencial que debe hacerse el buen ingeniero.

La visión también ayuda a entender mejor las expectativas del usuario.

Recientemente leí este tweet:

{% blockquote @ideasagiles https://twitter.com/ideasagiles/status/313618318844121088 %}
Insumir mucho tiempo pensando como soportar una carga grande de usuarios sin siquiera haber lanzado el producto, es una pérdida de tiempo.
{% endblockquote %}

¿Qué significa esto a la luz de lo que estamos discutiendo? Sin tener claro cuál es la visión, puede tener mayor o menor sentido. Claramente pesa la visión del hacer y reaccionar del agilismo. Que está bien, después de todo lo importante es salir con el producto. Pero, ¿y si el  cliente, esperaba que el sistema soportara una carga grande de usuarios desde el principio?

El modelo ágil tradicional (Scrum, por ejemplo) privilegia el "hacer y reaccionar". Hay otra manera de abordarlo (Lean), que privilegia el pensar y luego hacer.

Ese es el modelo que es mejor, en mi opinión. Pero sin llegar al extremo de pensar demasiado y no hacer nada. Pasar 3 meses diseñando un sistema no lleva a ninguna parte.

Eso es algo que debemos recuperar, y que parece haberse perdido en el agilismo. Pensar, luego hacer, por sobre el hacer y reaccionar. Software útil (usable software) más que software funcionando (working software).

**Prácticas Perdidas**

Muchos al abordar metodologías ágiles piensan que se trata de botar todo lo "desagradable", cosas como arquitectura, documentación, análisis funcional, deben quedar fuera. Como si se tratara de traer un Scrum Master o algo similar que toque el tambor, y poner a  usuarios y desarrolladores a iterar juntos hasta sacar algo mínimamente aceptable. Después de todo, se trata de "individuos e interacciones por sobre procesos y herramientas".

El agilismo tiene la virtud de ser probablemente el primer movimiento en el desarrollo de software que introdujo un conjunto maduro de disciplinas. Lamentablemente, en el camino mucha experiencia ganada, que no estaba en este conjunto de disciplinas se fue perdiendo, o la fuimos considerando como irrelevante, y no lo son.

Hay que recuperar esas prácticas perdidas. ¿Cuáles prácticas? me preguntarán, bueno, de eso vamos a hablar en los próximos posts ;-)

{% img center /blog/images/2013/03/camino.jpg %}

**Notas**

[1] [Lean Architecture, for Agile Software Development](http://amzn.to/11uAEJX), James Coplien & Gertrud Bjornvig.