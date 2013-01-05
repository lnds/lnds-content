---
comments: true
date: 2006-09-07 00:10:55
layout: post
slug: graceful-degradation
title: Graceful Degradation
wordpress_id: 333
categories:
- Sin categoría
---

Después de [leer el excelente artículo](http://www.elfrancotirador.cl/2006/08/29/vivafirefox-%c2%bfpero-botando-plata/) de [Francotirador ](http://www.elfrancotirador.cl/)sobre la promoción de Firefox, me parece que aparte de promover el uso hay que despertar a los proveedores de servicios web chilenos. Que se den cuenta que hay muchos usuarios usando otros browsers distintos.

Hace poco, traté de pagar mis cuentas de electricidad y agua, en un popular sitio que da este servicio,usando firefox, y sencillamente no pude, el javascript no funcionaba.

Aunque Ajax ha revitalizado el uso de javascript, siempre ha habido una mala costumbre de los programadores de sobrecargar el evento onsubmit, o los onclick de los botones, en vez de usar el antiguo, pero siempre eficaz botón submit.

Hay varias maneras de solucionar estos problemas de compatibilidad, pero voy a sugerir dos.

La primera consiste en desarrollar considerando que hay una cantidad siempre creciente de usuarios que no usan internet explorer. Es de perogrullo, pero no se hace.

La segunda es degradar el sistema en forma elegante. Me explico, hay un principio en construcción de software, que se llama "Graceful Degradation":

> "Es la degradación de unl sistema de tal manera que este continúa operando, pero provee un nivel de servicios reducidos, en vez de dejar de prestarlos."

Por ejemplo, si javascript está deshabilitado, siempre puedes programar tu sitio para que funcione. De hecho, todo lo que se controla en el cliente se puede controlar en el servidor, en el momento del POST.

Este camino es mejor, pues no tienes porque estar al corriente de todas las nuevas capacidades de los browsers.  
Se puede alegar que significa más trabajo, pero hay ambientes, y frameworks para Java que pemiten despreocuparse de este problema, configurando adecuadamente (el mejoer ejemplo es ASP.NET).

Si uno ve los sitios de otros países, funcionan con Ajax, con distintos browsers, e incluso con javascript deshabilitado. Pero en Chile, los sitios de servicios (públicos y privados) dejan mucho que desear.



