---
comments: true
date: 2009-03-20 23:26:10
layout: post
slug: una-api-no-es-codigo-abierto
title: Una API no es código abierto
wordpress_id: 278
categories:
- La Naturaleza del Software
- Opensource
- Paradigmas
tags:
- API
---

Leo en un [apunte de Micronauta](http://blog.canal.cl/2009/03/y-dale-con-que-va-morir-el-diario.htm) la afirmación: "el triunfo total del código abierto, una tendencia en la cual la liberación de APIs que estamos observando por estos días es un eslabón fundamental.". Esta frase es el resumen de un [texto en inglés](http://xark.typepad.com/my_weblog/2009/03/news-futures-a-whats-next-overview.html) que dice:

  


> **Open Source wins**. Open Source solutions and platforms will push proprietary systems to the brink simply because of the rate at which they adapt to change and innovation. Pay attention to the Big Media attempt to monetize this Open Source principle through the proliferation of news APIs, but don't expect it to succeed unless these APIs give developers and end-users more freedom.

  


¿De qué estamos hablando acá?

Hay varias confusiones en estas afirmaciones.

Primero, las API, que son algo viejisimo, no hay nada innovador en este concepto, el hecho de que los usuarios periodistas las hayan descubierto hace poco, no las hace innovadoras.

Segundo, ¡las API nacieron precisamente para esconder el código, no para hacerlo abierto!.

La frase "el código abierto va a triunfar", es linda, y puede ser que llegue a suceder, pero eso no tiene que nada que ver con la proliferación de las API.

Eso es , dirían [Les Luthiers](http://www.youtube.com/watch?v=LWmQXz361dw), razonar fuera del recipiente.

Las API son mecanismos de abstracción, en que publicamos una interfaz que nos permite operar con un sistema, cuya implementación no nos interesa.

Por eso que podemos distribuir una biblioteca, o un sistema, sin necesidad de publicar su codigo fuente, bastando la publicación de su interfaz pública, una API.

Un caso famoso es la API de Windows, los programadores usaron la API de Windows para desarrollar aplicaciones, sin necesidad de contar con el código fuente de Windows.

Pero publicar una API, no es y no tiene nada que ver con el código abierto.



