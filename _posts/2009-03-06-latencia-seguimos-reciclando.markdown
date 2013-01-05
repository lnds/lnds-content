---
comments: true
date: 2009-03-06 09:35:01
layout: post
slug: latencia-seguimos-reciclando
title: Latencia (seguimos reciclando)
wordpress_id: 287
categories:
- Desarrollo
- Internet
- Tecnología
---

> "No sé lo que quiero, ¡pero lo quiero ya!"  
-- [Luca Prodan](http://es.wikipedia.org/wiki/Luca_Prodan), fallecido vocalista y lider de Sumo  


> "Los problemas de Ancho de banda se curan con dinero. Los problemas de Latencia son más difíciles, porque la velocidad de la luz es fija. (No le puedes robar a Dios)"  
-- Anónimo [1]

Cuando medimos el desempeño de una aplicación Web, el aspecto técnico que más afecta a la percepción de usuario es la **Latencia**.

Aplicando lo dicho por el gran Luca Prodan, el usuario no sabe lo que quiere, pero quiere que se le entregue con prontitud.  
  
Para entender los conceptos de evaluación de desempeño vamo a definir las siguientes variables, en términos sencillos:

  * Ancho de Banda: Cantidad de datos que pueden ser enviados por la red en un segundo.
  * Rendimiento (Throughput): Cantidad de trabajo que puede realizar el servidor en un periodo de tiempo.
  * Contención: Competencia por los recursos, se da cuando tenemos más de 1 cliente accediendo al servidor.
  * Latencia: tiempo para realizar una operación simple asumiendo que no hay contención [1]. Tiempo de respuesta efectivo medido por parte del cliente.

  


La latencia es función del ancho de banda, y el throughput, sin considerar la contención:

>   


> > Latencia = F (Ancho Banda, Througput)
>
>>   


  


El ancho de banda se mide en bits por segundo (bps).

Normalmente se considera un 80% de uso del canal.

  


> Ejemplo 1: Si tenemos un ancho de banda de 256 (Kbps), es decir, 32 KiloBytes por segundo (KB/s), entonces el límite teórico considerando el 80% de eficiencia, es de 25.6 KB/s (32*0,8). Por lo tanto, una página de 40 KB, será descargada en 1,56 segundos.

>   


Si el rendimiento del servidor es de 100 páginas por segundo (p/s), entonces, en generar una página se demorará 1/100 segundos. Luego la Latencia para la página de 40 Kbps es de 1,56 + 0,01, o sea, 1,57 segundos por página.

  


Fórmula práctica para la Latencia

  


Una función práctica para medir la latencia está dada por la siguiente ecuación:

> L = (1/T)+{P/W)

Donde:

  


  * T : Throughput (rendimiento) expresado en Paginas por Segundo
  * P: Tamaño de la página en Kilobytes/Pagina
  * W: Ancho banda efectivo en Kilobytes por segundo (se puede calcular rápidamente dividiendo el ancho de banda en Kbps por 10).
  
  


> Ejemplo 2: La contención tiene un efecto sobre el throughput: supongamos que tenemos 1.000 usuarios, queriendo acceder a una página al mismo tiempo, ésta debe realizar una consulta a la base de datos y entregar un resultado, que corresponde a 40 kilobytes de datos (incluyendo el código html). Asumamos que tenemos un pool de 10 conexiones a la base de datos, y que la consulta toma unos 250ms en ejecutarse. De acuerdo a la Teoría de Colas, el tiempo promedio de espera para usar la conexión es de 12,375 ms, luego, el tiempo promedio para generar la página es de 12,625 ms, o sea, el throughput en este caso es de 0,08 p/s (1000/12,625). Si el ancho de banda es 256 Kbps, tendremos que la latencia teórica es de: L = 1/0.08 [seg/pag] + 40/25.6 [kb/pag]/[kb/seg] = 14.06 [seg/pag]

**

  


Latencia Ideal** : corresponde a la latencia sin considerar el throughput, es decir:  
  


> > > > Li = P / W

  


Consejos para disminuir la Latencia

  


Los problemas de latencia son los más difíciles de abordar, el artículo de David A. Patterson de la CACM [1], sugiere 3 técnicas típicas para afrontar los problemas de latencia:

> 1. Caching: Originalmente nació porque el acceso al almacenamiento secundario siempre es más lento, en este caso, tenemos ejemplos donde aplica el caching, guardar los objetos precalculados, guardar tablas con parámetros, etc.

> 2. Replicación: Esto es más costoso, pero uno podría tener réplicas de los sitios en varios servidores (Server farm) balanceando la carga entre ellos.

> 3. Predicción: Tratar de adivinar que se va a necesitar, por ejemplo, si la tabla de ciudades se va a usar siempre, en vez de leerla 1 vez, puedo tener un objeto de aplicación que lea la tabla de ciudades y se mantiene una copia compartida por todas las sesiones.

>   


Hay más técnicas, como aplicar patrones de diseño, introducir una capa de negocios intermedia, etc.

> Todas estas decisiones deben tomarse con cuidado y con la asesoría adecuada.

  


[1] Latency Lags BandWidth, David A. Patterson, Comunications of the ACM Magazine (CACM), Oct, 2004



