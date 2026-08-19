# Immutability is not Enough  

El texto muestra una implementación imperativa de un juego básico que tiene un personaje en medio. Lo traduce a código funcional dejando este mensaje:

- Se puede modelar cambios de estado tomando un estado por parámetro y retornando un nuevo estado, y haciendo pipeline de las acciones.
- En ese pipeline, si se ordena de cierta manera podría tener bugs (lo que se busca evitar con functional programming)

Después, vuelve a modificarlo, pero esta vez las funciones pueden devolver un StateUpdate o un []. 
- Se concatena un pipeline de updates
- Se pasan esos updates a una funcion applyUpdates().

Problema: con esta implementación, nadie conoce los cambios que se hicieron durante el pipeline hasta la próxima iteración. Y se mantiene el problema del orden de las funciones.

Entonces, la programación funcional no evita problemas de estado, los eleva a otro nivel de abstracción.

La programación se trata de construir modelos, abstracciones que tienen ciertas propiedades y reglas. Las inmutables son solo una de esas abstracciones.

## Side Effects
Se puede modelar que si hay más de una actualización en cierto punto, se lance un error. Esto marcaría que hay una dependencia de ordenamiento entre dos componentes.

Los sistemas de efectos, manejan efectos laterales. Son una solución a los problemas de estado en programación funcional pura, pero aun así, teniendo un programa puramente funcional, este será susceptible a sufrir problemas de estado.

