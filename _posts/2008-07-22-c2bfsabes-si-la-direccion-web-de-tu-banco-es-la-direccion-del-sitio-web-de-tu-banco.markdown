---
comments: true
date: 2008-07-22 22:08:43
layout: post
slug: '%c2%bfsabes-si-la-direccion-web-de-tu-banco-es-la-direccion-del-sitio-web-de-tu-banco'
title: ¿Sabes si la dirección web de tu banco es la dirección del sitio web de tu
  banco?
wordpress_id: 695
categories:
- Seguridad
tags:
- privacidad
- seguridad
- vuilnerabilidades
---

Probablemente un usuario novicio no sabrá cómo responder esta pregunta, pero si eres un usuario más avanzado me dirás que has revisado la barra de direcciones de tu navegador, que te has preocupado de no seguir un link que recibiste por email, o tuviste la precaución de escribir la dirección que te entregó tu banco, caracter a caracter, con mucho cuidado.

¡Es más! Te entregaron un aparatito, que te dijieron que está sincronizado con un super califragilistico mecanismo al que sólo accede un servidor de tu banco, y que asegura que, si alguien llegase a adivinar tu clave, el numerito mágico que este dispositivo te entrega impide que otro pueda ingresar al web del banco haciendose pasar por tí.

Estás tranquilo y seguro de que todo funciona, porque además tu proveedor de internet te ha prometido que se preocupa de tu seguridad, protegiendote para que no entren virus, bloqueando puertos que no vas a necesitar, y evita que te lleguen emails no solicitados, que podrían tratar de engañarte.

Pero tengo que decirte que todo eso es una falsa sensación de seguridad.

Porque intentar clonar un sitio web como el de tu banco es algo que un ladrón informático intentará hacer.

Me dirás que no pueden clonar la dirección web del banco, porque hay instituciones que se aseguran que funcione todo el sistema de nombres de dominio, para que nadie se adueñe de la dirección de otros.

Efectivamente, hay una enorme infraestructura montada sobre un servicio llamado [DNS](http://es.wikipedia.org/wiki/DNS) que permite que puedas llegar al servidor asociado a la dirección que ingresaste en tu navegador, y esas instituciones efectivamente se preocupan de que las direcciones sean entregadas a quienes corresponden.

Es un complejo servicio, que funciona muy bien, a una velocidad asombrosa y que permite que toda la web sea lo que es.

Pero esa maquinaria, tan compleja y maravillosa tenía (tiene) [un fallo en su diseño original](http://www.kriptopolis.org/fallo-critico-dns-obliga-parchear-internet), un error tan grande que ha sido manejado en secreto, y de forma coordinada por importantes firmas y proveedores de internet en todas partes del mundo, para que sea reparado antes de que algún delincuente haga uso de esta vulnerabilidad.

Porque esta vulnerabilidad permitiría engañar a tu computador, a tu navegador, y cualquier otros programa que use direcciones basadas en nombres, enmascarando un servidor fraudulento, redirigiendo el tráfico a donde no corresponde.

Las consecuencias serían muy graves, por eso que se ha hecho esta coordinación a nivel mundial.

Pero lamentablemente, [al menos en Chile](http://twitter.com/ryrys/statuses/863773077), y al parecer en [España también](http://www.kriptopolis.org/fallo-dns-todo-sigue-igual), nuestros proveedores de internet aún no han reparado el problema, a pesar de que tienen la solución desde hace semanas.

Algo que es tan urgente, aún no ha sido ejecutado, con la prontitud que esperaríamos, no sabemos las causas, pero creo que danlo mismo la razón de la demora, es obligación de los ISP brindar un servicio seguro que nos proteja de potenciales problemas como los descritos, o al menos si es cierto lo que ellos mismos dicen, de [que toman medidas, que atentan a la neutralidad de la red, para protegernos](http://blog.maz.cl/2008/06/el-silln-de-don-otto-y-la-neutralidad.html), entonces con mayor razón deberían demostrarlo parchando sus servidores DNS vulnerables.

¿Quieres saber si tu proveedor de internet se ha preocupado de reparar sus servidores DNS? visita esta [dirección](http://www.doxpara.com/), y presiona el botón que dice Check My DNS, esperemos que se pongan las pilas pronto nuestros proveedores de acceso, porque tenemos [razones para sospechar que pronto se empezará a hacerse mal uso de esta vulnerabilidad](http://www.kriptopolis.org/filtrados-detalles-ataque-kaminsky-dns).
