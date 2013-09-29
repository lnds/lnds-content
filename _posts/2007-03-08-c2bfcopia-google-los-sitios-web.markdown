---
comments: true
date: 2007-03-08 11:00:01
layout: post
slug: '%c2%bfcopia-google-los-sitios-web'
title: ¿Copia Google los sitios web?
wordpress_id: 1791
categories:
- Sin categoría
---



Me quedé pensando en la afirmación de [Carlos ](http://replay.web.archive.org/20071010142137/http://eldiabloenlosdetalles.net/)de que Google [copia el contenido de un sitio web para obtener la información relevante que permite crear la "magia" de encontrar los sitios relevantes](http://replay.web.archive.org/20071010142137/http://eldiabloenlosdetalles.net/2007/03/07/microsoft-ataca-a-google-racias-a-google-news/).

Vamos a analizar la veracidad de la afirmación, porque no me queda claro que si Google puede hacer con los libros o videos lo mismo que hace con las páginas web. Independiente de la disputa legal, voy a explorar esto, porque las consecuencias son interesantes.


## Indexar es el negocio


Google se dedica a la indexación del contenido, independiente de que ahora permite publicar y almacenar contenido, para Google el nucleo sigue siendo la mantención de un índice que facilita la búsqueda de información en internet.

Se preguntarán ¿qué pasa con el caché de Google? Efectivamente es una copia, pero el dueño de un sitio [puede solicitar que no se guarde una copia de este en el caché](http://replay.web.archive.org/20071010142137/http://www.google.com/help/features.html#cached). Por ejemplo, busquen por la fundación Bill y Melinda Gates, y notarán que ese sitio en particular no está en el caché de Google.

O sea que Google respeta el deseo de un dueño de un sitio de no ser "copiado". Además hay otros mecanismos para regular la manera en que los crawlers de Google visitan los sitios, esto se regula mediante varios mecanismos, como los archivos robots.txt, los sitemaps, etc.








El caché existe para poder mostrar algo en caso de que el enlace no esté disponible. Este es un servicio que se agradece, por cierto, pero que no es obligatorio para que Google funcione. Es más, se puede construir el índice sin necesidad de almacenar copias de la páginas.

El proceso de crawling genera una copia temporal de la página, pero esta copia podría permanecer en memoria volatil, como la RAM de alguna de las miles de computadoras de Google.


## La tabla de indice


Ahora les voy a mostrar un truco interesante. Supongamos que le asignamos un número a cada palabra, y lo colocamos en una tabla, parte de esa tabla sería mas o menos así:


> de - 344
del - 345
hardware - 450
la - 510
las - 511
naturaleza - 789
software - 1568


Entonces, la secuencia (510,789,345,1568) representa la frase "la naturaleza del software". Es claro que mediante tablas como estas es posible almacenar en forma compacta cualquier información (de hecho así funcionan varios algoritmos de compresión, como LZE, la base del format ZIP).

Google usa algoritmos y formatos similares para almacenar e indexar el contenido de las páginas. Con esto, no sólo puede obtener información, sino que puede llegar a reconstruir el contenido completo de las páginas sin tener que copiarlas bit a bit.

O sea, Google no es un parásito que no construye nada, o que sólo vive de la copia de contenidos, decir eso es ignorar lo que realmente hace esta empresa.

Ellos navegan la red periódicamente para extraer información, la que es almacenada en formatos propios, con esto construyen un gran índice que corresponde al "destilado" de filtrar las páginas web. Este "destilado", el índice, es una creación nueva, que no existía antes, y que es función del contenido de terceros, pero no es una copia literal. Además le agregan valor a ese índice, analizando las interrelaciones que se dan en las páginas, el famos PageRank, el cálculo de relevancia, etc.

El índice de Google es una creación nueva. Lo importante es que esta creación se obtiene del procesamiento de información accesible fácilmente.

Ahora Google está haciendo lo mismo con información más compleja, como los libros y los videos. Si crea un índice para toda esta información será un gran aporte para todos, el problema es legal, porque si bien nadie puede negarle el acceso a un sitio web, sí pueden negarle scanear un libro, o digitalizar un video.

Personalmente creo que es estúpido negarle el acceso a la información para crear un índice, es como si los escritores negaran a los bibliotecarios que archivaran sus libros.

Estoy seguro que ningún escritor se negará a que sus libros estén en la biblioteca nacional, entonces ¿por qué podrían negarse a estar en el índice de Google?

Porque creen que su trabajo será copiado y distribuido libremente, eso hace que a algunos les baje la angustia, porque ven que sus potenciales ingresos se verán mermados.

Por eso que hay que explicar bien que Google no copia el contenido y lo publica en la web para que todos lo bajen. Aunque tiene la capacidad, no tiene porque hacerlo, y si el autor ve que su trabajo puede estar desprotegido puede solicitar que Google no publique el contenido. Lo que no quita que Google tiene todo el derecho a a crear el índice igual.

Como yo lo veo, es imposible protegerse del proceso de indexado, y tampoco es algo ilegal, ni inmoral. Al contrario, trae más beneficios que otra cosa.


## ¿Indexar es legal, pero copiar no?


Hasta donde sé crear un indice de contenido es legal, sin embargo copiar un contenido protegido por copyright puede ser ilegal dependiendo de la juridicción. En nuestro país hay que pedir permiso al autor, en otros paises es legítimo copiar para uso privado.

Lo interesante, es que el índice permite recrear el contenido.

¿Si yo tuviera registrada la frase: "la naturaleza del software", tendría derecho sobre la secuencia (510,789,345,1568) ?

Supongamos que un tercero crea la tabla privada:


> de - 11
del - 12
hardware - 56
la - 68
las - 69
naturaleza - 79
software - 150


¿tengo derechos sobre la secuencia (68,79,12,150)?

La respuesta es no, porque la tabla es privada, y si el tercero no la hace pública no me afecta. Si este tercero brinda servicios basados en esa tabla, tampoco me afecta, y sin embargo puede perfectamente reconstruir una frase sobre la que tengo derechos de copia!

Oh my God!!

Creo que me están comenzando a convencer.....

:)





