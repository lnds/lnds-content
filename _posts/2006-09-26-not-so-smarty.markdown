---
comments: true
date: 2006-09-26 20:24:38
layout: post
slug: not-so-smarty
title: Not so Smarty
wordpress_id: 2091
categories:
- Sin categoría
---

Ricardo Galli [tiene razón](http://web.archive.org/web/20090426081006/http://mnm.uib.es/gallir/posts/2006/09/26/820/), si usas [Smarty](http://web.archive.org/web/20090426081006/http://smarty.php.net/), el impacto en el desempeño es alto. He leido por ahí que Smarty es eficiente, pero seguramente hay que ser un gurú del mismo para lograr lo prometido.

En el caso de Blogmemes, el 80% del tiempo de rendering de una página se consume en Smarty, y estoy hablando sólo de tiempo en el servidor. Este es un problema que he postergado por falta de tiempo, y porque el tráfico de blogmemes no lo justifica. De todas maneras afecta la experiencia usuario, y quizás haya que "entrar a picar".

Internamente, en la Red Blogmemes estamos trabajando en el diseño una nueva versión de [akarrú](http://web.archive.org/web/20090426081006/http://trac.blogmemes.com/trac_script), pero creo que se hace necesario que liberemos una versión nueva pronto, porque bastante polvo tiene acumulado el último release.

El objetivo principal será optimizar el uso de plantillas, porque además del problema de desempeño hay muchos usuarios que se enredan con la configuración de Smarty. Creo que además akarrú debe mejorar su mecanismo de instalación.

Una vez que todo esto esté listo les comunicaremos el cambio, y espero que los usuarios de [BlogMemes ](http://web.archive.org/web/20090426081006/http://www.blogmemes.com/)lo noten, y lo agradezcan.


