---
comments: true
date: 2012-05-25 03:24:06
layout: post
slug: dos-de-tres
title: 'Dos de Tres: El Teorema CAP'
wordpress_id: 2751
categories:
- Desarrollo
- La Naturaleza del Software
- Paradigmas
- Programación
tags:
- alta disponibilidad
- bases de datos no relacionales
- cloud computing
- complejidad
- desarrollo
- NoSQL
- sistemas distribuidos
- tecnología
- tolerancia a fallas
---

Mi amiga ISA [reclama por sus papitas](http://idelabar.blogspot.com/2012/04/quiero-mis-papitas-d.html), se refiere a un problema que tuvo al tratar de adquirir objetos con su tarjeta de crédito para un juego online. Este es un problema común, lo que todos esperamos es que si el dinero ha sido descontado de nuestra tarjeta de crédito nos llegue el producto que compramos, más aún si se trata de un objeto virtual (después de todo se trata de mover bytes de un registro a otro, ¿no?).

Si hay fondos en la cuenta, y el servidor de medio de pago ha dado la autorización esperamos que nuestros bienes lleguen a nosotros, o los servicios que pagamos estén disponibles. O cuando pagamos una cuenta en linea, esperamos que todo esté acreditado y no tengamos problemas posteriores.

En [su artículo](http://idelabar.blogspot.com/2012/04/quiero-mis-papitas-d.html) Isabel menciona  las propiedades que deben cumplir las bases de datos transaccionales, el famoso acrónimo ACID: Atomicity (Atomicidad), Consistency (Consistencia), Isolation (Aislamiento) y Durability (Durabilidad). Estas propiedades son deseables, y se espera que un motor de bases de datos transaccionales las respete. Isabel dice que "algunas de estas caracteristicas las entrega la base de datos y otras es parte responsabilidad de quienes desarrollan la transacción."

El problema es que implementar sistemas que respeten estas propiedades en sistemas distribuidos ¡es muy difícil! Es más, existe un importante resultado que nos dice que en sistemas distribuidos hacer esto requiere ciertos compromisos. Ese resultado es conocido como el [Teorema CAP](http://en.wikipedia.org/wiki/CAP_Theorem), y sospecho que no muchos de ustedes lo conocen, y si se dedican a la arquitectura de sistemas deberían.


# El Teorema CAP


El 19 de julio de 2000 el profesor [Eric Brewer](http://www.cs.berkeley.edu/~brewer/), planteó una conjetura en base a su trabajo implementando Inktomi.

![](http://www.lnds.net/blog/wp-content/uploads/2012/05/Inktomi.png)

Inktomi era la gran promesa de ese tiempo, se consideraba que sería el buscador que terminaría desplazando a  AltaVista, bueno, eso fue antes de Google, y que reventara la burbuja de las .com. Lo importante es que Brewer aprendió mucho implementando este servicio, y en un simposio de la ACM planteó la siguiente conjetura:


> Es imposible para un sistema distribuido garantizar simultáneamente las siguientes tres características:

> 
> 
	
>   * Consistency (Consistencia): todos los nodos ven la misma data al mismo tiempo.
> 
	
>   * Availability (Disponibilidad): una garantía de que todos los requerimientos recibirán una respuesta de que el requerimiento fue exitoso o fallido.
> 
	
>   * Partition Tolerance (Tolerancia a la Partición): el sistema continúa operando a pesar de la pérdida arbitraria de mensajes, o la falla de parte del sistema.
> 




Dos años más tarde Seth Gilbert y Nancy Lynch del MIT publicaron [una demostración](http://lpd.epfl.ch/sgilbert/pubs/BrewersConjecture-SigAct.pdf) de la conjetura de Brewer, estableciéndolo como un teorema, probablemente uno de los teoremas más importantes de las ciencias de la computación, y uno de gran importancia para todos los que nos dedicamos a la arquitectura de software.

El Teorema CAP dice que puedes garantizar dos de tres de estas propiedades. Es decir, el teorema CAP explica porque Isabel tuvo que esperar por sus papitas más tiempo del que ella esperaba, o simplemente puede que no les haya recibido. Explica porque a veces aunque tratamos de diseñar nuestro sistema de la forma más robusta posible hay algo que vamos a perder.

Si ustedes tratan de diseñar su arquitectura para tener full consistencia, full disponibilidad y una total tolerancia a fallos, entonces están perdiendo su tiempo, es imposible. En algún momento algo se va a romper, una transacción se va a perder, o un registro quedará inconsistente, no pueden tener las tres propiedades garantizadas, deben elegir dos.

Como la demostración del teorema es muy técnica, voy a explicarles en términos simples usando [un bonito ejemplo](http://ksat.me/a-plain-english-introduction-to-cap-theorem/) escrito por Kaushik Sathupadi.


> **Capítulo 1: Un nuevo emprendimiento**

Una noche cuando tu esposa agradece que te acuerdes de vuestra fecha de aniversario de matrimonio, te viene a la cabeza una idea curiosa. Muchas personas tienen problemas para recordar las cosas, y sin embargo tu no tienes es problema, porque eres muy bueno recordando, entonces decides crear tu propia startup: Recuerdos Inc.

Escribes tu anuncio en el diario:

> 
> _Recuerdos Inc: Nunca olvide, ¡sin necesidad de recordar! ¿Se ha sentido mal por olvidar demasiado? No se preocupe, simplemente llámenos, marque el 555-RECUERDE y díganos lo que necesita recordar después.  ¿No recuerda la fecha de cumpleaños de su jefe? llame al 555-RECUERDE y se la recordaremos. No olvide más, no necesita recordar nada, nosotros recordamos por usted. (Costo $ 290, IVA incluido)_
> 
> 
Y contratas una linea telefónica, te compras unos cuadernos y empiezas a atender. Un diálogo en tu servicio sería más o menos así:

> 
> 
	
>   * Cliente: Hola, ¿podría guardar la fecha de cumpleaños de mi vecino?
> 
	
>   * Tú: Claro, ¿cuando es?
> 
	
>   * Cliente: el 4 de mayo
> 
	
>   * Tú: (anotas la fecha en la página del cliente en un cuaderno) ¡Anotado! Llámenos cuando necesite saber el cumpleaños de su vecino
> 
	
>   * Cliente: ¡Gracias!
> 
	
>   * Tú: De nada, esta llamada tiene un costo de $290 el minuto, gracias por llamar.
> 

**Capítulo 2: empiezas a escalar**

Consigues algo de capital de riesgo, y empiezas a recibir cientos de llamadas al día. Y junto con esto empiezan los problemas, las  llamadas se empiezan a encolar, la gente cuelga el teléfono después de esperar tanto rato. Y para colmo un día te enfermas y pierdes todo un día de atención. Así que decides escalar, le pides a tu mujer que te apoye y se incorpore al servicio. Compras una central telefónica, colocas un anexo para tu esposa y duplicas tu capacidad de atención (¡y duplicas tus ingresos!)

**Capítulo 3: tu servicio es malo**

Es miércoles y recibes una llamada de tu mejor cliente Juan:

> 
> 
	
>   * Juan: Hola
> 
	
>   * Tú: Buenas tardes señor, gracias por llamar a Recuerdo Inc. ¿en que podemos servirle?
> 
	
>   * Juan: ¿Puede decirme cuando es mi viaje a Puerto Montt?
> 
	
>   * Tú: Un segundo por favor (buscas en tu cuaderno, ¡y no hay ningún vuelo anotado en la página de Juan!)
Señor, creo que hay un error, usted no nos ha dicho nada sobre un viaje a Puerto Montt.
> 
	
>   * Juan: ¡Qué! ¡Si yo los llamé ayer! (y cuelga)
> 

Conversas con tu esposa y te das cuenta que ella atendió a Juan ayer, pero el vuelo está anotado en el cuaderno de ella, y no en el tuyo. **¡Tu sistema distribuido no es consistente! **Un cliente puede ser atendido por tu esposa, y cuando llame de nuevo puede ser redirigido a otra persona, y Recuerdos Inc. ¡no tendrá una respuesta consistente para el cliente!

**Capítulo 4: arreglas el problema de consistencia**

Conversas con tu esposa y le dices:

> 
> 
	
>   * Siempre que recibamos una llamada de un cliente antes de completar la llamada le avisaremos al otro.
> 
	
>   * En ese momento ambos anotaremos el recordatorio.
> 
	
>   * De este modo ambos tendremos copia de los recuerdos y no tendremos que ir a leer el cuaderno del otro.
> 

Esto implica que cuando  se tenga que actualizar el cuaderno no podremos atender a nadie. Eso no es un gran problema porque la mayor parte de las veces los requerimiento son de consultas que implican buscar algo en los cuadernos, más que escribir. Además lo importante es que no podemos dar respuestas incorrectas, así que este es un costo que debemos asumir.

Pero tu mujer te hace notar que no has considerado el caso cuando uno de los dos no se presenta a trabajar. En ese momento no es posible atender una conversación de actualización, porque no está disponible el otro para copiar a su cuaderno. Estamos ante un problema de **disponibilidad**, si el otro no está, ¡no es posible completar la llamada!

**Capítulo 5: una solución astuta**

¿Cómo logras que las anotaciones en los cuadernos queden consistentes y disponibles, ante la ausencia de uno de los dos? Para resolver esto se te ocurre  una idea brillante, y se la dices a tu pareja:

> 
> 
	
>   * Cuando una persona llame para ingresar un recuerdo, es decir, cuando se requiera escribir algo en los cuadernos, lo que haremos es que si está la otra persona disponible entonces le avisaremos en ese momento y ambos actualizarán sus apuntes.
> 
	
>   * Si la otra persona no está disponible, entonces le enviaremos un email con la actualización.
> 
	
>   * Al otro día, cuando la persona que estuvo ausente regrese lo primero que debe hacer es leer sus emails y actualizar su cuaderno antes de poder empezar a atender el teléfono.
> 

Genial! Ahora Recuerdos Inc. tiene un servicio **consistente** y de **alta disponibilidad**.
**Capítulo 6: tu mujer está enojada contigo**




> Pero un día discutes con tu mujer, y estás tan molesto que decides salir y presentarte a trabajar. ¿Qué tal si ella está tan enojada contigo que decide no actualizarte de nada y no manda los emails acordados?. Tu genial idea fracasa, porque a pesar de que es una idea astuta que garantiza consistencia y alta disponibilidad no es **tolerante a una partición**. Puedes decidir ser tolerante a fallos tomando la decisión de no atender llamados hasta que te hayas reconciliado con tu mujer, pero si haces eso entonces ¡**sacrificas la disponibilidad** durante todo ese tiempo!.




> **Conclusión**




> Así que el teorema CAP nos dice que cuando diseñas un sistema no puedes tener las tres características: Consistencia, Disponibilidad o Tolerancia a Particiones. Sólo puedes elegir dos:




> 

> 
> 
	
>   * Consistencia: tus clientes, una vez que han actualizado información siempre tendrán la información más actualizad cuando llamen nuevamente. No importa que tan rápido vuelvan a llamar.
> 
	
>   * Disponibilidad: Recuerdos Inc siempre estará disponible para llamadas mientras cualquiera de ustedes (tú o tu esposa) se presente a trabajar.
> 
	
>   * Tolerancia a Partición: Recuerdos Inc operará siempre, aunque se haya perdido la comunicación entre tú y tu esposa
> 






## Consistencia Eventual


¿Qué pasaría si contrataras a un ayudante que se encargue de actualizar los cuadernos cada vez que hay un cambio?. Este personaje puede actualizar los cuadernos en "background", mientras no se ocupan, su labor es mantener consistente las anotaciones, claro que con un cierto retraso. La base no se encuentra consistente de inmediato, pero con esto no sacrificas la disponibilidad, a cambio de un cierto grado de inconsistencia temporal.

Así es como funcionan muchas bases de datos NoSQL, por ejemplo. Lo importante es que el ayudante haga su trabajo con cierta celeridad, si realiza su labor digamos que cada 5 minutos, entonces reduces las probabilidades de que te encuentres con inconsistencias.

Por lo tanto debemos aceptar que no podemos controlar todas las situaciones y hay veces que nuestras arquitecturas van a fallar. Podemos diseñarlas para maximizar estas tres propiedades, pero eventualmente algo deberemos sacrificar. La pregunta es qué. ¿La disponibilidad por la consistencia, o la consistencia por la disponibilidad? Ese es el desafío, y buscar medidas de mitigación es nuestra labor como arquitectos. Pero no olviden, que habrá ocasiones en que simplemente tendremos que devolver el dinero, o pedir disculpas, eso es seguro, tenemos un teorema que lo demuestra. :)
