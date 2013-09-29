---
comments: true
date: 2010-03-11 19:41:24
layout: post
slug: internet-en-chile-ante-la-contingencia
title: Internet en Chile ante la contingencia
wordpress_id: 5
categories:
- Sociedad
- Tecnología
tags:
- BCP
- Chile
- DRP
- planes de continuidad
- terremoto
- tolerancia a fallas
---

Los principios de diseño de los protocolos de internet asumen que la infraestructura de red es inherentemente no confiable, y dinámica en términos de disponibilidad y nodos. Para poder reducir la complejidad de la red, la inteligencia se deja en las puntas ([la red es un mundo de extremos](http://www.lnds.net/2008/06/un-mundo-de-extremos.html)).

El protocolo IP no garantiza una calidad de servicio, ofrece el "mejor esfuerzo" por entregar la información. Y funciona bastante bien, gracias al concepto de packet switching, la idea de Leonard Kleinrock ([el niñito de 6 años  que quería comprar un condensador variable](http://www.lnds.net/2008/04/todo-por-un-condensador-variable.html)).

  


Funciona? Sirve ante situaciones de catástrofe, como el terremoto que tuvimos el otro día? Pasa la prueba? En teoría sí, pero ¿en Chile? Esa es [la pregunta que Jo Piquer se hace](http://dccuchile.blog.terra.cl/2010/03/10/terremoto-2010-%C2%BFinternet-resistio-bien-la-prueba/).

Jo dice:

> **No existe ninguna razón estructural o de fondo para que Internet falle globalmente en el país por falta de energía**: todos los datacenters donde operan los proveedores de Internet poseen sistemas de generación propia que debieran ser capaces de operar en forma autónoma por muchas horas (el ideal es que fueran varios días). La mayoría de estos centros funcionaron bien y resistieron el evento, de hecho, muy pocos servidores importantes se vieron afectados.

> Finalmente, la primera noticia de mi familia, y la primera forma de comunicación que me funcionó, fue con mensajes de texto entre celulares ¡vergüenza para Internet!
> 
> No sé qué fue lo que realmente ocurrió. **No hemos obtenido información oficial y nadie quiere aceptar lo que resulta obvio: Internet no respondió como esperábamos y la gran mayoría de los proveedores de Internet fallaron en proveernos un servicio confiable.** La mayoría de los servidores estaban funcionando, la mayoría de los enlaces desde esos servidores a sus proveedores estaban activos y operando, pero hubo prácticamente cero tráfico durante casi 6 horas. Los amigos extranjeros no pudieron acceder a ningún sitio en Chile. La mayoría de los chilenos no teníamos acceso a nada. Esto no tiene ninguna excusa: la telefonía es esperable que no funcione, pero Internet debió haber respondido primero.

La verdad es que no comparto muchas de sus opiniones. Primero porque las encuentro algo contradictorias, o poco claras. Pero no me parecen ciertas, algo exageradas incluso. Puede que desde el punto de vista académico estas opiniones sean razonables, pero desde un punto de vista ingenieril y práctico no.

En las estrategías de recuperación ante desastres existe un parámetro importante a definir: el [RTO (Recovery Time Objective)](http://en.bcmpedia.org/wiki/Recovery_Time_Objective_(RTO)) , que corresponde al  tiempo máximo aceptable que puede pasar antes que la falta de una función del negocio impacte severamente a una organización. Es el lapso y nivel de servicio dentro del cual un proceso de negocio debe ser recuperado después de un desastre. Se mide dsde el momento del desastre, e incluye el tiempo necesario para realizar las tareas necesarias para arreglar el problema antes de iniciar la recuperación, el tiempo de recuperación en si mismo y el tiempo necesario para comunicarlo a los usuarios.

¿Cuál es el RTO esperado para nuestra plataforma de comunicaciones a nivel nacional?

Con un terremoto grado 8.8 vamos a tener congestión de tráfico, y las comunicaciones van a fallar, pero después de pocas horas, tener una infraestructura a nivel nacional operando, en un gran porcentaje, debe ser nuestra prioridad.

Yo no sé si existe un RTO Nacional, pero creo que logramos un RTO bastante aceptable.

Por eso que no estoy de acuerdo con mi antiguo profesor, al contrario, yo creo que internet sí pasó la prueba. Al contrario de Jo, yo creo que internet sí pasó la prueba, dentro de un RTO razonable.

Pero además está el problema de la energí
a, que en teoría, según Jo, no tiene justificación alguna, salvo que él no considera los problemas logísticos.

Permitanme citar a [Pablo Bello](http://blogs.elmercurio.com/cienciaytecnologia/2010/03/11/los-servicios-de-emergencia-no.asp), el subsecretario de telecomunicaciones del gobierno saliente:

> "Hemos estudiado desastres de la magnitud de este terremoto en el mundo y en todos ellos se generaron los mismos problemas, incluso más graves que los que se produjeron en Chile. La infraestructura de telecomunicaciones se mantuvo en pie, pero fue el tema de la energía lo que ocasionó más dificultades".

>   

> 
> "El problema inicial -explica- fue la congestión de las redes. Eso provocó que las baterías de respaldo de las radiobases se agotaran más rápido. Una vez que se agotan las baterías de respaldo, comienzan a funcionar los grupos electrógenos, pero sólo un 30% de las radiobases cuenta con uno. Si pensamos que cada empresa tiene entre 1.500 y 2 mil radiobases, es inviable que todas cuenten con uno por la logística que implica", señala el subsecretario.

En los días posteriores al terremoto escuché historias de ingenieros trabajando en terreno que partieron de madrugada hacia el sur para trabajar y mantener operativa la red, con poca bencina, sin dinero, haciendo lo que hacemos los ingenieros: mantener la sociedad operando. Gente a la que había que llevarle dinero, comida, equipos de radio, y todo el soporte necesario para que pudieran trabajar en esas condiciones.

Así y todo la red de comunicacione resistió bastante bien. Sabemos que muchos no pudieron comunicarse, pero se pudo levantar la infraestructura, y ha resistido bastante bien ante las exigencias propias de esta situación catastrófica.

Lo mismo pudo haber pasado con algunos datacenters, es muy probable que haya sido muy dificil coordinar la recarga de los grupo electrógenos. Sabemos que algunos datacenters fallaron, e incluso que algunos quedaron inutilizables o destruidos. Pero la principal razón de falla (cuando la hubo, y eso hay que comprobarlo), fue la falta de energía.

El día sábado pude acceder a los datacenter donde se alojan los servidores de mi trabajo usando la internet desde la casa de mi madre, porque en la mía no había electricidad. Ningún servidor se re inició por falta de energía, todos operativos y visibles desde internet, todo anduvo bien.

Me gustaría escuchar la experiencia de otros ingenieros de sistemas, con sus datacenters, pero creo que, dentro de los parámetros de un plan de recuperación de destrastres, la infraestructura anduvo bastante bien.

  




