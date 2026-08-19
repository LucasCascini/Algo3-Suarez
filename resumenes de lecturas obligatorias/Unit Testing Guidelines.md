# Unit Testing Guidelines
- Que sean cortos y rápidos
- 100% automáticos y nada interactivos
- Que corran con un comando o un click
- Analizar la cobertura de los tests
- Cuando un test falla, arreglar urgente el código que lo causó
- Una clase de testeo por cada clase y aunque sea tentador, mantener el testeo unitario.
- Empezar desde lo mas pequeño y simple como crear un objeto y verificar que se creó
- Los tests tienen que ser independientes y no depender del orden en que son ejecutados
- Mantener los tests en el mismo directorio que la clase a testear
- Que cada test pruebe una única cosa y tenga un nombre descriptivo
- Si métodos privados requieren testing, es mejor hacerlos públicos en una clase de utilería
- Actúa como un consumidor de la clase, testeando si cubre todos los requisitos por sí sola
- Testear los casos de lógica más complejos
- Testear los casos triviales, a veces por copiar y pegar puede haber errores en los casos más básicos como un getter o setter
- Probar la cobertura actual, muchos casos
- Probar los casos bordes, en enteros 0, nan, infinito, positivo, negativo, en strings vacío, un caracter, etc.
- Testear los casos del medio con un generador random y bucles de muchos ciclos
- Testear solo lo que dice el nombre del test en el menor codigo posible
- Usar asserts explícitos, dan información más precisa del error en cuestión
- Testear que se lancen las excepciones indicadas
- Codear pensando en los testeos
- Si se necesita contenido externo, debe estar disponible para el test, preferentemente dentro del proyecto
- La cobertura estimada es del 80%, hay partes que cuesta cubrir como caídas de servidores o de las bases de datos, manejo de excepciones con recursos externos.
- Priorizar los tests: arreglarlos apenas se rompen
- Evitar que haya cortes de ejecución del entorno de testeo por comportamientos excepcionales o inesperados dentro de un test
- Cuando hay un bug, hacer un test y tomarlo como criterio de corrección del bug
- Que sea corto y simple, te das cuenta que no lo es cuando pareciera que el propio codigo del testeo necesita testeos

Los testeos no pueden probarlo todo y asegurar que el código esté bien. Sí son un buen inicio para chequear que se sigan cumpliendo las invariantes, confirmar que el código siga funcionando bien luego de algún refactor, para documentar. El testeo te ayuda a pensar en cómo mejorar el código.