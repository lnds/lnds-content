---
comments: true
date: 2007-12-24 08:15:42
layout: post
slug: la-magia-de-innovar
title: La magia de innovar
wordpress_id: 386
categories:
- Tecnología
---

Les quiero presentar un par de innovaciones del investigador [Johnny Chung Lee](http://www.cs.cmu.edu/~johnny/), postulante a doctorado en la Universidad de Carnegie Mellon.

La primera innovación la descubrí a través de un post en   
[Botón Turbo.](http://www.botonturbo.com/quien-dijo-que-la-wii-no-es-next-gen-ps3-is-so-last-week). Lamentablemente en ese blog no entendieron muy bien que es lo que sucede, así que permitanme explicarlo, antes de presentarles el video.

En este caso Chung Lee escribe un programa en C# y utiliza el control de la Wii como dispositivo de entrada conectado a su Laptop, corriendo Windows. En **ningún momento ha escrito código que se ejecute en la consola de Nintendo**, todo ocurre en el laptop, y lo que se usa es el WiiMote. La característica principal de esta innovación es que utiliza el control de la Wii al revés, mueve el sensor infrarrojo en vez del WiiMote.

[Ver Video](http://www.youtube.com/watch?v=Jd3-eiid-Uw)

  






  


Noten el efecto que se produce al introducir el marco, una técnica usada en computación gráfica. Claro que sólo sirve para un usuario, el que esté portando el sensor infrarrojo a la altura de sus ojos. Como explica Chung Lee, esta innovación le da nuevas posibilidades a la Wii.

La segunda innovación de Chung Lee, y que a mí me parece más interesante es cómo usa este concepto de usar el WiiMote para seguir el rastro de un lapiz infrarrojo. Con esto monta una pizarra interactiva, y luego construye su propia versión del Surface, claro que a una centésima parte del costo (una WiiMote cuesta unos 50 dolares, y un Surface unos 5000).

[Ver Video](http://www.youtube.com/watch?v=5s5EvhHy7eQ).

  






  


¡¡Con esto se pueden montar pizarras interactivas en cualquier colegio, a una fracción del costo!!

Lo mejor es que todo el código fuente de estos proyectos está publicado, les sugiero explorar la [página de proyectos](http://www.cs.cmu.edu/~johnny/projects/) de Chung Lee y sorprenderse con este innovador.

Estos proyectos han sido desarrollados en Windows usando como base la [Managed Library for Nintendo's Wiimote](http://blogs.msdn.com/coding4fun/archive/2007/03/14/1879033.aspx) escrita por Brian Peek y publicada en el blog de Microsoft [Coding4Fun](http://blogs.msdn.com/coding4fun/).



