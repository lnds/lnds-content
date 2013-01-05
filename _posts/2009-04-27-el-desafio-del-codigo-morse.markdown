---
comments: true
date: 2009-04-27 22:07:10
layout: post
slug: el-desafio-del-codigo-morse
title: El desafío del código morse
wordpress_id: 75
categories:
- Programación
---

Este es el segundo desafío que voy a publicar, esperemos que tenga más participación que [el anterior](http://www.lnds.net/2008/08/zig_zag_un_desafio.html) (sólo una respuesta).

Hoy es el día que se celebra el natalicio de Samuel Morse, así que el desafío se compone de 2 partes.

La primera parte es la más simple, consiste en crear una función que reciba un string de puntos y rayas e imprima las letras que corresponden.

Si la función se llama CodigoMorse() entonces el resultado de

> CodigoMorse("<del>.. .</del> <del>. .</del> - .-- .-. .- .-.. . .. .- <del>....</del>.. ...---..-.-..-.-..") = "La naturaleza del software".

La segunda parte considera consiste en construir un programa que emita sonidos que representen el código morse.

La idea es que el programa reciba una frase y emita bips en el parlante del computador que representen los puntos y las rayas.

Hay que considerar que el código morse es un sistema rítmico, con las siguientes reglas, si el punto es la unidad básica, entonces una raya dura lo que duran 3 puntos, entre símbolos hay una pausa de duración de 1 punto, y entre palabras hay una pausa de 7 puntos.

Pueden escribir el programa en el lenguaje que quieran, deben dejar un enlace al código fuente del programa en los comentarios.

Les dejo esta tabla tomada de Wikipedia con el código morse:

  


![Morse_Code.svg.png](http://www.lnds.net/images/450px-International_Morse_Code.svg.png)

