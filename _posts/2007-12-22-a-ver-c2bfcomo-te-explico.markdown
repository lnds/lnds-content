---
comments: true
date: 2007-12-22 13:03:07
layout: post
slug: a-ver-%c2%bfcomo-te-explico
title: A ver... ¿como te explico?
wordpress_id: 385
categories:
- Sin categoría
---

No, si [usas un sistema operativo de 32 bits no puedes usar más de 4 GiB de memoria RAM](http://www.kriptopolis.org/mas-ram-no-gracias).

Punto.

Con 32 bits sólo puedes acceder a 2 elevado a 32 posibles direcciones. Existen mecanismos propuestos para acceder a direcciones sobre los 4 GiB, pero tienen sus problemas. (Cuando el mundo era joven, y usabamos el 286, había un truquillo para usar memoria por segmentos, pero eso si que era un dolor de cabeza, algo similar a lo que hace [PAE](http://www.microsoft.com/whdc/system/platform/server/PAE/pae_os.mspx)).  
De todas maneras, este es un "acceso virtual" a más de 4GiB, que se logra [con 4 bits adicionales de indirección](http://multingles.net/docs/jmt/4gbmem.htm), en un momento dado, la CPU sólo accede a 4GiB.

De todas maneras, el modo PAE crea bastantes inconvenientes, así que no es una solución real al problema.

Otros sistemas soportan PAE, pero insisto, siempre estás accediendo en forma indirecta a la memoria adicional, es mejor irse por un sistema de 64bits, porque te dará menos dolores de cabeza y sin degradar el desempeño.

Y no se trata de una [limitación de Windows](http://blogs.msdn.com/dcook/archive/2007/03/25/who-ate-my-memory.aspx), con Linux (de 32 bits) tampoco vas a poder, no importa lo que te digan los talibanes.

Si quieres usar más de 4GiB de RAM debes tener un procesador de 64 bits, y un sistema operativo de 64bits.

Les recomiendo leer este [artículo de Kriptópolis](http://www.kriptopolis.org/comprar-mas-ram) al respecto, (ah! y Bill Gates [nunca dijo que 640 Kb de RAM eran suficiente](http://www.kriptopolis.org/comprar-mas-ram))



