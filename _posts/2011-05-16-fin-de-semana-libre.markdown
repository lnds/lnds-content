---
comments: true
date: 2011-05-16 00:54:48
layout: post
slug: fin-de-semana-libre
title: Fin de Semana Libre
wordpress_id: 1868
categories:
- Programación
- Software libre
- Usabilidad
tags:
- Fedora
- gnome shell
- linux
- shell
- ubuntu
- usabilidad
---

Durante este fin de semana he estado probando las ultimas versiones de dos distribuciones populares linux, Fedora 15 Beta, y Ubuntu 11.04. Me entregaron un pendrive de Fedora 15 en la RedHat Summit así que le di la oportunidad este fin de semana.

Instalar estos sistemas operativos es sencillisimo. Hace un tiempo tuve que restaurar mi notebook a la configuración de fábrica con Windows 7 y la experiencia fue desagradable, tras cuatro horas seguía instalando drivers y parches, y la verdad es que aún el sistema no está operando como logré tenerlo alguna vez.

En cambio Ubuntu y Fedora se instalaron en pocos minutos, y las actualizaciones son muy simples. Hay que reconocer que en esto tienen varias ventajas.

Lograr tener los 3 sistemas en mi PC no fue fácil, porque la gracia es que Grub te despliegue las 3 opciones de booteo, y los dos distros no son muy amistosos en esto. Finalmente logré hacerlo y aprovecho de dejarles esta receta para los que quieran emprender esta aventura:



**Cómo configurar un PC para booteo triple: Windows 7, Fedora 15 y Ubuntu 11.04:**



	
  1. Instalar Windows 7, y si lo tienen instalado entonces dejar espacio y particiones libres para instalar los otros sistemas. Esto es fácil de lograr, en el Panel de Control ir a Herramientas Administrativas luego a Crear y Formatear particiones de disco y liberar espacio.

	
  2. Instalar  Fedora en una de las particiones. Grub reconocerá a Windows.

	
  3. Instalar Ubuntu en otra de las particiones, al hacer esto Grub dejará de reconocer a Fedora, pero no se preocupen, esto pasa porque Fedora queda instalado en un volumen LVM. Una solución es no usar LVM, pero eso implica entrar a opciones maś avanzadas de instalación.

	
  4. Para solucionar el problema de Grub debemos instalar el soporte de LVM en Ubuntu.Esto se logra con el siguiente comando:
**sudo aptitude install lvm2**
(Es probable que tengan que instalar aptitude)

	
  5. Re iniciar Ubuntu.

	
  6. Ahora que Ubuntu reconoce las particiones lvm2 ejecutar este comando:
**sudo update-grub**

	
  7. Con esto grub reconoce Fedora en su partición.


La pista me la dió este [post](http://www.taringa.net/posts/linux/6075755/Hacer-Que-El-Grub-de-Ubuntu-Reconozca-Particion-de-Fedora.html) de ercherramon en Taringa.

Esto me ha permitido evaluar ambos sistemas. Por ahora me estoy quedando con Fedora 15 y Gnome Shell. Es una interfaz más usable que Unity. No podía soportar la barrita de aplicaciones de Unity, y me parece que Gnome Shell está mejor pensada. Lo que me gusta de Unity es la integración de la barra de menú en la parte superior, hace ganar espacio.

Hay algo que no me termina de gustar y que encuentro que Windows es mejor, es en la tipografía y uso del espacio. Por alguna razón en Windows las letras y el espacio parecen mejor aprovechados que en Unity o Gnome Shell, y en versiones anteriores de escritorios de Linux he notado lo mismo. Eso es algo que deben mejorar.

En fin, ha sido un fin de semana entretenido, he podido hackear con Open Shift, y otros lenguajes dinámicos, y espero de estas aventuras en código contarles algo más adelante.
