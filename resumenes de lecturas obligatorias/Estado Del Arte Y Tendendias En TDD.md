## Desventajas de la TDD
1.  Basa todo en desarrollo unitario, sin una vista en conjunto
2.  se critica la pretensión de que el diseño evolucione solo, sin una planificación previa
3.  No permite probar interfaces de usuario
4.  Es una práctica centrada en la programación, no sirve para testers
5.  Los cambios medianos y grandes suelen exigir cambios en las pruebas

## Mocks
El mocking llegó como solución a la problemática 1. Acá los distintos tipos de mocks
- dummy: no se usa en la prueba, ej: se envia como parámetro pero no es el objeto de prueba
- stub: reemplaza un objeto real, generalmente para generar entradas de datos no impulsar funcionalidades del objeto que esta siendo probado.
- spy: verifica los mensajes que envía el objeto durante la prueba
- mock: reemplaza a un objeto real para observar los mensajes enviados a otros objetos desde el receptor
- fake: reemplazan a un objeto del sistema con una implementación alternativa

## Pruebas de cliente de XP
Kent beck planteaba en XP, tener un representante del cliente en el equipo de desarrollo, pero aun así, son pruebas técnicas basadas en el diseño y no en los requerimientos del cliente.

## Acceptance TDD: el punto de vista de los requerimientos y del comportamiento
Se basa en la idea central iterativa de TDD pero empezando por tomar user stories con el usuario, basándose en ellas hacer pruebas de aceptación, y por cada una de ellas hacer todo el ciclo de TDD.  
Las pruebas de aceptación de una user story se convierten en las condiciones de satisfacción del mismo, y así los criterios de aceptación se vuelven ejecutables.

## Behavior-Driven Development
(Influenciada por Domain Driven Design (DDD), de Eric Evans)
En vez de pensar en pruebas, pensar en comportamiento o especificaciones. De esa manera es más fácil de validar, y se logra más abstracción, escribiendo las pruebas desde el punto de vista del consumidor.  
Pruebas integrales, de porciones de comportamiento del sistema, no de clases y metodos. Una clase de prueba por requerimiento o user story
Críticas: Es solo un cambio de nombre a TDD. Es solo TDD bien hecho.

## BDD vs ATDD
Ambas pusieron énfasis en que no son pruebas de pequeñas porciones de código, sino especificaciones de requerimientos ejecutables. Ponen el foco en que el software se construye para dar valor al negocio por encima de lo técnico.  

Unit TDD facilita un buen diseño de clases, y ATDD y BDD construir el sistema correcto.  

## Story TDD: ejemplos como pruebas y pruebas como ejemplos
Plantea que cada rol de la organizacion pide o da ejemplos que podrían servir como complementos de requerimientos: el cliente le da ejemplos de uso al especialista de negocio, este a los desarrolladores, los desarrolladores hacen tests unitarios basandose en ejemplos de entradas y salidas, etc.  
Por lo tanto, plantea especificar los requerimientos con ejemplos.  
- Sirven como herramienta de comunicacion
- Se expresan por extensión en vez de con largas descripciones y reglas propensas a libre interpretacion
- Son mas sencillos de acordar con clientes, mas concretos.
- Evitan que se escriban ejemplos distintos
- Sirven como pruebas de aceptacion  

Tiene su enfoque en la comunicación y la captura de requerimientos.

## El foco en el diseño orientado a objetos: NDD
A principios de la POO y hasta la creacion de la ley de demeter, el codigo se veia atravesado por consultas de estado. Luego de la ley de demeter, nos encontramos con otro problema: para testear los cambios de estado de un objeto tras la invocación de uno de sus métodos, nos vemos obligados a ponerle getters solo por las pruebas.

## Una propuesta de solución: Need-Driven Development
Steve Freeman y otros tres autores, plantean que el comportamiento de los objetos debería estar definido por cómo envía mensajes a otros objetos, además de los resultados devueltos. Pretende resolver un buen diseño orientado a objetos y separacion de incumbencias, basandose en:
- Mejorar el código con términos de dominio
- Preservar el encapsulamiento
- Reducir dependencias
- Clarificar las interacciones entre clases
Acá nacen los Mocks, ante la necesidad de testear el comportamiento de una clase, conocienco la interfaz y el impacto de esta sobre las clases vecinas.  
A veces sirve para testear.

