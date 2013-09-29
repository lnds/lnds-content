---
comments: true
date: 2009-01-05 20:46:31
layout: post
slug: md5-las-vulnerabilidades-siguen-ahi
title: 'MD5: las vulnerabilidades siguen ahí'
wordpress_id: 317
categories:
- Paradigmas
- Privacidad
- Seguridad
tags:
- criptografía
- hashing
- MD5
- vulnerabilidades
---

En 2005 escribí una [prueba de concepto](http://www.codeproject.com/KB/security/HackingMd5.aspx) aprovechando la vulnerabilidad de MD5 ([Busindre](http://www.busindre.com/) ha [explicado mucho mejor que yo](http://www.busindre.com/evilize-creando-distintos-ejecutables-con-identico-md5-colisiones/), en español, mi prueba de concepto), en realidad la prueba de concepto tomaba las ideas expuestas por Dan Kaminsky en su ahora bastante famoso paper [MD5 To Be Considered Harmful Someday](http://www.doxpara.com/md5_someday.pdf).




Hace unos días un grupo de investigadores europeos publicaron otra prueba de concepto igual de interesante, en un paper irónicamente llamado: [MD5 considered harmful today](http://www.win.tue.nl/hashclash/rogue-ca/).




Al parecer, no he leido detalladamente el artículo, la prueba aprovecha la misma vulnerabilidad que mi ejemplo. El hecho es que teniendo una manera de generar una colisión, no es complejo modificar el contenido de cualquier archivo firmado con MD5, esto se podría extender para modificar un certificado digital, convirtiendolo en un certificado raiz.




No sabemos cuantas Autoridades Certificadoras (CA) aún usan MD5 para firmar sus certificados, no creo que sea una práctica común, pero basta tener un sólo certificado firmado con este algoritmo para dejar vulnerable a todos los certificados generados por esa autoridad certificadora.




La manera más efectiva de combatir esta vulnerabilidad es dejar de usar el algoritmo MD5 al momento de certificar un certificado. Esto es algo que seguramente empezará a ser implementado en los browsers, y todas las bibliotecas que implementen SSL.




[Ben Laurie](http://en.wikipedia.org/wiki/Ben_Laurie), uno de los fundadores de la Apache Software Foundation, y miembro del teamo core de Open SSL [ha pensado lo mismo](http://www.links.org/?p=480), y al menos ha estado analizando la factibilidad de eliminar MD5 del código fuente de Open SSL, o al menos cambiar el nombre a las funciones que implementan este algoritmo, y propone calendarizar al menos la total eliminación de MD5, al parecer eliminar ahora el algoritmo provocaría una serie de problemas a varios certificados existentes.




Espero que este sea un golpe de gracia para el uso de MD5 como mecanismo de validación de firma electrónica. Me gustaría que fuera así, lamentablemente este algoritmo sigue siendo usado para certificar archivos SO, o todo tipo de documentos digitales, por ejemplo, en Chile hay varias instituciones públicas que usan este algoritmo como firma obligatoria en varias normativas y procedimientos oficiales, que transfieren información bastante sensible, esos usos no tienen efectividad alguna, tal como [mostré en 2005](http://www.lnds.net/blog/2007/10/mi-mayor-aporte-a-la-seguridad-informatica.html), espero que lean este artículo alguna vez y se cambie por algo mejor.




Estuve revisando algunos sitios web importantes que usan certificados digitales en Chile, con el fin de verificar que no usaran MD5, y afortunadamente no encontré nada. Pero atención, urge impedir que MD5 sea usado como algoritmo de firma en todo certificado, así que mientras eso no suceda, en realidad no sé si podemos confiar mucho en la infraestructura PKI.




Pero tampoco quedé muy tranquilo, porque casi todos los certificados digitales que pude ver usan SHA1 como algoritmo de firma, y sabemos SHA1 va a ser quebrado más temprano que tarde (teniendo un mecanismo de generación de colisiones es posible un esquema de suplantación similar al usado con MD5).




En términos de seguridad informática hemos empezado un año entretenido ;)




Actualización: [MetaSploit ha agregado](http://blog.metasploit.com/2009/01/scanning-for-md5-signed-ssl.html) al arbol principal de su código la detección de certificados emitidos y firmados con MD5, lo malo es que el problema no está en los certificados ya firmados (estos se pueden revocar), la vulnerabilidad es que podemos crear nuevos certificados firmados con MD5. Insisto, lo que hay que hacer es invalidar la verificaciónMD5 cuando se use SSL.
