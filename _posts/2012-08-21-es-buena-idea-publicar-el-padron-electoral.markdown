---
comments: true
date: 2012-08-21 01:44:14
layout: post
slug: es-buena-idea-publicar-el-padron-electoral
title: ¿Es Buena Idea Publicar el Padrón Electoral?
wordpress_id: 2958
categories:
- Cultura
- General
- Identidad Digital
- La Naturaleza del Software
- Sociedad
tags:
- identidad digital
- leyes de la identidad
- padrón electoral
- servel
---

Resulta que se publicó el padrón electoral chileno en conformidad con el artículo 32 de la [Ley 18.556](http://www.leychile.cl/Navegar?idNorma=29951&buscar=18556) (LEY ORGANICA CONSTITUCIONAL SOBRE SISTEMA DE INSCRIPCIONES ELECTORALES Y SERVICIO ELECTORAL).

Como las últimas modificaciones de esta ley implican que se debe inscribir automáticamente a todo chileno o chilena mayor de 18 años en los registros electorales, el padrón contendrá inmediatamente los datos del RUT, Nombre Completo, Domilicio y sexo de todos ellos. El artículo 32 dice:


> 
"El Padrón Electoral con carácter de auditado y la Nómina Auditada de Inhabilitados 
deberán ser publicados por el Servicio Electoral en su sitio web con setenta días de 
antelación a la fecha que deba verificarse una elección o plebiscito."



Por lo tanto a partir de ahora estos datos son de dominio público. ¿Pueden ser usados para cualquier cosa? Acá es donde me pierdo, no soy abogado, así que no puedo responder eso, lo único que conozco es la [ley 19.628](http://www.leychile.cl/Navegar?idNorma=141599&buscar=19628) (De Protección de Datos Personales), que en el artículo cuatro dice:


> 
"No requiere autorización el tratamiento de datos 
personales que provengan o que se recolecten de fuentes 
accesibles al público, cuando sean de carácter 
económico, financiero, bancario o comercial, se 
contengan en listados relativos a una categoría de 
personas que se limiten a indicar antecedentes tales 
como la pertenencia del individuo a ese grupo, su 
profesión o actividad, sus títulos educativos, dirección 
o fecha de nacimiento, o sean necesarios para 
comunicaciones comerciales de respuesta directa o 
comercialización o venta directa de bienes o servicios."



Mi interpretación (no soy abogado, insisto), es que si el padrón electoral es público, no hay problemas en usar esta información para otros fines, como por ejemplo, enviar correspondencia personalizada a las casas de los electores.

Eso puede ser bueno, o malo. Supongamos que una madre quiere encontrar al padre de sus hijos para cobrarle la pensión alimenticia, o un grupo que quiera "funar" a algún político, con la disponibilidad de esta base el localizar a estas personas podría facilitarse.

Pero por el lado de los malos usos,  podemos usar el padrón electoral para hacer ingeniería social, o hacking como le dicen algunos medios. Ahora hemos disponibilizado elementos para poder ir conformar el delito de suplantación de identidad, hay muchos escenarios que se pueden armar a partir de los datos de esta base (¿cuanta gente usará, como pin de su tarjeta bancaria, los últimos dígitos de su domicilio, por ejemplo?).

La información de contacto de una persona es muy valiosa, y hay muchos escenarios legítimos en que es necesario contar con los datos personales de las personas, para entregarle una comunicación importante, y que le puede afectar.  Un banco necesita saber donde encontrar a sus clientes, pero no es bueno que un ladrón de identidad pueda acceder a esta misma información, por esto que los bancos y otras instituciones deben resguardar el uso de los datos personales de sus clientes. Estas instituciones tienen prohibido, por ley, publicar datos de contacto de sus clientes, o vender esa información, sólo pueden usarla si la han obtenido del propio usuario, o de una fuente pública, y para los fines propios del negocio que establecen con este cliente.

Si usted tiene  una empresa que realiza despacho de publicidad a las casas, por ejemplo, puede crear una base de datos, pero debe obtenerla directamente de las personas, con su consentimiento, o de alguna fuente pública, pero la ley  exige que si el cliente se lo pide, usted debe borrar de sus registros los datos personales. Eso es razonable, porque permite un equilibrio entre el desarrollo de un negocio y cautela la privacidad de la información. Pero el principio es poner un grado de trabas a la obtención de esta información, para resguardar la privacidad.

En este contexto hay varios modelos propuestos para manejar adecuadamente la información de carácter personal. Lamentablemente en nuestro país adoptamos un instrumento que es la pesadilla de todo experto en privacidad informática: el RUT.

El RUT debería ser un elemento para ser usado por el individuo en forma personal y privada, no debería divulgarse como se hace actualmente, ¿por qué? Porque permite establecer un enlace muy simple a toda la información disponible del individuo en distintas fuentes.

Piensen en el reciente [hackeo al periodista Mat Honan de Wired](http://www.wired.com/gadgetlab/2012/08/apple-amazon-mat-honan-hacking/):


> "In the space of one hour, my entire digital life was destroyed. First my Google account was taken over, then deleted. Next my Twitter account was compromised, and used as a platform to broadcast racist and homophobic messages. And worst of all, my AppleID account was broken into, and my hackers used it to remotely erase all of the data on my iPhone, iPad, and MacBook."


En el caso de Mat Honan el hacker pudo destruir toda la vida digital de este periodista, ¡llegando hasta borrar los datos de su computador, ipad y teléfono celular! ¿Cómo lo hizo?  estableciendo los enlaces de  información necesaria para obtener las claves de todos sus servicios en la nube.

Pues bien, en Chile hacer eso es mucho más simple, porque tenemos el enlace perfecto: El RUT.

El RUT, que es usado como clave en aplicaciones, en cada base de datos de personas que se crea en Chile se usa el RUT como llave primaria; es usado para acceder a las aplicaciones de home banking y administrar nuestras cuentas corrientes; para cada trámite en linea, para cada trámite off line. El RUT es la manera perfecta que puede usar un hacker para enlazar cada pedacito de información que vamos dejando en el ciber espacio (hace unos años, [en una visita a Chile](http://www.emol.com/noticias/nacional/2003/08/26/121353/uso-de-rut-en-transacciones-bancarias-por-internet-aumenta-peligro-de-robos.html), el famoso hacker [Kevin Mitnick](http://es.wikipedia.org/wiki/Kevin_Mitnick) realizó una demostración de esto ante un asombrado público).

El RUT puede ser usado para minería de datos y obtener el comportamiento de compra, nuestros hábitos, y por supuesto nuestro comportamiento crediticio. Por eso que es un elemento tan valioso y que deberíamos resguardar cuidadosamente, no andar divulgándolo por ahí, pero en Chile no se entiende este principio fundamental de seguridad informática.

Pero [no nos auto engañemos tampoco](http://www.lnds.net/blog/2012/06/mentira.html), la verdad es que hace rato que es posible obtener mucha información de cualquier chileno con su RUT, la publicación del SERVEL sólo facilita las cosas aún más. Eso puede ser usado para cosas buenas, pero para muchas más cosas malas.

Recordemos este modelo de manejo de identidad que nos plantean expertos como [Kim Cameron](http://www.identityblog.com/stories/2004/12/09/thelaws.html) o [Pamela Dinglin](http://eternallyoptimistic.com/2008/08/27/laws-of-identity-pamela-style/), las famosas 7 leyes de la identidad, que en su versión simplificada dicen:


> 1. No compartir la información de los usuarios a sus espaldas.

2. No pedir a los usuarios más información que la necesaria.

3. No exponer la información de los usuarios en forma innecesaria.

4. No permitir que la información pueda ser enlazada lógicamente por terceros, a menos que lo autorice el usuario.

5. El usuario debe ser capaz de elegir si los datos que tiene almacenado en algún sistema pueden ser conectados con sus datos en otro sistema.

6. Si la forma más simple de usar una herramienta no es la más segura, entonces la herramienta está mal construida.

7. Es deseable una experiencia de usuario simple, consistente y comprensible, aunque tras bambalinas se usen diferentes tecnologías y proveedores de identidad.


La publicación de los datos del padrón electoral chileno violan las leyes 1, 3, 4, 5 y 6. Y aunque su disponibilización es muy útil para los que usan (usamos) este tipo de información, hay que reconocer que desde un punto de vista del manejo informático de la identidad esta publicación es un desastre.




