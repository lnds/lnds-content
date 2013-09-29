---
layout: post
title: "El camino de la innovación"
date: 2013-02-15 13:30
comments: true
categories: 
- Innovación
- Desarrollo
- Paradigmas
- Cultura
---
Adrian Cockcroft es el "arquitecto de nube" en Netflix, sí, cloud architect. ¿Qué diablos es eso? En otra oportunidad les voy a explicar. Lo importante es que escribe [un blog](http://perfcap.blogspot.com/) bien interesante, sobre el cual se basa casi todo lo que voy a escribir hoy.

{% img center /blog/images/2013/02/netflix.jpg %}

En diciembre de 2011 escribió un post titulado ["How Netflix gets out of the way of innovation"](http://perfcap.blogspot.com/2011/12/how-netflix-gets-out-of-way-of.html), que les sugiero que lean. Es en realidad el "script" de una presentación sobre la cultura de Netflix.

Lo que quiere explicar Cockcroft en su presentación es: cómo Netflix puede hacer cosas tan rápido (a veces demasiado rápido), de modo que han podido realizar movidas estratégicas de gran envergadura, en poco tiempo y con un equipo pequeño de ingenieros.

Fíjense en lo que acabo de escribir: "realizar movidas estratégicas de gran envergadura, en poco tiempo y con un equipo pequeño de ingenieros".

No es fácil, claro está. ¿Donde está la clave?

Cómo siempre, la clave está en no seguir las reglas del libro, hacer las cosas cómo los agoreros del desastre dicen que no se deben hacer, sin miedo, y torciendo un poco las reglas.

<!-- more -->

Netflix nace en 1997, fundada por Marc Randolph y Reed Hastings,  ambos desarrolladores de software que trabajaban en Pure Software, los creadores de Purify, un debugger de memoria para C y C++ bastante popular a principios de los noventa en ambientes Unix. En esos tiempo esta era una herramienta valiosísima para depurar programas. Reed Hastings además era fundador de esa empresa.

En 1997 fueron adquiridos por Rational Software, la empresa detrás de UML y RUP, y que actualmente pertenece a IBM.

De esos tiempos Hastings recuerda que Pure Software era una pequeña empresa, bastante libre y anárquica, pero en la medida que fue creciendo se volvía cada vez más burocrática. Así que se retiró en cuanto fue adquirida por Rational, y [pensó durante 2 años cómo volver a organizar su nuevo emprendimiento](http://www.businessweek.com/stories/2007-09-23/netflix-flex-to-the-max) de modo que no cayera en estos "vicios del crecimiento". 

El resultado es Netflix, una empresa basada en los principios de "libertad y responsabilidad". Hastings le paga muy bien a sus empleados, tienen vacaciones ilimitadas, y les permite estructurar sus propios paquetes de compensaciones. A cambio se espera un alto desempeño, que cada empleado sea capaz de hacer el trabajo de 3 ó 4 personas. 

Voy a citar a Cockcroft quien describe de este modo la cultura innovadora de Netflix:

> Lo que encontré en pocos años es una cultura que permite la innovación, de modo que Netflix hace las cosas más rápido que otras compañías, que están demasiado asustadas o son muy lentas para intentar algo.

> ¿Quién trabaja en una compañía que tiene más de una linea de productos? El problema es que esa compañía pierde el foco y tiene problemas asignando recursos que se necesitan, y esto produce grandes peleas. Toma una cosa grande y hazla bien. Para Netflix, el mercado objetivo es todo aquel que le guste ver películas y programas de TV, eso es lo que nos mantendrá ocupados por un tiempo.

> [evitar la sobrecarga en la comunicación y la sincronización] Para los geeks, piensen en la [Ley de Amdahl](http://www.lnds.net/blog/2009/09/el-problema-de-paralelizar.html) aplicada a las personas. Tenemos la mayor cantidad de personas en el mismo lugar. Ancho de banda alto, y baja latencia en las comunicaciones.

> No tenemos ingenieros junior, ni estudiantes en práctica. Encontramos que los ingenieros que cuestan el doble son más de dos veces productivos, porque necesitamos menos sobrecarga administrativa. Reducir la sobrecarga administrativa es un aspecto importante para una cultura innovadora.

> Vale la pena el gasto extra en ingenieros que no requieran administración. Somos pequeños comparados con compañías como Google, ellos toman talento crudo y lo desarrollan, nosotros a veces tomamos la opción de contratar a alguien con sólo cinco años de experiencia.

> No tenemos un comité de arquitectura, ni estándares centralizados de codificación. Lo que hacemos es crear herramientas que creen un camino de mínima resistencia, lo que, combinado con la presión de los pares, mantiene alta la calidad. Los ingenieros son libres y responsables de resolver sus propios problemas.

> Tampoco tenemos un equipo de sistemas (operaciones) que se encarga de correr el código en producción. Los desarrolladores ejecutan lo que han escrito. El teléfono celular de todos está  disponible siempre, el truco es asegurarse de que no te llamen. 

> Toda la gente en operaciones tiene historias de horror acerca de desarrolladores estúpidos, y viceversa, pero no tiene por qué ser así. Tenemos una organización de desarrolladores que lo hace todo y no hay un equipo de IT Ops involucrado en nuestro desarrollo en cloud.

> ¿Quién tiene que pedir permiso para desplegar (deploy) 100 o 1000 servidores? Nosotros no. Los desarrolladores usan nuestro portal directamente, tienen que llenar un ticket de control de cambio donde registran lo que hicieron y pasa a producción, eso es todo. Hemos entrenado a nuestros desarrolladores para operar su propio código. Hemos creado y destruido hasta 1.000 servidores en un día, con sólo publicar nuevo código. 

> ¿Quién tienen un ciclo centralizado de publicación y tienen que esperar el próximo tren antes de publicar su código? Nosotros no. Cada equipo maneja su propio calendario de liberaciones (releases). El código nuevo se actualiza frecuentemente, y reduce su ritmo en servicios maduros. Los equipos son responsables para manejar la evolución de la interfaz y dependencias por si mismo. Libertad y responsabilidad nuevamente.

> Nuestros administradores de proyectos no están preocupados del seguimiento de las entregas. Ellos son dueños de sus recursos y de establecer el contexto para sus equipos. Tienen tiempo para hacerlo porque hemos eliminado todo el BS (Bull Shit) de su rol.

{% img center /blog/wp-content/uploads/2012/07/bullshit.jpeg %}

> Los administradores tienen que ser buenos para seleccionar personal, deben ser técnicos y con la capacidad para "arquitecturar" lo que su equipo hace, además de gestionar el proyecto para lograr resultados. No separen esto en tres personas. Reduzcan la sobrecarga administrativa, minimicen el BS y el tiempo perdido. Los equipos típicamente están compuestos de 3 a 7 personas. Tengan una reunión semanal con el equipo y un 1 a 1 con cada ingeniero para mantener el contexto.

> No tenemos herramientas estándares de desarrollo. Asumimos que los desarrolladores ya saben como ser productivos por si mismos. Damos algunos patrones comunes para que los nuevos puedan empezar, como Eclipse, IntelliJ, en Mac o Windows. Algunos usan Emacs en Linux. Contraten ingenieros experimentados que sean preocupados de su trabajo, y se encargarán de la calidad del código y los estándares sin tener que decírselo.

> Trabajen con gente que respetan. La única manera de tener una alta densidad de talento es sacar a la gente que no aporta. Eso también aplica a lo que algunos llaman "pelmazos brillantes" (brilliant jerks). Aunque hagan un gran trabajo, la cultura no puede tolerar a las prima donnas ni el comportamiento anti social, así que la gente que no confía en otros o comparte lo que saben no encajan.

> No pagamos bonos. No tenemos otros grados más que Ingeniero Senior, Manager, Director y VP. No registramos las horas o los días de vacaciones, decimos "tómatelas". Una vez al año revisamos el salario de todos comparados con sus pares y el mercado.

> Algunos pensaran que esto debe salir bastante caro, ¿pero cuál es el valor de ser increíblemente productivo y moverse más rápido que la competencia? Puedes adelantarte y establecer una posición líder antes que cualquiera se de cuenta que estás en el juego. ¿Recuerdan cuando hace unos pocos años atrás los "Analistas" decían que Netflix, la compañía de los DVD sería aniquilada por la otras compañías de streaming, y repentinamente el público se dio cuenta que estábamos generando más ancho banda de streaming que el resto?

> Así, ¿qué puede salir mal? Bueno, erramos recientemente, fuimos demasiado rápido, en parte porque podíamos, pero no tuvimos suerte y metimos la pata. Lo bueno es que Netflix puede re planear y ejecutar los arreglos que necesitamos muy rápido, sin angustia interna ni acusaciones mutuas (finger-pointing).

> Menos proceso, pocas reglas y principios simples. Denle a la gente libertad, háganlos responsables, reemplacen a los que no pueden o no quieren desempeñarse en ese ambiente. Enfóquese en  la densidad de talento y en conservar la atención de la administración removiendo el BS de sus trabajos.

> Ese es tu desafío. ¿Quieres organizar una banda y partir en una misión para salvar tu compañía? Deja de hacer las cosas que te quitan velocidad, y elimina toda la basura improductiva que obstruye tu gestión y a tus ingenieros.

Ese es el mensaje, y la segunda razón por la que me gusta Netflix. Libertad y Responsabilidad, así es cómo hay que trabajar. ¿Se atreverían a seguir un modelo como el propuesto por Netflix? ¿Creen que en su trabajo aceptarían un cambio cultural de este tipo? ¿Qué es lo que nos falta?

