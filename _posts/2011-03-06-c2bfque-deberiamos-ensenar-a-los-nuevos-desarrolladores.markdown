---
comments: true
date: 2011-03-06 15:28:10
layout: post
slug: '%c2%bfque-deberiamos-ensenar-a-los-nuevos-desarrolladores'
title: ¿Qué deberíamos enseñar a los nuevos desarrolladores?
wordpress_id: 1581
categories:
- Ciencia
- Educación
- La Brecha Intelectual
- La Brecha Tecnológica
- La Naturaleza del Software
- Paradigmas
- Personajes
tags:
- academia
- Bjarne Stroustrup
- educación
- industria
- ingeniería de software
- universidad
---

La siguiente es mi traducción de un [artículo](http://cacm.acm.org/magazines/2010/1/55760-what-should-we-teach-new-software-developers-why/fulltext) publicado por Bjarne Stroustrup en la Communications of ACM en Enero de 2010. [Bjarne Stroustrup](http://www2.research.att.com/~bs/) es el creador del lenguaje C++.


# ¿Qué deberíamos enseñar a los nuevos desarrolladores? ¿Por qué?


por **Bjarne Stroustrup.**

Publicado en Communications of the ACM ([texto original](http://cacm.acm.org/magazines/2010/1/55760-what-should-we-teach-new-software-developers-why/fulltext))
Vol. 53 No. 1, Pages 40-42
10.1145/1629175.1629192

La ciencia de la computación debe estar en el centro del desarrollo de los sistemas de software. Si no está, debemos confiar en la experiencia individual y en reglas generales, y terminamos con sistemas menos capaces y confiables, desarrollados y mantenidos a costos innecesariamente altos. Necesitamos cambios en la educación que permitan mejorías de la práctica industrial.


## [![](http://www.lnds.net/blog/wp-content/uploads/2011/03/Eraser.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/03/Eraser.jpg)El Problema


En varios lugares hay una desconexión entre la educación en computación y lo que la industria necesita. Considere el siguiente intercambio:

Famoso profesor de Informática (orgullosamente): "_Nosotros no enseñanos a programar, nosotros enseñamos ciencias de la computación._"

Gerente Industrial: "_Ellos no pueden programar ni como salir de una bolsa de papel."_

En muchos casos ambos están en lo correcto, y no sólo a un nivel superficial. No es el trabajo de la academia preparar programadores industriales, y las necesidades de la industria no son solamente la de contar con "buenos pensadores de alto nivel" y "científicos".

Otro profesor de computación: "_Nunca escribo código_."

Otro gerente: "_No contratamos graduados en computación, es más fácil enseñarle a un físico a programa que enseñarle física a un graduado en computación._"

Ambos tienen un punto, pero en un mundo ideal, ambos deberían estar fundamentalmente equivocados. El profesor está equivocado en que no puedes enseñar lo que no practicas (y en muchos casos, nunca ha practicado) y por lo tanto no entiende, mientras que el gerente está en lo correcto sólo cuando los requerimientos para la calidad del software están puestos tan absurdamente bajo que los físicos (y otros no entrenados en computación) bastan para cubrirlos. Obviamente, no me estoy refiriendo a físicos quienes han dedicado un esfuerzo significativo a dominar también la ciencia de la computación (esa combinación de habilidades está entre mis ideales).

Profesor de Computación (acerca de un estudiante): "_El aceptó un trabajo en la industria_."

Otro profesor: "_Que pena, el mostraba ser una promesa._"

Esta desconexión está en la raíz de muchos problemas y complica los intentos para remediarlos.

La industria requiere graduados en computación para construir software (al menos inicialmente en sus carreras). Ese software es, a menudo, parte de una base de código de larga vida y es usado para sistemas integrados o distribuidos con altos requerimientos de  fiabilidad. Sin embargo, muchos graduados no tienen, en esencia, educación o entrenamiento en desarrollo de software fuera de sus actividades recreativas. En particular, muchos ven la programación como un esfuerzo menor para completar una tarea y raramente les toca una vista más amplia que incluya pruebas sistemáticas, mantención, documentación y el uso de su código por parte de otros. También, muchos estudiantes fallan en conectar lo que aprendieron en una clase con lo que aprendieron en otra. Luego, a menudo vemoos estudiantes con altas notas en algoritmos, estructuras de datos, e ingeniería de software quienes sin embargo hackean soluciones en una clase de sistemas operativos con total desprecio por las estructuras de datos, algoritmos, y la estructura del software. El resultado es un desastre de pobre rendimiento imposible de mantener.

Para muchos, "programar" ha llegado a ser una extraña combinación de hackeos sin fundamenteos e invocación de las bibliotecas de otras personas (con sólo una vaga idea de lo que está pasando). Las nociones de "mantención" y "calidad del código" son típicamente olvidadas o pobremente entendidas. En la industria, las quejas sobre la dificultad de encontrar graduados que entiendan "sistemas" y puedan "arquitecturar software" son comunes y reflejan la realidad.


## Pero mi computador no ha fallado últimamente


Quejarse sobre el software es un pasatiempo popular, pero mucho software ha mejorado durante la última década, exáctamente como ha mejorado en décadas anteriores.  Desafortunadamente, las mejoras han llegado con un tremendo costo en términos de esfuerzo humano y recursos computacionales. Básicamente, hemos aprendido a construir sistemas razonablemente confiables a partir de partes poco fiables agregando interminables capas de chequeos en tiempo de ejecución y testeo masivo. La estructura del código en si misma a veces ha cambiado, pero no siempre para mejor. A menudo, estas capas de software y las intrincada dependencias comunes en diseño impiden a un individuo, aunque sea competente, que pueda entender completamente un sistema. Esto es un mal presagio para el futuro: no podemos entender y no podemos siquiera medir los aspectos críticos de nuestros sistemas.

[caption id="attachment_1588" align="alignright" width="300" caption="Bjarne Stroustrup"]![](http://www.lnds.net/blog/wp-content/uploads/2011/03/Bjarne-300x218.jpg)[/caption]



Hay, por supuesto, constructores de sistemas que han resistido las presiones para construir sistemas hinchados y más comprendidos. Debemos agradecerle a ellos que nuestros aviones computarizados no se estrellen, nuestros teléfonos funcionen, y nuestros correos arriben a tiempo. Ellos merecen alabanzas por sus esfuerzos de hacer del desarrollo de software un conjunto maduro y confiable de principios, herramientas y técnicas. Desafortunadamente son una minoría,  y el bloatware (software hinchado) domina mucho de la impresión y pensamiento de las personas.

Similarmente, hay educadores que han combatido a la separación de la teoría y la práctica industrial. Ellos también merecen alabanzas y soporte activo. De hecho, toda institución educacional que conozco tienen programas orientados a proveer de experiencia práctica y algunos profesores han dedicado sus vidas a crear casos exitosos a partir de programas particulares. Sin embargo, mirando el panorama general, no estoy impresionado, un par de proyectos o prácticas son un buen comienzo, pero no un substituto para una aproximación más completa a un curriculum más balanceado. Preferir las etiquetas de "ingeniería de software" o "TI" por sobre "Ciencia de la Computación" pueden indicar diferencias en la perspectiva, pero los problemas tienen un desagradable modo de resurgir, en formas ligeramente diferentes, después de moverse a una nueva configuración.

Mi caracterización de la "industria" y la "academia" bordea la caricatura, pero estoy confiado en que cualquiera con un poco de experiencia reconocerá partes de realidad reflejada en ella. Mi perspectiva es la de un investigador industrial y administrador (24 años en AT&T Bell Labs, siete de ellos como lider de departamento) que ahora ha dedicado seis años a la academia (en el departamento de ciencias de la computación de una escuela de ingenería). Viajo mucho, teniendo serias discusiones con gente técnica y administrativa de varias docenas de compañías (principalmente en E.E.U.U) cada año. Veo el desajuste entre lo que producen las universidades y lo que la industria necesita como una amenaza a ambas, la viabilidad de la ciencia de la computación, y la industria de la computación.


## La Brecha Academia/Industria


[![](http://www.lnds.net/blog/wp-content/uploads/2011/03/chasm-241x300.jpg)](http://www.lnds.net/blog/wp-content/uploads/2011/03/chasm.jpg)Entonces, ¿qué podemos hacer? La industria preferiría contratar "desarrolladores" totalmente entrenados en las últimas herramientas y técnicas, mientras que la ambición más grande de la academia es producor más y mejores profesores. Para progresar, estos ideales deben llegar a estar mejor alineados. Los graduados que van a ir a la industria deben tener una buena comprensión del desarrollo de software y la industria debe fomentar mejores mecanismos para absorber nuevas ideas, herramientas y técnicas. Insertar desarrolladores dentro de una cultura diseñada para prevenir que programadore semi calificado hagan daños no tiene sentido porque los nuevos desarrolladores estarán impedidos de hacer nada significativamente nuevo y mejor.

Permítanme señalar la cuestión de la escala. Muchos sistemas industriales consisten de millones de líneas de código, mientras un estudiante puede graduarse con honores de los programas de más alto nivel en ciencia de la computación sin siquiera escribir un programa más extenso que unas 1.000 lineas. Todos los proyectos industriales mayores involucran a mucha gente, mientras que muchos programas de ciencias de la computación valoran el trabajo individual al punto de desalentar el trabajo en equipo. En vista de esto, muchas organizaciones se enfocan en simplificar las herramientas, las técnicas y los lenguajes y procedimientos operativos para minimizar la dependencia de las habilidades del desarrollador. Esto es un desperdicio de talento humano y esfuerzo porque reduce a todos al mínimo común denominador.

La industria quiere confiar en herramientas y técnicas ciertas y que funcionan, pero también es adicta al sueño de "las balas de plata", "avances transformadores", "killer applications", y así. Quieren ser capaces de operar con desarrolladores mínimamente capaces e intercambiables guiados por unos pocos "visionarios" demasiados grandes para estar preocupado de los detalles de la calidad del código. Esto lleva aun inmenso conservadurismo en la elección de las herramientas básicas (como los lenguajes de programación y los sistemas operativos) y a un deseo de monoculturas (para minimizar los costos de entrenamiento y despliegue). A su vez, esto lleva al desarrollo de enormes infraestructuras propietarias y mutuamente incompatibles. Algo más allá de las herramientas básicas se necesita para habilitar a los desarrolladores para producir aplicaciones y los proveedores de plataforma quieren algo que permita atrapar a los desarrolladores a pesar de los comunes que son las herramientas básicas. Los sistemas de incentivos favorece esquemas corporativos grandiosos y resultados a corto plazo. Los costos resultantes son pasmosos, como las tasas de falla para los nuevos proyectos.

Enfrentada con la realidad industrial, y otros disuasivo similares, la academia se vuelve a si misma, haciendo lo que hace mejor: estudia cuidadosamente fenómenos con los que pueda lidiar en aislamiento por un pequeño grupo de gente de pensamiento similar, construyendo fundaciones teóricas sólidas, y elaborando diseños perfectos y técnicas para problemas idealizados. Herramientas propietarias que administran enormes bases de código escritos en estilos arcaicos no se ajustan a este modelo. Como en la industria, la academia desarrolla estructuras de recompensas. Todo esto se ajusta perfectamente con una tiraje constante de la chimenea con cursos sobre asuntos académicos bien delineados. Luego, el éxito académico  se ajusta a las necesidades industriales como una clavija cuadrada en un hoyo redondo y la industria tiene que cubrir los costos de entrenamiento y de desarrollo de las infraestructuras especializadas.

Alguien siempre sugiere "si la industria simplemente les pagara a los desarrolladores un salario decente, no habría problema". Eso podría ayudar, pero pagar más por el mismo tipo de trabajo no va a ayudar mucho, para una alternativa viable, la industria necesita mejores desarrolladores. La idea del desarrollo de software como una linea de ensamblaje repleta de trabajadores intercambiables semi calificados es fundamentalmente fallida y costosa. Empuja a los más competentes fuera del campo y desalienta a los estudiantes para entrar. Para quebrar este círculo vicioso la academia debe producir más graduados con las habilidades relevantes y la industria debe adoptar herramientas, técnicas y procesos para aprovechar estas habilidades.


## Sueños de Profesionalismo


"Computer science" (CS, "Ciencia de los computadores") es un término horrible y engañoso. CS no es primaramente sobre computadores y no es primariamente una ciencia. Más bien es sobre los usos de los computadores y sobre maneras de trabajar y pensar que involucran la computación ("pensamiento algorítmico y cuantitativo"). Combina aspectos de la ciencia, matemáticas y la ingeneriaía, a menudo usando computadores. Para casi toda la gente en CS , es un campo aplicado (La "CS pura", aislada de la aplicación es, típicamente, esteril).

¿Qué distingue a una persona CS al construir una aplicación de otro profesional, en otro campo (como la medicina o la física), construyendo una?  La respuesta debe ser "la maestría en el núcleo de la ciencia de la computación". ¿Cuál debería ser este "núcleo"? Debería contener mucho del currículum establecido en CS, algoritmos, estructuras de datos, arquitectura de máquinas, principios de programación, algo de matemáticas (principalmente para enseñar razonamiento basado en pruebas y razonamiento cuantitativo), y sistemas (como sistemas operativos y bases de datos). Integrar esos conocimiento y tener una idea de como manejar problemas grandes, cada estudiante debe completar varios proyectos de grupo (podrían llamar a eso la ingeniería de software básica).  Es esencial que haya un balance entre la teoría y la práctica, CS nos sólo principios y teoremas, y tampoco es no sobre hackear código.

Este núcleo es obviamente más "orientado a la comptudora" que el campo de la computación como un todo. Así que, nadie debería ser llamado un científico en computación si agragar una especialización dentro de las ciencias de la computación (por ejemplo, gráficos, redes, arqutectura de software, interacción humano computador, seguridad). Sin embargo, eso aún no es suficiente. La práctica de la computación es inherentemente aplicada e interdisciplinaria, así que todo profesional en computación debería tener el equivalente de un minor en algún otro campo (por ejemplo, física, ingeniería médica, historia, contabilidad, literatura francesa).

Los educadores experimentado observarán: "¡Pero eso es imposible! Dificilmente un estudiante podría dominar eso en cuatro años." Esos educadores están en lo correcto: algo habrá que dejar fuera. Mi sugerencia es que el primer grado calificado para ejercer como científico en computación debería ser el de magister - y un magister diseñado como un todo, no un grado de bachille con uno o dos años finales agregados. La gente que planea hacer investigación tendrá por objetivo, como de costumbre, postular a un doctorado (Ph.D).

Muchos profesores objetarán: "¡No tengo tiempo para programar!" Sin embargo, pienso que los profesores que enseñan a los estudiantes a ser profesionales del software deben hacerse el tiempo y sus instituciones deben encontrar maneras de incentivarlos para que programen. La meta última de la computación es ayudar a producir mejores sistemas. ¿Confiaría en alguien que no ha visto un paciente por años que enseñe cirugía? ¿Qué pensaría de un profesor de piano que nunca ha tocado el teclado? Una educación en computación debe llevar al estudiante más allá del aprendizaje por libros a dominar su aplicación en sistemas completos y en una apreciación de la estética en el código.

Uso la palabra "profesional". Esa es una palabra con muchos significados e implicancias. En campos como la medicina y la ingenería, esta palabra implica "licenciamiento"(1). El licenciamiento es un tópico muy complicado y emocional. Sin embargo, nuestra civilización depende del software. Es razonable que esencialmente cualquiera pueda modificar un cuerpo de código crítico basado en el gusto personal y el políticas corporativas? Si es así, será siendo razonable en 50 años? ¿Es razonable que piezas de software de las que dependen millones de personas vengan sin garantías? El problema real es que el profesionalismo forzado a través del licenciamiento depende en tener un cuerpo amplio y compartido de conocimientos, herramientas y técnicas. Un ingeniero licenciado puede certificar que un edificio ha sido construido usando técnicas y materiales aceptados. En la ausencia de un lineamiento ampliamente aceptado sobre la competencia en computación (como lo sugerí anteriormente), no veo como hacerlo para una aplicación de software. Hoy en día, no sabría como seleccionar un grupo de personas para diseñar un examen de licenciamiento (o realisticamente un conjunto de exámenes para las varias sub especialidades, como las juntas médicas).

¿Qué puede hacer la industria para acortar la brecha? Es más dificil caracterizar a la "industria" y las "necesidades de la industria" que hablar sobre la academia. Después de todo, la academia tiene una aceptable estructura estándar y bastante aproximaciones estándares para lograr sus objetivos. L industria es mucho más diversa: grande o pequeña, comercial o sin fines de lucro, sofisticada o media en su aproximación a la construcción de sistemas. Consecuentemente, no puedo ni siquiera prescribir remedios. Sin embargo, tengo una observación que se relaciona directamente con la brecha academia/industria: Muchas organizaciones que dependen críticamente de la computación han caido peligrosamente bajo en habilidades técnicas:

Gerente industrial: " _El in-sourcing de experiencia técnica es crítico par ala sobrevivencia."_

Ninguna organización puede permanecer existosa sin una memoria institucional y una infraestructura para reclutar y desarrollar nuevos talentos. Incrementar la colaboración con los académicos interesados en el desarrollo de software puede ser productivo para ambas partes. Investigación colaborativa y énfasis en el aprendizaje de larga vida va más allá de meros cursos de entrenamiento, y debería jugar un rol mayor en esto.


## Conclusión


Lo debemos hacer mejor. Hasta que lo hagamos, nuestra infraestructura continuará crujiendo, hinchada, y consumiendo exageradamente recursos. Eventualmente, alguna parte se romperá de una manera no predecible y desastrosa (piense en el enrutamiento de internet, banca en linea, voto electrónico, y control de la red eléctrica de potencia). En particular, debemos acortar la brecha academia/industria haciendo cambios en ambos lados. Mi sugerencia es definir una estructura de la educación en computación basada en un núcle más especialización y áreas de aplicación, con el objetivo eventual del licenciamiento de artefactos de software en al menos algunos de los profesionales que los producen. esto podría ir de la manao con un énfasis en un involucramiento a largo plazo entre la industria y la academia para los expertos técnicos.

**Bjarne Stroustrup** tiene el cargo de College of Engineering Chair in Computer Science Professor at Texas A&M University in College Station, TX.



Notas:

(1) Para entender por qué Stroustrup dice que el tema del licenciamient es polémico sugiero leer [este documento](http://www.cse.unsw.edu.au/~se4921/PDF/CACM/p91-white.pdf), licenciamiento se refiere a la certificación de los profesionales por parte de una entidad para que puedan ejercer, tal como pasa con los abogados y la corte suprema, o con los colegios profesionales en distintos paises.

(2) He usado el término computación cuando el autor usaba computer science (CS), he mantenido ese término en algunos párrafos para tratar de mantener el sentido del texto.

No se usó un traductor automático para traducir este texto. Es probable que esta traducción tenga muchos errores, agradeceré sus comentarios y mejoras.
