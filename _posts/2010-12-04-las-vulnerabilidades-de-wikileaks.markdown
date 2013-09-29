---
comments: true
date: 2010-12-04 15:16:39
layout: post
slug: las-vulnerabilidades-de-wikileaks
title: Actividades ilegales
wordpress_id: 1021
categories:
- Credibilidad
- Privacidad
- Seguridad
- Sociedad
- Tecnología
tags:
- Assange
- ciberguerra
- ciberterrorismo
- DDoS
- hackers
- PayPal
- política
- vulnerabilidades
- wikileaks
---

[![](http://www.lnds.net/blog/wp-content/uploads/2010/12/Logotipo_de_Wikileaks-199x300.jpg)](http://www.lnds.net/blog/wp-content/uploads/2010/12/Logotipo_de_Wikileaks.jpg)Aunque Wikileaks funciona desde 2006, los eventos recientes correspondientes a la filtración de mensajes diplomáticos desde las embajadas norteamericanas, le han significado no sólo una mayor publicidad, sino que una mayor cantidad de problemas técnicos, y una seria amenaza para la viabilidad del proyecto.

Hay tres aspectos de la infraestructura que sostiene Wikileaks cuyas vulnerabilidades se veían venir y que voy a analizar, para tratar de entender cómo pudo esta organización de hackers experimentados pudo ponerse en esta posición riesgosa.

Primero, ante un masivo ataque de denegación de servicio (DDoS), el equipo de Assange llevó parte de sus operaciones a los servidores en la nube de Amazon, pero en menos de 48 horas el servicio les fue revocado sin explicación alguna. La medida es controversial, pero podría tener justificación por parte de Amazon, en [la sección 3 del Customer Agreement](http://aws.amazon.com/agreement/#3), se mencionan las causales por las que Amazon puede cortar sus servicios (en particular el punto 3.4.1 (vii) me parece que aplica en este caso).

Bueno, en este caso aplican [las recomendaciones del World Privacy Forum](http://www.worldprivacyforum.org/cloudprivacy.html) de las que hablamos en marzo de 2009 cuando publiqué los [tips para usar cloud computing](http://www.lnds.net/blog/2009/03/tips-para-usar-el-cloud-computing.html):



	
  * Lea los Términos de Servicio antes de colocar cualquier información en la nube. Si no entiende Los Términos de Servicio, considere usar un proveedor de servicios diferente.

	
  * No ponga nada en la nube que no quiera que sea visto por el gobierno o algún litigante privado.

	
  * Asegúrese que no está violando alguna ley o política, al colocar datos en la nube, y pienselo dos veces antes de poner datos de los consumidores en la nube.

	
  * Lea la política de privacidad antes de colocar su información en la nube. Si no entiende la política, considere usar un proveedor diferente.

	
  * ¿El proveedor de servicios le da avisos anticipados sobre cualquier cambio de los términos de servicio o la política de privacidad?


Yo no habría publicado la información de Wikileaks en la nube de Amazon, porque lo más probable es que recibieran alguna notificación del FBI o el gobierno norteamericano solicitando la suspensión del servicio.

El segundo aspecto tiene que ver con el DNS. Wikileaks.org estaba registrado en [EveryDNS](http://www.everydns.com/). Este servicio informó el 3 de diciembre que suspendería el servicio a Wikileaks ante los ataques al servidor de nombres que afectarían a otros 550.00 dominios.

Los ataques a los servidores de nombres es otra de las armas del arsenal hacker que quiera perjudicar a un sitio como Wikileaks, todo experto en seguridad informática te dirá que si se quiere voltear a un sitio como Wikileaks, lo primero es denegar el servicio a los servidores web, y lo segundo es atacar a los DNS.

Todos los elementos externos, no controlados directamente por Wikileaks, son blancos seguros de estas actividades ilegales. Porque un ataque de este tipo es un acto ilegal, que se da para perjudicar un negocio, o  en casos de ciberterrorismo, la única otra "justificación" sería una acción de [ciberguerra](http://en.wikipedia.org/wiki/Cyberwarfare), pero esta última se da sólo entre paises en conflicto (reales o guerras frias, como en algunos incidentes entre China y USA, en BieloRusia, Corea y otros).

Pero la tercera vulnerabilidad se [reveló hoy](http://thelede.blogs.nytimes.com/2010/12/04/paypal-suspends-wikileaks-account/), y también es perimetral, y tiene que ver con cortar el financiamiento de Wikileaks.  Paypal en [su blog oficial declara que](https://www.thepaypalblog.com/2010/12/paypal-statement-regarding-wikileaks/):


> Paypal ha restringido permanentemente la cuenta usada por WikiLeaks debido a una violación de la Política Aceptable de Uso de Paypal, que dice que nuestro servicio de pago no puede ser usado para cualquier actividad que anime, promueva, facilite o instruya a otros a participar en una actividad ilegal.


Y ahí están nuevamente los términos de servicio, PayPal es una parte importante de la infreaestructura de los nuevos servicios en la nube, y hay que leer sus contratos,  no es sorpresa que estas empresas ante este tipo de problemas van a suspender rápidamente los servicios ante este tipo de situaciones, que puede que no nos gusten políticamente hablando, pero no son reprochables, los términos son claros y sabemos que si queremos montar algo como Wikileaks basado en este tipo de servicios de cloud computing es muy probable que tengamos serias dificultades.

Estos son sólo tres aspectos, no quiero meterme en las vunerabilidades más duras tecnicamente. Lo que me extraña, que siendo Assange un hacker tan connotado haya optado por confiar en servicios en la nube, para sostener a WikiLeaks,  a menos que sea otro astuto hackeo político que pretenda poner en evidencia la fragilidad de la infraestructura de la nube ante situaciones que incomodan a los más poderosos (¿serán tan astutos como para eso?).
