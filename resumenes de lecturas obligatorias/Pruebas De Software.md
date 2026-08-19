# Pruebas de Software

Pruebas de verificación: controlan que hayamos construido el producto que queríamos construir. Se pueden clasificar en tres tipos.
- pruebas unitarias: se deben ejecutar seguido y validan una responsabilidad única de un método. Las tienen que hacer y ejecutar los programadores.  
- pruebas de integración: verifican que varias porciones de código trabajando en conjunto, hacen lo que queríamos, es decir, varios métodos, o incluso varios objetos. También es conveniente que las escriban y ejecuten los programadores.  

Pruebas de validación: prueban que hayamos construído lo que el cliente quería.  

Pruebas de aceptación: (se necesita el sistema completo) se deben dar en un entorno lo más cercano posible al del usuario.  
Si se dan en un entorno de desarrollo, se denominan pruebas alfa, si lo prueba el cliente en su entorno, son pruebas beta.  
Las hacen usuarios o analistas de negocio, como mucho los testers, pero es imperativo validarlas con los usuarios.  

Pruebas de comportamiento: se denominan así, las pruebas que pretenden comprobar sólo comportamiento, lógica, sin necesariamente tener la interfaz de usuario. Están entre las de programadores y las de testers, entonces cualquiera puede diseñarlas y ejecutarlas.  

Pruebas manuales: no las deben realizar programadores, sino analistas y testers, dandole la mayor participacion al usuario.  

Cuando incorporamos características nuevas, podemos romper partes del programa que ya funcionaban. Esto se llama regresión, y para evitarlas se ejecutan pruebas de regresión, que es ejecutar las pruebas de todo el sistema de vez en cuando.

Pruebas funcionales: se deducen de lo que el programa debe hacer, en el ejemplo del tateti, serían las reglas del juego

Pruebas de atributos de calidad: existen muchos tipos
- pruebas de compatibilidad
- pruebas de rendimiento
- pruebas de resistencia
- pruebas de seguridad
- pruebas de recuperación
- pruebas de instalación

Decimos que una prueba es de caja negra cuando la ejecutamos sin mirar el código que estamos probando, que ante ciertos estímulos realiza ciertas acciones

Decimos que una prueba es de caja blanca cuando analizamos el código durante la prueba, como por ejemplo, el debugging.

Una técnica que cayó en desuso eran las pruebas de escritorio, donde el programador hacía un seguimiento en papel de lo que debería hacer el programa, pero ahora el costo computacional ya no es caro, y es preferible usar debugging y que trabaje la computadora.

Otra técnica es la revisión de código entre dos o más programadores, o pair programming.

TDD ha minimizado la importancia de las pruebas de aceptación y salieron varias estrategias a subsanarlo

BDD (behavior driven development): especificar el comportamiento mediante escenarios completos y automatizarlo

STDD (StoryTest Driven Development): pretende construir el software haciendo pasar pruebas de aceptacion creadas a base de las historias de usuario

ATDD (Acceptance Test Driven Development): construye el producto en base a pruebas, con menos énfasis en la automatización y más en los procesos.

SBE (Specification By Example): ha ido convirtiendose en una práctica colaborativa de construcción basada en especificaciones mediante ejemplos que sirven como pruenas de aceptacion.

Autor: CARLOS FONTELA