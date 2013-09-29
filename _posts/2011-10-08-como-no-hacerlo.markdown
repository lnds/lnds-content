---
comments: true
date: 2011-10-08 15:20:49
layout: post
slug: como-no-hacerlo
title: Los problemas de un plebiscito
wordpress_id: 2315
categories:
- Sociedad
- Tecnología
- Usabilidad
tags:
- ciberactivismo
- hackers
- plebiscito
- tecnología
- votaciones
---

> Nunca atribuyas a la malicia lo que puede explicarse por la incompetencia
– Napoleón Bonaparte


Enzo Abbagliati (@cadaunante) tiene mucha razón en su crítica “[el plebiscito que no fue](http://www.cadaunadas.net/2011/10/el-plebiscito-que-no-fue.html)”. El entusiasmo no es excusa para hacer mal las cosas, menos si se quiere lograr un grado de legitimada para un movimiento ciudadano.

Hace años participé en una de los procesos de conteo oficial, durante la que fue la elección presidencial donde resultó Eduardo Frei, y ahí pude palpar las dificultades tecnológicas y logísticas de realizar un proceso de votación, y eso que mi equipo era liderado por amigos que [ya eran expertos en este tipo de actividades](http://www.lnds.net/blog/2008/10/los-hackers-del-5-de-octubre.html).

Por ese tiempo también exploramos las posibilidades del voto electrónico. Personalmente creo que no hay manera técnica de hacer el voto electrónico bien, menos por internet. Hay gente que piensa distinto, sobretodo los que venden soluciones de voto electrónico.

Después de leer la reflexión de @cadaunante decidí echar un vistazo superficial al sitio [www.votociudadano.cl](http://www.votociudadano.cl), donde se puede realizar la votación a través de internet. Varias cosas saltan a la vista desde el punto de vista de la seguridad informática



	
  * No hay certificado digital, ni sesión segura usando SSL (protocolo https)

	
  * El sitio está escrito en php, se usó GentleSource Form Mail, gracias por darles pistas de la herramienta usada a los hackers, ahora es cosa de ver que vulnerabilidades afectan a este producto y realizar el ataque.

	
  * No hay captchas, así que es muy fácil que alguien pueda programar un robot para inflar votos (@cadaunante dice que solo se puede votar 1 vez, pero no da detalles de la prueba que realizó, no tengo tiempo para probar, pero hay que ver varias cosas: validan la IP? qué pasa cuando las conexiones vienen detrás de un proxy, desde un router wifi compartido en casa, etc.)

	
  * No se hicieron pruebas de stress, y lo que es peor, no se contactaron con el proveedor de datacenter (norteamericano) para informarles que el sitio podría tener un tráfico anormal (como sucedió), [el proveedor bloqueó la cuenta porque consideró que estaba bajo ataque de denegación de servicio](http://www.votociudadano.cl/contenido/comunicadoVC.php).

	
  * Volvamos al tema de la herramienta usada, GentleSource Form Mail es un script php que despacha los formularios a una dirección de correo, acá no hay una base de datos, así que **todos los votos de este plebiscito están llegando al correo de alguien. **Esto es peor que malo, es escandaloso, porque además se está pidiendo el RUT de cada votante en el formulario. Olvidense del anonimato que debe asegurar una votación como esta, no existe.


No tengo tiempo para hacer un análisis en más profundidad, algún hacker que lea este post podrá hacer un examen más detallado, pero les digo que el [comunicado del equipo técnico de voto ciudadano](http://www.votociudadano.cl/contenido/comunicadoVC.php) es insuficiente. No creo que sea necesario culpar a un supuesto ataque al sitio por las falla, no es necesario ponerse tan paranoico, basta recordar la frase Napoleón, si este plebiscito electrónico fracasa es por la incompetencia de sus implementadores. Una lástima, porque estoy seguro que hay mucho profesional con experiencia que habría apoyado encantado este proyecto.

Si les interesa el tema pueden ver esta presentación de Javier Smaldone: ¿[El voto electrónico, es compatible con la democracia](http://blog.smaldone.com.ar/files/evoto/voto_electronico.pdf)?
