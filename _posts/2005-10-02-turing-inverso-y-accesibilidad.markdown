---
comments: true
date: 2005-10-02 17:54:15
layout: post
slug: turing-inverso-y-accesibilidad
title: Turing Inverso y Accesibilidad
wordpress_id: 160
categories:
- Usabilidad
---

Los Test de Turing Inverso, o CAPTCHAS se han convertido en una desagradable práctica que espero desaparezca pronto.

La verdad, es que frente a varios CAPTCHAS me he sentido como un verdadero idiota, a tal grado que dudo si mi problema es mi [astigmatismo](http://es.wikipedia.org/wiki/Astigmatismo), o es que soy incapaz de reconocer imágenes.

En el [Factor Humano](http://www.webstudio.cl/blog/) hay un completisimo artículo sobre los CAPTCHAS desde el punto de vista de la accesibilidad:[http://www.webstudio.cl/blog/captchas-y-accesibilidad/](http://www.webstudio.cl/blog/captchas-y-accesibilidad/).

Hay otras maneras de combatir el spam. Si lo que te preocupa es la seguridad, los captchas no son para eso, como[explique anteriormente](http://www.lnds.net/archives/2005/08/no_comprometas.html),

De todas maneras, si lo que quieres es verificar que al otro lado hay un humano hay 2 maneras.

  * La más cara es usar biometría, sobre todo [biometría cancelable](http://www.lnds.net/archives/2005/10/biometria_cance.html).
  * La más barata, es que puedes usar los eventos de movimiento del mouse, por ejemplo puedes dibujar una matriz con números sobre celdas de colores y solicitar al usuario que haga click sobre uno de los números, o sobre una secuencia específica.

Uno de los mejores CAPTCHAS que he visto es, irónicamente, el usado por ese generador de SPAM, llamado BlogClicker. La imagen muestra el concepto:

![goodcaptcha.GIF](http://www.lnds.net/archives/goodcaptcha.GIF)

Este se mejoraría sin tener que distorsionar el número solicitado.

Es muy dificil para un script llegar a simular los clicks de un mouse (la verdad es que no se me ocurre como hacerlo, pero siempre hay hackers astutos).

De todas maneras yo creo que esta práctica debería desaparecer, lo que hay que hacer es buscar mejores maneras de asegurar la confianza de nuestros usuarios, con otros medios. Probablemente las nuevas ideas sobre [las leyes de la identidad ](http://www.identityblog.com/stories/2004/12/09/thelaws.html)nos lleven a impedir efectivamente el spam.



