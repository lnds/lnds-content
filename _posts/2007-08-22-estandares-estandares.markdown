---
comments: true
date: 2007-08-22 09:20:42
layout: post
slug: estandares-estandares
title: Estándares, estándares...
wordpress_id: 1833
categories:
- Sin categoría
---

[![](http://www.lnds.net/blog/wp-content/uploads/2011/04/debate-thumb-240x175.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/04/debate-thumb-240x175.jpg)En estos momentos hay una [intensa discusión](http://replay.web.archive.org/20071017000912/http://www.elfrancotirador.cl/2007/08/22/odf-vs-ooxml-en-chile-%c2%a1un-round-mas/) sobre la manera en que[debe votar](http://replay.web.archive.org/20071017000912/http://sushiknights.org/2007/08/presentacion_ooxml.html) Chile con respecto a la adopción de OOXML como estándarISO.

Ayer se realizó una reunión en el [INN](http://replay.web.archive.org/20071017000912/http://www.inn.cl/)donde se pudo exponer el punto de vista de los [criticos a la adopción](http://replay.web.archive.org/20071017000912/http://sushiknights.org/2007/08/presentacion_ooxml.html) de este estándar.

Personalmente me he convencido de que adoptar OOXML como estándar sería pésimo, por razones técnicas, y comerciales, al final esto sólo lleva a perpetuar el lock in de un proveedor específico: Microsoft.

Hay argumentos sin fundamentos, y que tratan de confundir ([para variar](http://replay.web.archive.org/20071017000912/http://www.lnds.net/2007/08/codigo-libre.html)), y qué sólo dejan mal a quienes los esgrimen.

Ejemplos de estos malos argumentos se encuentran en las respuestas a sus lectores en el [blog de José Antonio Barriga](http://replay.web.archive.org/20071017000912/http://blogs.technet.com/joseantoniobarriga/default.aspx).

El [primer argumento](http://replay.web.archive.org/20071017000912/http://tinyurl.com/34gkcv) dice:


> _No sé si eres programador ni tampoco si sabes que la ISO tienen un sinúmero de lenguajes de programación (ISO FORTRAN, ISO PASCAL, ISO Eiffel, ISO CommonLISP, ISO C, ISO BASIC, ISO ADA, ISO C++, ISO C#, ISO EcmaScript, por nombrar algunos).¿ Como es esto si finalmente todos ellos generan un código binario que se netinede[sic] con la CPU? ¿Para que´tener tantos lenguajes? Recuerdo las peleas que tenía entre mis colegas si la papa era C++ o Fortran (si Fortran aunque ustedes no lo crean!)... al final el tema es que cada lenguaje está "diseñado" para resolver de una forma particular un algoritmo. Lo anterior nos lleva a que no existe un mejor lenguaje que otro, sino que dependiendo de cómo es mi set de información voy a ocupar uno u otro. (Recuerdo haber programado una calculadora en Cobol! Porque la circunstancia así me lo recomndaba[sic] )._


Hace años le hicieron esas preguntas a Microsoft con respecto a .Net, ¿para que soportar tantos lenguajes? ¿por qué no concentrarse en un sólo lenguaje, como lo hace Java?

La razón es muy simple, existen diversos lenguajes porque no todos los lenguajes de programación son de propósito general, pero es más, incluso los autodenominados lenguajes de propósito general no lo son.

Existen lenguajes específicos porque han sido definidos para distintos dominios de soluciones, los lenguajes son herramientas para los programadores. Podemos usar un alicate para clavar, o un[destornillador](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/Destornillador) como [gubia](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/Gubia), pero no fueron diseñados para esos usos.

Por eso que, así como existen estándares para cada herramienta, es obvio que exista un estándar para cada lenguaje de programación.

Pero esto no aplica para este caso. OOXML y ODF son dos estándares orientados para resolver el mismo problema, representar un documento, para su posterior transporte, impresión, almacenamiento, etc.

OOXML hace lo mismo que ODF, pero agrega una complejidad innecesaria. Además tiene muchos errores de consistencia, re inventa unidades de medida, e impone el uso de formatos patentados por Microsoft, algo que no es aceptable en un estándar ISO.

Acá hay que hacer una aclaración. Algunos que argumentan que LaTex es mejor que OOXML yODF, o que PDF es un mejor estándar que ODF, la verdad es que están confundiendo las cosas. Estos formatos se encargan de resolver problemas en distintas etapas de la vida del documento (LateX para componer, OOXML y ODF para almacenar y compartir, y PDF para visualizar con calidad de impresión).


## Pero si es XML...


El segundo argumento es bastante malo en realidad, y comete mismo error que cometieron en el gobierno al definir que la interoperabilidad de documentos electrónico sólo exige que estos seanXML y que estén disponibles los [schemas](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/Schema) respectivos (¿que hubieran pensado si el gobierno sólo exigiera que un documento electrónico esté formado por un conjunto de bytes?).

El [segundo argumento](http://replay.web.archive.org/20071017000912/http://tinyurl.com/2tec3q) va así:


> "...en Wikipedia la cantiada[sic] de estándares ( mas de 140) basados en XML y que yo sepa, no ha pasado nada. Cada cual representa una realidad distinta y podrás ver que existen varios sobre la misma materia. Es mas , la Contraloría General de la república, a raiz del decreto del documento electrónico, creo su propio "estándar". Una cosa buena es que ese si puede ser incluído dentro deOXML pues, éste es extensible por diseño."


[XML](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/XML) es un metalenguaje. Es una forma de ordenar documentos electrónicos en forma libre, y tiene reglas muy simples en realidad, una de las razones por la que ha sido exitoso (y también la causa de tanto abuso de este formato).

Cualquier cosa hecha sobre XML es _extensible por diseño_, eso no es ninguna gracia.

XML es como el alfabeto latino, pero uno puede escribir en francés, inglés, castellano incluso en chileno, usando el mismo alfabeto.

Así como se puede decir cualquier cosa usando el alfabeto latino, del mismo modo se puede decir cualquier cosa con XML, pero no todo es relevante, y no todo se entiende.

Decir que los documentos electrónicos deben estar en formato XML no es suficiente. Porque puedo convertir cualquier información en formato propietario, pasarlo a [base64](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/Base64) e insertarlo como un[blob](http://replay.web.archive.org/20071017000912/http://es.wikipedia.org/wiki/BLOB) entre dos etiquetas XML, de la siguiente manera:


> <?xml version="1.0" ?>
<DocumentoElectronico>
TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCBieSB0aGlz
IHNpbmd1bGFyIHBhc3Npb24gZnJvbSBvdGhlciBhbmltYWxzLCB3aGljaCBpcyBhIGx1c3Qgb2Yg
dGhlIG1pbmQsIHRoYXQgYnkgYSBwZXJzZXZlcmFuY2Ugb2YgZGVsaWdodCBpbiB0aGUgY29udGlu
dWVkIGFuZCBpbmRlZmF0aWdhYmxlIGdlbmVyYXRpb24gb2Yga25vd2xlZGdlLCBleGNlZWRzIHRo
ZSBzaG9ydCB2ZWhlbWVuY2Ugb2YgYW55IGNhcm5hbCBwbGVhc3VyZS4=
</DocumentoElectrinico>


Pero ¿qué pasa con el que recibe este "documento electrónico"?

Este documento está de acuerdo a lo definido por nuestro gobierno (el schema es bien simple, y basta con indicar que el blob decodificado corresponde al un documento word, por ejemplo), así que será problema del que recibe ver que hace con estos "garabatos".

El problema que muchos proyectos del Estado hacen esto. Hay reparticiones no tienen el software para interpretar el base64 decodificado, entonces ¿deben licenciar el software (esperando una aprobación de presupuesto), o "piratear" para poder leerlo? ¿Es eso aceptable? ¿Qué pasa con los privados que reciben estos documentos?

Por eso que decir "vamos a usar XML" no es suficiente, hay que ponerse de acuerdo en cómo se estructura el documento XML.

ODF y OOXML son definiciones, que basadas en XML estructuran una representación de un documento electrónico, pero estos estándares deben asegurar interoperabilidad, no es aceptable que requieran la compra de licencias de algún producto específico, o el pago de patentes.

OOXML es malo porque está pensado para prolongar la dependencia de un sólo proveedor: Microsoft.


## Los estándares permiten competir


Los estándares permiten competir, y deben ser neutrales por lo mismo. Normalmente cuando un estándar surge desde la empresa privada pasa por un proceso de incorporación de todos los competidores, ya pasó con SOAP, y por eso que extraña que Microsoft sea tan tozudo con este caso.

Pero la verdad es que están defendiendo, de mala manera, al más exitoso de sus productos Office.
Microsoft debería entender que es mejor abrazar un estándar abierto, y potenciarlo, en vez de seguir con esta actitud arrogante.

[Black and Decker](http://replay.web.archive.org/20071017000912/http://www.blackanddecker.com/), y [Stanley](http://replay.web.archive.org/20071017000912/http://www.stanleytools.com/) son dos grandes empresas que compiten en la industria de las herramientas.

Ambas adoptan estándares, internacionales, y nacionales, para poder competir. Todos saben que las llaves tienen una forma estándar, cumplen con las normas de operación, dimensiones, etc.
Probablemente sin estos estándares la industria de las herramientas sería un caos.

Eso falta en la industria del software.

Pero ya no debemo resistirnos más.

Aunque podemos programar cualquier cosa, y el software permite un grado de flexibilidad casi infinita, los usuarios nos están pidiendo que paremos, que de una vez por todas empecemos a usar estándares de interoperabilidad.

Esto de los estándares hay que verlo como una oportunidad para mejorar, y que nos permitirá crecer aún más. Es mejor tomar el ejemplo de otras industrias, y adoptar estándares, que sean simples, y que estén bien pensados, no llenos de errores (como en OOXML).


