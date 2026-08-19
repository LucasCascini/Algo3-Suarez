# What's The Point Of Test-Driven-Development

Toda la gente que envuelve un proyecto tiene que estar al tanto de los avances de éste, y saber qué es lo que se quiere lograr, para así poder encontrar y resolver malentendidos. Todos saben que las cosas van a cambiar, pero no saben qué va a cambiar.  

## El feedback es la herramienta fundamental
En esta sección el autor describe que un equipo trabaja mejor con ciclos anidados de feedback, siendo los ciclos de adentro, los más pequeños, se centran en el detalle técnico: qué hace una porción de código y cómo se integra al sistema, unit tests. Los ciclos de afuera o más grandes se refieren a organización del equipo y del sistema y cómo sirve a las necesidades del usuario.  
Si algo se le escapa a un ciclo de adentro, lo atrapa el de afuera. Cuanto antes se pueda tener feedback, mejor. Esta metodología de trabajo hace que el proyecto sea iterativo e incremental, desarrollando funcionalidades de a poco, estando siempre integradas, y no creando mucho e integrando al final.  

## Prácticas que soportan cambios
- Tests automatizados
- Mantener el código lo más simple y legible posible y si es necesario hacerle un refactor

## Ventajas del TDD
- Te da la calma de codear sabiendo que todo está controlado
- Te ayuda a separar diseño de implementación
- detecta errores apenas ocurren y cuando está fresco el causante

## Los tests de aceptación (end-to-end)
Se tratan de probar el sistema completo, pero desde la interfaz de usuario, sin acceder al codigo interno, actuando como su ambiente, como sistemas de terceros, usando sus servicios web, etc.  

## Recapitulación: Jerarquía de testing
- Aceptación: ¿El sistema entero anda?
- Integración: ¿Nuestro código anda frente a código que no podemos cambiar?
- Unitarios: ¿Nuestros objetos hacen lo correcto? ¿Son convenientes para trababjar con ellos y entre sí?

## Calidad externa e interna
La **calidad externa** es de cara al usuario, si es funcional, responsive, rentable, etc. 
La **calidad interna** es cómo se adapta a las necesidades del equipo: si es fácil de modificar, de entender, etc.

Son más fáciles de mantener las funciones o features con menos dependencias, siempre es mejor mantenerlas con la menor cantidad de dependencias posibles.  

Las clases deben tener coherencia, tener un sentido, realizar las responsabilidades que le corresponden por completo y dejarle a los demás lo que no es propio de ellas.  