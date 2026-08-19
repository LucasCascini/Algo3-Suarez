# The Art Of Enbugging

Los bugs aparecen por nuestra culpa, no llegan solos. Una buena forma de evitar futuros bugs es mantener una separación de conceptos, es decir, que las clases tengan una intención bien definida, responsabilidades propias y buena semántica.  

El objetivo es hacer código "tímido", que no le guste revelar cosas a otros ni hablarle a otros más de lo necesario.  

Le pedimos al objeto qué hacer, no le preguntamos su estado y en base a eso le decimos qué hacer. Como el invocador, no tomamos decisiones en base al estado del receptor y luego le pedimos que cambie su estado.  


## La Ley de Demeter
Un objeto solo puede llamar 4 cosas:
- A sí mismo
- Los parámetros del método
- Los objetos que creó
- Los objetos que contiene directamente

#### Autores: Andy Hunt and Dave Thomas, "The pragmatic programmers"