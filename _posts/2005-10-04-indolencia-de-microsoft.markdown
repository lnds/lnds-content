---
comments: true
date: 2005-10-04 20:27:37
layout: post
slug: indolencia-de-microsoft
title: Indolencia de Microsoft
wordpress_id: 2002
categories:
- Seguridad
tags:
- Microsoft
- vulnerabilidades
---

Esa parece que es la manera en que Microsoft trata sus problemas de seguridad.

Desde junio se conoce una vulnerabilidad descubierta por Secunia, que permite hacer spoofing y phishing usando java script.
Este esquema resume la vulnerabilidad.

1. El Usuario Visita un Sitio Malicioso
2. El usuario sigue un enlace confiable
3. Mientras tanto un sitio web malicioso abre una ventana popup delante del browser, haciendose pasar como una ventana del sitio confiable.

[![](http://www.lnds.net/blog/wp-content/uploads/2011/07/dialog_origin.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/07/dialog_origin.jpg)

Esto puede ser usado para hacer [phishing](/http://es.wikipedia.org/wiki/Phishing).

(Ver [prueba de concepto en Secunia.com](http://web.archive.org/web/20090426080911/http://secunia.com/multiple_browsers_dialog_origin_vulnerability_test/))

Mientras que Firefox resolvió el problema 1 mes despues en la versión 1.0.5, Microsoft recomienda a sus usuarios que simplemente no naveguen por sitios en los que no confian!. [http://www.microsoft.com/technet/security/advisory/902333.mspx](http://www.microsoft.com/technet/security/advisory/902333.mspx)

Esa es la manera que tiene Microsoft para resolver sus problemas???
Lo malo que para Secunia eso cuenta como una corrección.


