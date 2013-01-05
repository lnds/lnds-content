---
comments: true
date: 2012-02-21 13:02:10
layout: post
slug: sobre-la-seguridad
title: Sobre la Seguridad
wordpress_id: 2539
categories:
- La Brecha Intelectual
- Paradigmas
- Seguridad
- Sin categoría
tags:
- desarrollo
- desarrollo corporativo
- hackers
- jaquers
- seguridad
- vulnerabilidad
- vulnerabilidades
---

[![](http://www.lnds.net/blog/wp-content/uploads/2012/02/securityk-300x225.jpg)](http://www.lnds.net/blog/wp-content/uploads/2012/02/securityk.jpg)Hace unas semanas atrás almorzaba con mi jefe, conversamos sobre seguridad TI. Cuando llegaron con la máquina para pagar con la tarjeta de débito le pregunté si estaba seguro de que la máquina que le pasaron para pagar pertenecía a la red bancaria, ¿cómo sabía que no era una máquina falsa, que estaba capturando y clonando su tarjeta?. Creo que le arruiné la vida :), ahora no puede usar su tarjeta de débito sin tener esa duda.

Hay asesores de seguridad que hacen eso arruinar la vida de toda una organización con sus observaciones, que siendo válidas deben ser tomadas con precaución.

Como [dice Steve Yegge](https://plus.google.com/112678702228711889851/posts/eVeouesvaVX), la accesibilidad es la cosa más importante en el mundo de la computación:


> "Como todo lo que es grande e importante en la vida, la Accesibilidad tiene una gemela malvada, marcada por el desbalanceado afecto de sus padres en su juventud, y que ha crecido para convertirse en su igualmente poderoso archi némesis llamada Seguridad (sí, hay más de un enemigo para la accesibilidad) . Y vieran ustedes como están siempre en desacuerdo estas dos.

"Pero argumentaré que la Accesibilidad es realmente más importante que la seguridad, porque llevando la Accesibilidad a cero significa que no tenemos producto, mientras que llevando la Seguridad a cero aún puedes tener un producto razonablemente exitoso como la Playstation Network."


Y aquí es donde saltan los "expertos en seguridad", rasgando sus vestiduras, y "tirándose las mechas", ¡cómo puedo difundir este mensaje tan irresponsable!". Y claro, puedo ser tildado de ser un bloguero anti seguridad.

No, no estoy diciendo eso, y Steve Yegge tampoco, digo que hay cosas más importantes que la seguridad, que la seguridad absoluta es un fin que no debemos perseguir, si queremos vivir sanamente, y dejar que las cosas funcionen. La seguridad puede llegar a ser un espejismo peligroso, como nos recuerda Bruce Schneier en [este video](http://www.lnds.net/blog/2011/10/el-espejismo-de-la-seguridad.html).

Tampoco debemos aceptar el chantaje de los "jaquers" que se dedican a publicar vulnerabilidades de forma no ética, exigiendo además que sean resueltas en los plazos que ellos estimen conveniente. Las decisiones de negocio no se toman así, las áreas de desarrollo y mantención deben subordinar sus programas de trabajo de acuerdo a las necesidades y prioridades del negocio, no al ritmo de histéricos script kiddies que han descubierto un XSS en el sitio.

Eso no exime de responsabilidad a los desarrolladores, de que deben mejorar sus prácticas y adoptar metodologías que aseguren la calidad y seguridad de los productos. Hay una tensión en las organizaciones entre Accesibilidad y Seguridad, pero siempre debe resolverse en favor de la primera. El área de seguridad es un área de apoyo, soporte. Debe lidiar con los riesgos, y administrarlos.

Un buen desarrollador debe estar preocupado de la seguridad, y debe saber cómo abordarla. Hay procesos que permiten incluir desarrollo seguro desde el principio, no es fácil adoptarlos, pero puede hacerse. Por otro lado,hay veces que sabemos de un riesgo, y decidimos vivir con él porque estimamos que la probabilidad de que sea explotado es menor que el costo de repararlo, o porque sencillamente no existe el presupuesto para corregirlo. Lo importante es advertir, consignar este hecho, aunque claro, después cuando viene el desastre nadie recuerda la advertencia, pero es el mundo en que nos toca vivir. Nos encantaría tener los recursos y el dinero para hacer un sistema totalmente robusto libre de vulnerabilidades, pero no siempre se puede, y muchas veces "hay que arar con los bueyes que se tienen".

Estas cosas no las entienden algunos personajes no han tenido que lidiar con las complejas políticas de una organización, personas con mucho tiempo libre, que derrochan sus talentos "jaqueando" y publicando sus "descubrimiento" con el sólo fin de sembrar FUD y agrandar su pequeño ego, pura vanidad. Si alguien estuviera publicando la lista de casas sin alarmas en mi condominio seguramente sería denunciado y perseguido por cometer un delito, pero si alguien hace eso exponiendo la seguridad de los clientes de un sitio web de un banco, o de la web de un servicio público, las redes sociales lo glorifican. Eso no es ético, es casi tan peligroso como realizar el ilícito. Es lo que Jaron Lanier llama una ideología de violación, y es el texto que les dejo a continuación, para que lo reflexionemos:


**Una ideología de Violación**




por Jaron Lanier (*)





> 

> 
> Internet ha llegado a estar saturada con una ideología de violación. Por ejemplo, cuando algunas de la figuras más carismáticas del mundo en linea, incluyendo a  Jimmy Wales, uno de  los fundadores de Wikipedia, y Tim O‟Reilly, el creador del término “web 2.0,” propusieron un código de conducta voluntario ante el [caso de matonaje a ](http://www.simdalom.com/blog/2007/04/04/blogs-codigo-de-conducta-caso-kathy-sierra/)[Kathy Sierra](http://www.simdalom.com/blog/2007/04/04/blogs-codigo-de-conducta-caso-kathy-sierra/)[1], hubo una protesta generalizada, y las propuestas no llegaron a ninguna parte.




> 

> 
> La ideología de la violación no irradia desde las profundidades del reino troll, sino de las mayores alturas académicas. Hay respetables conferencias académicas dedicadas a los métodos de violar todo tipo de santidades. El único criterio es que los investigadores desarrollen alguna manera de usar la tecnología digital para lastimar gente inocente que pensaba que estaba a salvo.




> 

> 
> En 2008, investigadores de la Universidad de Massachusetts en Amherst y de la Universidad de Washington presentaron papers en dos conferencia (llamadas Defcon y BlackHat), divulgando una bizarra forma de ataque que aparentemente nunca se había expresado en público antes, incluso en trabajos de ficción. Ellos gastaron dos años de esfuerzo de su equipo para conseguir la forma de usar tecnología de teléfonos móviles para hackear marcapasos y apagarlos por control remoto con el fin de matar a una persona [2]. (Aunque ocultaron algo de los detalles en sus presentaciones públicas, ciertamente describieron lo suficiente para garantizar que el éxito era posible.)




> 

> 
> La razón por la que yo llamo a esto una expresión de una ideología es que hay un entramado de argumentos vigorosamente construidos que decoran este comportamiento asesino para que parezca algo grandioso y nuevo. Si la mismos investigadores hubieran hecho algo similar sin tecnología digital,  habrían al menos perdido sus trabajos. Supongan que ellos hubieran gastado un par de años y abundantes fondos investigando como configurar una lavadora para envenenar la ropa con el fin de (hipotéticamente) matar a un niño una vez que el se la pusiera. O ¿qué tal si hubieran dedicado un laboratorio en una universidad de elite para encontrar una nueva forma de manipular imperceptiblemnte esquíes para causar accidentes fatales en las pistas? Estos son proyectos perfectamente factibles, pero, como no son digitales, no soportan esta ilusión de ética.




> 

> 
> Un resumen de esta ideología es más o menos así: toda esta gente no técnica, ignorante e inocente allí afuera que van por su vida pensando que están a salvo cuando en realidad son terriblemente vulnerables a todos quienes son más inteligentes de lo que ellos son. Por lo tanto, nosotros los técnicos, las personas más inteligentes tenemos que inventar formas de atacar a los inocentes, y publicar nuestros resultado, de modo que todos estén alertados de los peligros de nuestros poderes superiores. Después de todo una persona astuta y malvada podría venir.










> 

> 
> Hay algunos casos en los cuales la ideología de violación lleva a practicas positivas. Por ejemplo, cualquier joven técnico tiene el potencial de descubrir una nueva manera de infectar un computador personal con un virus. Cuando esto pasa, hay varios pasos siguientes posibles. El menos ético podría ser para el "hacker" infectara computadores. El más ético podría ser que el hacker discretamente deje que las compañías que soportan los computadores lo sepan, de modo que los usuarios puedan descargar mejoras. Una opción intermedia sería publicar la vulnerabilidad para obtener gloria. Un parche puede usualmente ser distribuido antes de que la vulnerabilidad sea explotada.







> 

> 
> Pero el ejemplo de los marcapasos es enteramente diferente. Las reglas de la nube aplican pobremente a la realidad. Le tomo a dos laboratorios académicos de alto nivel dos años de esfuerzo enfocado demostrar la vulnerabilidad. y esto sólo fue posible porque un tercer laboratorio en una escuela de medicina fue capaz de procurarles marcapasos e información sobre estos, algo que normalmente sería muy dificil de conseguir. ¿Deberían los estudiantes de enseñanza media o los terroristas, o cualquier otra parte imaginable, haber sido capaz de ensamblar los recursos necesarios para para averiguar si era posible matar gente de esta nueva forma?







> 

> 
> La reparación en este caso requeriría de muchas cirugías, más de una por cada persona con un marcapasos. Nuevos diseños de marcapasos sólo inspirarán nuevas formas de explotarlos. Siempre habrá una nueva vulnerabilidad, porque no existe una cosa tal como la seguridad perfecta. ¿Deberá cada paciente cardiaco programar cirugías al corazón anuales para mantenerse por delante de estos bien intencionados académicos, sólo para poder mantenerse vivo? ¿Cuanto costaría? ¿Cuántos podrían morir de los efectos laterales de la cirugía? Dada la oportunidad sin fin de hacer daño, nadie será capaza de actuar con la información que los investigadores han tenido a bien proveer, así que cualquiera con un marcapasos estará para siempre a un mayor riesgo de lo que de otra manera podría haber estado. No se ha logrado ninguna mejora, sólo daño.










> 

> 
> Aquellos que están en desacuerdo con la ideología de la violación se dice que subscriben a la falaz idea conocida como "seguridad a través de la oscuridad".  La gente inteligente no se supone que acepte esta estrategia de seguridad, porque internet supuestamente ha vuelto a la oscuridad obsoleta.







> 

> 
> Luego, otro grupo de investigadores de elite han gastado varios años encontrando el modo de abrir una de las cerraduras más difíciles de abrir, y han publicado los resultados en internet. Esta era una cerradura que los ladrones no habían logrado violar por si mismos. Los investigadores compararon su triunfo al rompimiento por parte de Turing de la máquina Enigma[3]. El método usado para abrir la cerradura podría haber permanecido oculto si no fuera por la ideología  que ha encantado a gran parte del mundo académico, especialmente los departamentos de ciencias de la computación.




> 

> 
> Ciertamente la oscuridad es la única forma fundamental de seguridad que existe, y que internet por si misma no hace obsoleta.  Una forma de desprogramar a los académicos que compran la omnipresente ideología de la violación es hacerles notar que la seguridad por oscuridad tiene otro nombre en el mundo de la biología: biodiversidad.







> 

> 
> La razón por la que algunas personas son inmunes a virus como el SIDA es que sus particulares cuerpos son oscuros al virus. La razóm por la que los virus de  computadoras infectan más PCs que Macs no es que el Mac tenga mejor ingeniería, sino que es relativamente oscuro. Los PCs son más comunes. Esto significa que hay más retorno en el esfuerzo de atacar los PCs.







> 

> 
> No existe algo como una cerradura inviolable. De hecho, la gran mayoría de los sistemas de seguridad no son demasiado difíciles de romper. Pero siempre se requiere de un esfuerzo para encontrar cómo romperlos. En el caso de los marcapasos, tomó dos años a dos laboratorios, lo cual debe haber significado un gasto significativo.







> 

> 
> Otro elemento predecible de la ideología de la violación es que cualquiera que se queja de los rituales de la elite de violadores será acusado de difundir el FUD[4], temor, incerteza y duda. Pero en realidad son los ideólogos los que buscan publicidad. Todo el punto de publicar  vulnerabilidades como el ataque a los marcapasos es la gloria. Si la notoriedad no está basada en esparcir el FUD, ¿qué es?




Notas:







[1] El caso de Kathy Sierra aún causa controversia y disputa en la [entrada de wikipedia](http://en.wikipedia.org/wiki/Talk:Kathy_Sierra#NPOV-tag) que habla sobre este caso.




[2] Sí, hay académicos que se dedican a pensar en formas ingeniosas de matar gente con teléfonos móviles, y mucha gente en la comunidad de seguridad piensa que hacer esto está bien: [http://www.schneier.com/blog/archives/2008/03/hacking_medical_1.html](http://www.schneier.com/blog/archives/2008/03/hacking_medical_1.html)




[3] La máquina Enigma era usada por los nazis para transmitir mensajes cifrados durante la segunda guerra mundial, Alan Turing y un equipo en Bletchey Park fueron capaces de romper el código que generaba este aparato, probablemente acortando el tiempo de la guerra.







[4] FUD por las palabras en ingés Fear, Uncertainty and Doubt.










(*) Tomado de su libro [You Are Not A Gadget: A Manifesto](http://amzn.to/y0R19L)
















**ESPARCIENDO REPELENTE DE TROLL: PSST, PSSST...**



