---
comments: true
date: 2005-11-08 20:56:55
layout: post
slug: linuxlupper
title: Linux/lupper
wordpress_id: 175
categories:
- Seguridad
---

Bueno, el nuevo gusano para linux esta explotando las vulnerabilidades de [XML-RPC ](http://www.securityfocus.com/bid/14088/)que se conocen desde hace bastante tiempo.

Afecta a sitios con Drupal, WordPress, Xoops y en general casi todo lo que tenga PHP y XML-RPC no actualizado.

La mejor forma de comprobar si se está infectado es observar la existencia del fichero /tmp/lupii, así como de un puerto UDP 7222 a la escucha, donde el gusano abre una puerta trasera...

[Via Kriptópolis.](http://www.kriptopolis.org/node/1355)

Una nota histórica, el primer gusano conocido de internet fue creado por Robert Morris en 1988 y afectaba sistemas Unix.

Un gusano el Linux es crítico dada la gran cantidad de servidores instalados, de hecho Linux+Apache domina en las configuraciones de servidores. Las configuraciones LAMP (Linux Apache MySql PHP, o Linux Apache Mysql Perl) son la más popular para los los sitios web.

Si no tienes control de tu servidor exige a tu proveedor de internet que mantenga actualizado el servicio.

Lamentablemente hay muchos administradores que no se preocupan de mantener sus sitio asegurados, también es cierto que en muchos casos incorporar un nuevo parche puede provocar problemas laterales.

Como ven, los bugs están en todo tipo de software, sea libre, abierto o cerrado. La calidad es la asignatura pendiente que tenemos los desarrolladores de software.



