---
comments: true
date: 2005-09-04 20:26:53
layout: post
slug: programacion-segura
title: Programación segura
wordpress_id: 145
categories:
- Seguridad
---

Leo un anuncio de Microsoft en el [Communications of the ACM,](http://www.acm.org/pubs/cacm/) edición agosto **2005**.

El anuncio dice mas o menos así:

**Can you spot the security Hole**

This is the Source Code in DCOM that led the [Blaster Worm](http://en.wikipedia.org/wiki/Blaster_worm)

`  
HRESULT GetMachineName(WCHAR *pwszPath)  
{  
WCHAR wszMachineName[N+1];  
LPWSTR pwszServerName = wszMachineName;  
while (*pwszPath != L'\\')  
*pwszServerName++ = *pwszPath++;  
....  
}  
`

El anuncio ofrece recursos e información a los academicos que enseñan en departamentos de computación con el fin de que incorporen los aspectos de seguridad en sus cursos.

Irónicamente el Blaster Worm original contenía el siguiente mensaje:

> billy gates why do you make this possible ? Stop making money and fix your software!! (¿billy gates por qué haces esto posible? Deja de hacer dinero y arregla tu software!!)

Me parece bien que Microsoft demuestre preocupación por la seguridad, también hay que admitir que ha mejorado bastante en el tema.   
Serán estos avisos una respuesta al mensaje enviado por el autor de Blaster worm???

**buffer overflow**

Pero este tipo de código no se ve solamente en el código de Microsoft, recordemos que el primer worm de la internet aprovechaba un [buffer overflow](http://en.wikipedia.org/wiki/Buffer_overflow). Y que hay todavía por ahí muchas bibliotecas open source con este problema. El problema no es exclusivo de Microsoft.

Lamentablemente, la seguridad y el control de calidad en la construcción no es un tema que se cubra en forma especializada en las universidades.

A los interesados les recomiendo el siguiente libro:



