---
comments: true
date: 2010-08-21 17:15:53
layout: post
slug: historias-de-depuracion
title: Historias de depuración
wordpress_id: 670
categories:
- Desarrollo
- La Naturaleza del Software
tags:
- Depuración
- desarrollo
- experiencia
- historias
- programación
---

La mejor herramienta de depuración de un programa (debugger) es la mente. Aunque el oido también sirve.

![](http://www.lnds.net/blog/wp-content/uploads/2010/08/debugger-300x242.jpg)

Una vez un amigo programador tenía un problema con dos procedimientos almacenados. Ambos eran casi idénticos, la diferencia estaba sólo en la fuente desde donde obtenían información, el algoritmo era el mismo. El primero entregaba la respuesta extremadamente rápido, y el otro se demoraba una eternidad. El programador llevó una copia de la base de datos a su PC y empezó a depurar. Cuando me puse a ayudarlo noté algo, al ejecutar el procedimiento con problemas el  computador se ponía ruidoso. "¿Por qué suena tu computador?" "Porque se activa el ventilador". "Sí, pero hay algo más". Efectivamente, el disco también sonaba porque empezaba a girar más de lo normal. Con el procedimiento almacenado más rápido no había ruido alguno y el disco apenas se movía. Ese ruido nos llevó a la pista correcta, el problema estaba en la tabla principal usada por el segundo procedimiento, que era el principal cambio entre uno y otro. Al principio pensamos que tenía más datos, pero no, lo que pasaba es que le faltaba un índice. Esa fue la primera vez que depuré de oido.

La otra historia que tengo para contarles es más épica ;)

Hace años, teníamos un contrato para implementar un sistema "hot backup". Era un trabajo poco frecuente y desafiante, este módulo era una pieza  auxiliar de un sistema [SCADA ](http://es.wikipedia.org/wiki/SCADA)más grande.

El contratista principal, y desarrollador del sistema SCADA, había colocado el producto como sistema de control de una planta automatizada de cementos en  Talcahuano. Como parte del servicio se incluía nuestra componente de hot backup, lo que garantizaba la tolerancia a fallas.

Este módulo _"hot backup"_ fue un bonito desafío técnico. El sistema se implementaba en una modalidad  activo/pasivo, es decir, se instalaba en dos instancias sobre servidores distintos. El módulo hot backup monitoreaba el servidor activo, se preocupaba de mantener sincronizada  la base de datos en tiempo real entre ambos servidores, y cuando el servidor principal fallaba, se encargaba de activar al segundo servidor y dejarlo operando en el mismo estado que tenía el principal antes de fallar.

Yo estaba a cargo del desarrollo. Fueron varios meses de programación  en C++, y bastante investigación. Todo lo que aprendí de sistemas distribuidos en la escuela lo apliqué en ese proyecto, y de paso aprendí varias cosas más.

El problema es que desde Talcahuano reportaban que el Sistema SCADA "se caía" ante una demanda alta y activando el sistema secundario, sin una razón que lo justificara. Las sospechas cayeron sobre mi módulo hot backup. Montamos un laboratorio y llegué a la conclusión que no había nada malo en mi código. Como no nos creyeron, fuimos a una reunión con el gerente general de la empresa contratista,  insistimos que no era culpa nuestra, y que el problema estaba en el SCADA. Llegamos a un acuerdo, yo acompañaría a un ingeniero del contratista a Talcahuano, deberíamos investigar en terreno las causas. Si el problema era nuestro lo corregíamos sin costo, si el problema era del SCADA el contratista nos pagaba todas las horas ocupadas a tarifa doble. Literalmente era un doble o nada. Mi gerente, socio y amigo me dijo que ponía toda su confianza en mí, pero estaba preocupado. Podría significar perder mucho dinero.

Nos dieron dos semanas para encontrar la causa y resolver el problema. Viajamos a Talcahuano, nos instalamos en la planta.  Decidimos agregar diversos logs en distintas partes de nuestro código para detectar el problema. Casi todos los días hacíamos algún cambio. Aprovechabamos de depurar y corregir otros detalles menores. Sin embargo, pasaban los días, y el sistema no fallaba y no conseguíamos reproducir la situación (no podíamos simular nada, debíamos esperar que el fenómeno ocurriera).

Antes de seguir, déjenme contarles como funcionaba la planta. Esta era una planta totalmente automatizada que preparaba sacos de cemento _"just in time"_,  es decir, según la demanda. El cemento estaba en silos. El sistema SCADA permitía que un operador eligiera los silos fuente, y la cantidad de sacos a producir. Apretaba un botón y se activaban las máquinas, el cemento empezaba a desplazarse por correas transportadoras desde los silos hasta llegar a un robot ensacador. En realidad era una maravilla tecnológica, y nos gustaba ver como el sistema controlaba esas máquinas, software escrito por un grupo de jóvenes ingenieros, con los que trabajé varios meses. El módulo que elegía la ruta más óptima para mover el cemento fue escrito por uno de mis socios, así que también era un orgullo para mí.[![](http://www.lnds.net/blog/wp-content/uploads/2010/08/planta.jpg)](http://www.lnds.net/blog/wp-content/uploads/2010/08/planta.jpg)

Faltaban dos días para que se cumpliera el plazo, y estábamos frustrados. Ese día nos quedamos hasta mas tarde, notamos que empezaban a llegar varios camiones a la planta, lo que significaba que el sistema sería usado con mayor intensidad. Llegó el operador del turno de la noche, un hombrón, con unas manotas que no parecían adecuadas para manejar el mouse. De hecho, días antes le habíamos enseñado a usar adecuadamente el mouse, porque tenía serios problemas con la motricidad fina. Era uno de los obreros reconvertidos para operar la planta. Una buena persona, inteligente, con muchas ganas de aprender e iniciativa. Nos quedamos para ayudarle, porque se veía que sería una noche de mucho trabajo. Claro, esta caravana de camiones llegaba cada dos semanas, y el problema se había reportado que ocurría con esa frecuencia, así que también era nuestra esperanza de observar el bug.

De repente notamos que el operador empezaba a programar una gran cantidad de cargas. Un click tras otro, en rápida secuencia. Y ahí, frente a nuestros ojos, el servidor principal se cae, y empieza a operar mi módulo hot backup, tomando el control y activando el secundario. "Ahí está, ¿vé? así se cae".  Pasaron los segundos y el segundo servidor tomaba el control, pero algunas de las tareas programadas no estaban, se habían perdido.

Nos fuimos de cabeza a los logs. Los empezamos a revisar, y empecé a sentirme aliviado, y mi colega preocupado. El problema no estaba en mi código. Una [race condition](http://es.wikipedia.org/wiki/Condici%C3%B3n_de_carrera) en el código del SCADA se daba cuando este operador empezaba a sobre exigir el sistema. ¿Y los registros que se perdían? tampoco era problema del hot backup, una cola mal programada que se usaba de buffer antes de cargar la base de datos de tiempo real, por lo tanto no podía copiarlo al segundo servidor si no tenía acceso a esos datos aún.

Volvimos a Santiago. Yo contento, y mi colega con el rabo entre las piernas. Nos reunimos con el gerente contratista, yo con mi informe, y mi socio con la factura. Estaba feliz.
