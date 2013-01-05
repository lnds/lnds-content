---
comments: true
date: 2007-07-25 08:25:55
layout: post
slug: los-meta-sistemas-de-identidad
title: Los meta sistemas de identidad
wordpress_id: 337
categories:
- Identidad Digital
- Paradigmas
- Privacidad
---

  


[![](http://www.lnds.net/images/ID_Theft.jpg)](http://www.lnds.net/images/ID_Theft.jpg)_"Internet fue construida sin una manera de saber quien se conecta y a que se conecta."_

Dado que la capacidad de identificar a las personas no está construida en la internet todo aquel que ofrece un servicio en internet tiene que resolver el problema del manejo de la identidad e alguna manera. A medida que la web crece la necesidad de identificar se hace más necesaria, y siempre nos topamos con distintos tipos de verificación de identidad, cada uno creado y adaptado a distintas necesidades. Millones de personas han aprendido a aceptar que cualquier cosa que un sitio web les pida es la "forma normal" de conducir los negocios en línea. Han sido entrenados para ingresar sus nombres, claves secretas e información de identificación personal en cuanto formulario de entrada que se les presenta en pantalla.

Como resultado el estado actual de la identidad digital en internet es un conjunto de soluciones adhoc que lleva a que las personas tengan diversas experiencias de usuario en cada sitios web. Todo esto hace que el sistema como una totalidad se vuelva frágil y no permite la realización de la promesa del comercio electrónico (vease las [leyes de identidad](http://www.lnds.net/2007/04/las_leyes_de_la_identidad_2.html))

## Un meta-sistema de identidad

Dado que la adopción universal de un único sistema de identidad digital o tecnología es improbable, para tener una solución de uso amplio en la internet requerimos una aproximación distinta. Una que permita conectar los sistemas existente y futuros de identidad en lo que denominaremos un **meta sistema de identidad**. Este meta sistema, o sistema de sistemas permite fortalecer a los sistemas de identidad que lo constituyen. Permite la interoperabilidad entre estos, y habilita la creación de una interfaz de usuario consistente para todos. (ver: [La Visión de Microsoft para un Meta Sistema de Identidad)](http://www.identityblog.com/stories/2005/10/06/IdentityMetasystem.pdf).

La adopción de estos meta sistemas pueden hacer de internet un lugar más seguro e impulsar el comercio electrónico, combatir el phishing y resolver otros problemas asociados al manejo de la identidad.

En el mundo off line, la gente lleva consigo distintas formas de identificación en sus billeteras, como por ejemplo, su cédula de identida, licencia de conducir, tarjetas de crédito, tarjetas de fidelización o asociación a un club, tarjetas de viajero frecuente. La gente controla cual tarjeta usar y cuanta información revelera en cada situación

Del mismo modo el metasistema de identidad permite facilitar a los usuarios asegurarse y controlar el aceso a sus recursos en la internet. Permite que los usuarios seleccionen entre distintos portafolios sus identidades digitales y las usan en los servicios de internet de su preferencia donde son aceptados.

El metasistema permite que las identidades provistas por una tecnología o sistema de identidad sea usada en ambientes con tecnologías diferentes, siempre que exista un intermediario que entienda ambas tecnologías y en el cual se confíe para que haga las traducciones necesarias.

## Las identidades dependen del contexto

Las identidades de una persona en el mundo offline varían de las signicativas, como un certficado de nacimiento, pasaporte, o la licencia de conducir, a las más triviales, como las tarjetas de negocios o las de un club de lectores. Las persoans usan sus distintas formas de identificación en contextos diferentes donde son aceptadas. Las identidades pueden estar fuera de contexto, pero no generan el resultado esperado. Por ejemplo, tratar de usar la tarjeta del club de lectores para cruzar una frontera claramente está fuera de contexto. Por otro lado, usar una tarjeta bancaria en un cajero autmático, o un Pasaporte .Net en una cuenta hotmail es algo que claramente está en su contexto adecuado.

Muchas veces sin embargo la distición no es tan clara. Por ejemplo, en Chile el RUT, un número entregado por el gobierno, es usado como identificador para ser consultado en los sitios web bancarios.  
Esto trae una serie de problemas, sobre todo porque abre las puertas para cometer varios delitos.  
En este sentido el uso del RUT en nuestros sitios web bancarios es mala.

Por otro lado, aunque el Passport de Microsoft puede ser usado en cualquier sitio, e incluso es simple de usar si uno usa la plataforma .Net, su uso en otros sitios normalmente está deshabilitado, porque se considera que está fuera de contexto.

De hecho, los investigadores de Micro
soft, estudiando la experiencia de Passport y otros sistemas similares que irrumpieron en los primero años de la web, en conjunto con otros expertos de la industria establecieron una serie de principios que deben guiar a todos los sistemas de manejo de la identidad. Estos principios fueron compilados en las llamadas Leyes de la Identidad, expuestas por [Kim Cameron](http://www.networkcomputing.com/713/713f2CAMERON.html).

## Las leyes de la identidad

Las leyes de la identidad son los fundamentos para los meta sistemas de identidad.  
Las 7 leyes de la identidad son:

1. **Control y consentimiento del usuario**. Los sistemas de identidad sólo deben revelar la información identificando a un usuario con el consentimiento del usuario.  
2. **Acceso Mínimo para un Uso Limitado**. Un sistema de identidad debe revelar la mínima información posible.  
3. **Justificación de las Partes**. Los sistemas de identidad deben ser diseñados de modo que la información revelada esté limitada a las partes que tenga un lugar necesario y justificado en una relación de identidad.  
4. **Identidad Dirigida**. Un sistema de de identidad universal debe soportar ambos, _identificadores omnidireccionales_para uso de las entidades públicas e identificadores _unidireccionales_ para uso de las entidades privadas, facilitando el descubrimiento junto con prevenir las correlaciones innecesarias entre los identificadores.  
5. **Pluralismo de Operadores y Tecnologías**. Una identidad universal debe utilizar y habilitar la interoperación de distintas tecnologías de identidad provistas por multiples proveedores de identidad.  
6. **Integración Humana**. Los sistemas de identidad deben definir al usuario humano como una componente del sistema distribuido, integradod a trave´s de un mecanismo de comunicación humano máquina que no sea ambiguo y que ofrezca mecanismos de protección en contra de ataques en contra de la identidad.  
7. **Experiencia Consistente entre Contextos**. El metasistema que unifica la identidad garantiza a sus usuarios una experiencia simple, consistente mientras permite la separación de los contextos entre distintos operadores y tecnologías.

## ¿Que significa todo esto?

Cuando la identidad se lleva al mundo digital esta parece estar más en peligro que en el mundo real. La gente desconfía de los servicios que piden información de identidad. Muchos negocios no se realizan porque existe el temor de perder el acceso a las cuentas bancarias, o tarjetas de crédito.  
El aumento del phishing y otros mecanismos de fraude hacen que muchas personas desconfíen de los sistemas de identificación en la red.

En realidad muchos de los problemas se resuelven considerando que la identidad en linea no es distinta de la identidad en el mundo fuera de linea. Es cosa de darnos cuenta de que los mismos mecanismos que operan en el mundo offline son los que deben ser posibilitados en la internet.

Al igual que en el mundo real, uno sólo entrega su licencia de conducir a la autoridad y en una forma controlada y consentida. En el mundo digital uno debe entregar su identidad digital con las credenciales adecuadas en el contexto apropiado, pero de una manera controlada y consentida.

Por eso es que cuando entregamos nuestros datos a una institución no queremos que estos datos sean entregados sin nuestro consentimiento, y tampoco queremos que sean usados en formas no autorizadas.  
Estos principios han sido expuestos claramente por investigadores de punta, y existen muchos trabajos en este sentido para asegurar que las leyes de la identidad sean entendidas no sólo por los usuarios, sino por los implementadores de sistemas que manejan información sensible.   
  
Para los que desarrollamos sistemas que deben manejar datos personales, el trabajo de [Kim Cameron y su equipo en Microsoft](http://www.identityblog.com/?page_id=352) son una excelente guía para no perdernos en como proteger la identidad de nuestros usuarios y clientes.



