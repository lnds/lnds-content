---
comments: true
date: 2005-08-10 18:24:43
layout: post
slug: no-comprometas-la-seguridad-de-tu-sitio
title: No comprometas la seguridad de tu sitio
wordpress_id: 110
categories:
- Seguridad
---

Esta imagen es real, de un sitio muy visitado por los desarrolladores java a nivel internacional:  
![badlogin.JPG](http://www.lnds.net/archives/badlogin.JPG)

No sólo eso, cuando le pedí que me enviara la clave me envió la original.

Principios de Seguridad básico:

1.- Nunca de pistas, si el nombre de usuario está mal, o la clave está mal, entregue el mismo mensaje de error. En este caso no hay que ser demasiado amistoso, porque se compromete la seguridad del sitio.

2.- No guarde la clave en claro en su sitio, no importa cuanto empeño le pongas, no existe sistema de seguridad perfecto. Lo mejor es hacer un hash con la clave.

3.- Exige claves largas, con 8 o más caracteres, lo ideal es que la clave tenga letras números y otros símbolos. Combina mayúsculas y minúsculas en las claves.

4.- Exija que las claves se cambien a menudo.

5.- Bloquee el login al sitio después de una cierta cantidad de reintentos.

6.- En casos extremos puedes bloquear la cuenta y enviar un email de notificación al usuario.

7.- No uses el email como identificación de acceso, eso es muy malo, porque el email es público, y facil de deducir.

8.- Cuando te pidan recuperar la contraseña, genera una nueva clave con caracteres al azar.

9.- No uses test de turings, o captchas, porque atentan contra la usabilidad de tu sitio, y dan un falso sentido de seguridad, los captchas fueron creados para otra cosa. Lo mismo aplica para los generadores de clave, que pueden ser interceptados, o robados.

10.- Usa biometría, es lo más seguro hoy en día.



