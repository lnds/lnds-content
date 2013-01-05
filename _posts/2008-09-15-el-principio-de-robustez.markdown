---
comments: true
date: 2008-09-15 21:59:27
layout: post
slug: el-principio-de-robustez
title: El Principio de Robustez
wordpress_id: 1306
categories:
- General
- Internet
- La Naturaleza del Software
tags:
- internet
- Ley de Postel
- Postel
- principio de robustez
- RFC
- xml
---

En 1981 se publica uno de los documentos más importantes de la internet, el famoso RFC 793, que define el protocolo TCP, que es el principal protocolo de internet, y que es la base de la mayoría de los protocolos usados en la red.

En este documento Jon Postel escribe, lo que ha llegado a conocerse como el Principio de Robustez, o la Ley de Postel:


> Las implementaciones TCP deben seguir un principio genera del robustez: ser conservador en lo que haces, ser liberal en lo que aceptas de otros.




> TCP implementations will follow a general principle of robustness: be conservative in what you do, be liberal in what you accept from others.


Dependiendo de tu sistema valórico, encontrarás el consejo de Postel como algo bueno, e incluso recomendable para otros aspectos de la vida, no sólo en los protocolos de transmisión de datos.

[![](http://www.lnds.net/blog/wp-content/uploads/2011/01/300px-Jon_Postel.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/01/300px-Jon_Postel.jpg)

Este principio ha sido criticado por cierto, porque aparentemenente promueve una tolerancia pasiva, o por ser demasiado liberal, y eventualmente permite aplicaciones inseguras.

La verdad es que no era la intención de Postel ser demasiado permisivo con los protocolos, y decir que las validaciones no eran necesarias. Pero, efectivamente, el principio de robustez ha sido mal interpretado, y eso nos ha generado muchos problemas, principalmente con la seguridad de las aplicaciones.

Pero no hay que olvidar que el **principio de robustez tiene una mirada puesta en las necesidades de los usuarios finales**.

En la actualidad esto tiende a olvidarse, y muchos desarrolladores, sobre todo los más rígidos (y sobre todo los más jóvenes), exigen que se cumplan los estándares, sin ninguna excepción, aunque eso atente contra las necesidades de los usuarios.

Consideren el caso de HTML. ¡Un verdadero caos! hay cientos de implementaciones de HTML, con miles de bugs, parches y soluciones ad-hoc incrustadas en la web y en los navegadores de internet.

En algún momento se optó por establecer estándares basados en XML como la solución definitiva del problema, y con esto se quiebró la Ley de Postel.

XML es un protocolo estricto. En teoría un documento XML inválido no debe ser aceptado.  Pero habrán documentos inválidos, eso es casi inevitable.

Un ejemplo clásico es lo que pasa con la sigla "AT&T", de acuerdo a la especificación XML se debe escribir: "AT&amp;T", pero eventualmente alguien escribirá "AT&T". Las aplicaciones que privilegien los deseos de los usuarios y acepten documentos XML escritos en forma no tan estricta (piensen en los varios tipos de browsers disponibles), terminarán imponiéndose (porque son aplicaciones más robustas).

XML nos pide que rompamos el principio de Postel, XML exige que seamos intolerantes con lo que recibimos. Esto puede atentar contra las necesidades del usuario.

Ese es un problema que aparece también en protocolos como SOAP, y en general casi todas las recomendaciones de interoperatividad basados en estándares rígidos, como XML. "La ley de Postel no acepta excepciones", cuando vamos contra este principio el que lo paga eventualmente es el usuario.

¿Qué opinan ustedes? ¿conocen otras situaciones donde al tratar de romper este principio perjudicamos la experiencia del usuario?