### Recomendaciones:
- Generar mocks solo para clases que podamos cambiar, no para externas.
- Solo generar mocks a partir de interfaces y no de clases.
- Generar mocks solo para los vecinos inmediatos del que está a prueba
- Evitar un orden de invocación
- Si se usan muchos mocks en la misma prueba, quizá el objeto tiene demasiadas responsabilidades

## Discusion sobre pros y contras 
### PROS:
- Cumple a rajatabla programar contra interfaces
- Pruebas menos acopladas a la implementación
- Promueve el ocultamiento de implementación
### CONTRAS
- Es sensible a los refactors por el uso de mocks, ya que buscan los nombres de los métodos por reflexión
- Usado por gente inexperta empeora el acoplamiento y la localizacion de responsabilidades
- Resulta costoso crear los mocks necesarios

## Pruebas de interacción y TDD
Pero hasta ahora no hablamos de testear la interfaz de usuario, y aunque hay herramientas para hacerlo, la mayoría de eminencias de la POO dicen que es mejor no probarla ya que es lo que más cambia, hay que cambiar los tests muy seguido.

### Limitaciones de las pruebas de interacción
Los problemas que suelen tener las pruebas automatizadas de interacción por grabación son:
- Sensibilidad al comportamiento: cambios en el modelo llevan a cambios en la interfaz y que sus pruebas dejen de funcionar
- Sensibilidad a la interfaz: cambios pequeños rompen las pruebas
- Sensibilidad a los datos: cuando hay cambios en los datos que se usan para correr la aplicación, los resultados que esta arroje van a cambiar
- Sensibilidad al contexto: si cambian los dispositivos externos se rompen las pruebas.
- Son lentas

### Cuidados al automatizar estas pruebas:
- Probar por separado el modelo y la ui
- Evitar automatizar si la ui es muy cambiante
- Hay que volver a generarlas cada tanto dada su fragilidad

Las pruebas de cliente y de propiedades, automartizarlas con herramientas específicas.  
Las pruebas unitarias y de componentes, con xUnit.  
Las de usabilidad y exploratorias, de forma manual.  

## Estudios del uso de TDD en la práctica

Los siguientes resultados cuantitativos fueron tomados por empresas que hicieron proyectos con TDD y sin TDD.  

### El uso de TDD refleja:
- Una gran mejora de calidad externa y de las pruebas funcionales que pasan
- Más tiempo de desarrollo, aunque se desconoce si se tiene en cuenta el retrabajo al corregir errores al no usar TDD.
- Exigiendo la misma cantidad de pruebas con o sin TDD, los que usaron TDD tuvieron mejor tiempo y calidad.
- Un buen descenso en la cantidad de errores introducidos al hacer cambios.
- Un buen descenso en el tiempo de correccion de errores y de cambios
- El tamaño del código usando TDD es menor 

### Resultados cualitativos:
- Algunos desarrolladores manifestaron más deseo de usar TDD
- Al ajustarse los cronogramas o no comprender del todo TDD, las organizaciones la ponen en riesgo.
- Cuando hay muchas trabas, los desarrolladores dejan TDD
- La satisfacción es mayor al ver todo en verde
- En proyectos chicos, no se valora la calidad interna que da TDD, se ve como una pérdida de tiempo y escribir más código.

### Cuestiones no medidas:
- Calidad de los casos de prueba
- Flexibilidad frente a un cambio de requisitos
- No se puede asegurar que se haya hecho TDD
- No se mide tanto la calidad interna

## Estudios sobre variantes de TDD mas allá de UTDD
### Un estudio sobre STDD arroja que:
- Se realizan pruebas de regresion a menor costo
- Mejores tiempos debido a la facilidad de adaptarse a los cambios de requerimientos por la participacion del cliente
- Mas confianza en cuanto a entregables debido a la comunicación
- Mayor conciencia sobre necesidad de pruebas
- Bastantes cuestionamientos a las herramientas para refactorizar pruebas
- Es complicado organizar y agrupar las pruebas

## Limitaciones de TDD y afines
### Situaciones en que TDD no es buena idea:
- Para mantener software que no usó TDD en sus versiones anteriores
- Para diseño e interfaces de usuario
- Para operaciones contra bases de datos, cuesta mucho tiempo
- Para infraestructura de servicios web.