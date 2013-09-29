---
comments: true
date: 2011-12-20 03:02:48
layout: post
slug: simplejizando
title: Simplejizando...
wordpress_id: 2481
categories:
- Desarrollo
- La Naturaleza del Software
- Programación
tags:
- lenguajes de programación
- Ogu
---

Una de las ventajas de publicar Ogu en esta etapa es que me permite confrontar mi diseño con los lectores y potenciales usuarios. He recibido comentarios en el blog y en privado que me han permitido enriquecer y determinar algunos problemas en la sintáxis.

El principal problema reside en la ambigüedad de las declaraciones, la gramática hasta ahora permitía el uso opcional de las palabras reservadas 'def', 'var' y 'val'.

De este modo la siguiente declaración


> x := 1


era equivalente a esta otra:


> val x := 1


y obligaba al uso de var para las variables mutables:


> var x:= 1


Por otra parte la declaración de funciones era de la siguiente manera


> factorial : Int -> Int

factorial 0 = 1

factorial n = n * factorial (n-1)


El problema es que una de las características de Ogu es que las funciones son _first class_, de este modo la siguiente declaración


> f : Int -> Int


es ambigua, puede ser la variable inmutable f de tipo función Int->Int, o la función f. La gramática actual exige que inmediatamente después de esta declaración debe venir una expresión que corresponde a la definición del cuerpo de la función, esto obliga al uso de var o val si queremos que f sea una variable que almacenará una función.

Ante esto he decidido hacer los siguientes cambios:



	
  * var, val y def son obligatorios al declarar variables o funciones.

	
  * al inferir tipos los dos puntos son opcionales.

	
  * También las palabras class y trait que eran opcionales ahora son obligatorias, y la definición de una clase debe ir precedida con la palabra reservada def

	
  * La consecuencia de esto es que ahora las clases pueden empezar con minúsculas (lo que me simplifica un problema con el runtime de java y los packages)


Con estas consideraciones los ejemplos del primer artículo de esta serie quedan así:


> **val** blog = “La naturaleza del software” // blog es de tipo String

**val** ogú = Cavernícola(nombre: “ogú”) // ogú es de tipo Cavernícola

**val** x, y := 1, 2 // x e y son de tipo Int, notar que el ':' es opcional


Las funciones se definen de esta forma:


> **def** factorial : Int –> Int

**def** factorial 0 = 1

**def** factorial n = n * factorial (n-1)


La forma abreviada es:


> **def** factorial : (n:Int)–> Int  =**if  **(n == 0) 1 **else ** n * factorial(n-1)


Lo interesante es que con este cambio también  se puede escribir de la siguiente manera:


> **def** factorial 0 = 1

**def** factorial n = n * factorial (n-1)


Potenciando más la inferencia de tipos.

Este cambio permite desambiguar la siguiente declaración


> **val** f : Int -> Int


Permitiendo lo siguiente:


> f = factorial


Las clases se declaran de este modo ahora:


> **def** Persona : **class** (nombre: String, edadInicial: Int) ={

**       var** _edad = edadInicial

**      def** saludar : () = println “hola “ + nombre

**       def** celebrarCumpleaños : () = {
_edad = _edad + 1
println “¡¡ feliz cumpleaños “ + nombre + “!!”
}
}


Los ejemplos del artículo anterior también deben ser re escritos:


> **def** Stack{T}  : **class** () = {

**      var** _data : [T] = []

**     def** push : (x:T) = _data = x :: _data

**     def** pop : ()->(r:T) = {
r = head _data
_data = tail _data
}
}


Las interfaces en Ogu se llaman traits (rasgos), siguiendo la tradición de Scala:


> **def** Figura : **trait** = {

**      def** area : ()->Int
**       def** perimetro : () –> Int
}

**def** Circulo : **class** (radio:Int) ~ Figura = {

**         def** area = pi * radio ^ 2

**         def** perimetro = 2 * pi * radio

}

**def** Cuadrado : **class** (lado:Int) ~ Figura ={

**         def** area = lado*lado

**         def** perimetro = lado*4

}


Además con esto queda más claro que area y perimetro son funciones y no variables.

Este ejercicio me hizo darme cuenta de que estaba cayendo en el vicio que pretendía evitar, el vicio de la _simplejización_.  En el afán de ahorrarme algunas palabras reservadas estaba haciendo de Ogu un lenguaje con una sintáxis que terminaría siendo oscura e intimidante, que obligaría a pensar mucho para analizar una expresión. Estos cambios van en la linea de la simplicidad, sin perder el minimalismo sintáctico que espero que tenga Ogu.


