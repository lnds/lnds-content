---
comments: true
date: 2005-08-02 17:17:04
layout: post
slug: 7-consejos-para-usar-excepciones
title: 7 Consejos para usar excepciones
wordpress_id: 100
categories:
- Programación
---

Aqui hay 7 consejos para el uso de excepciones en C#

1) No utilice las excepciones para controlar el flujo de la aplicación.  
2) Usar código de validación para evitar excepciones innecesarias.  
3) Usar el bloque finally para asegurar la liberación de los recursos.  
4) No atrape las excepciones que no va a manejar. .  
5) Tenga en cuenta que relanzar excepciones (rethrowing) es costoso. Casi tan costoso como la excepción que se produjo.  
6) Preservar toda la información de diagnóstico posible en los manejadores de excepciones. Esto es util para efectos de depurar.  
7) Utilizar el Monitor de Performance para monitorear excepciones del CLR.

Gracias a Juan Daria Tempesta (Instructor DCE) por inspirar este artículo

  




