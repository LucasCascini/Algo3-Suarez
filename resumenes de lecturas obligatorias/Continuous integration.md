# Integración Continua

La integración continua, a veces llamada Trunk-Based Development (TBD) es una práctica en la que los integrantes de un grupo mergean sus cambios a un repositorio todos los días. Cada integración es verificada automáticamente para evitar romper lo que ya funciona, y esto reduce el costo de agregar cosas nuevas y lo vuelve más rápido.

## Procedimiento de continuous integration
- pull para estar actualizado
- si hay un comando para construir el ambiente o compilarlo, lo uso para ver que funcione bien 
- agrego lo nuevo, atiendo los tests que se rompan
- cuando todo está listo, hago un pull de nuevo por si alguien subió algo
- construyo todo de nuevo para probar
- si alguien modificó algo y se rompen tests, reviso los commits míos y ajenos para ver quién introdujo el problema y arreglo todo

## Prácticas de CI
### Usar git
Agregandole todo lo necesario para que un nuevo integrante pueda usar el repositorio.  

_I should be able to walk up with a laptop loaded with only an operating system, and by using the repository, obtain everything I need to build and run the product._  

Debería encontrarse en el repositorio, en los cambios de cada momento, los recursos que se necesitan en ese momento para levantar el proyecto. Se puede hacer guardando un link a la versión a descargar de cada recurso, nunca usando latest.  

Tiene que haber una clara rama que sea el estado actual del producto, lo próximo a enviar a producción.  

##  Automatizar la construcción

Es repetitiva y hacer que los desarrolladores tengan que usar muchos comandos o tocar cuadros de texto, es una pérdida de tiempo y fuente de errores. Mejor usar comandos de make que hagan todo

## Pushear todos los días

Mientras que un programador pueda mergear main a su rama, resolver conflictos, los tests sigan pasando, está habilitado de mergear sus cambios a main. Hay que pushear seguido para encontrar los conflictos rápido y que no lleguen a crecer en el tiempo.

La red de testeo alerta de conflictos de semántica que no pudo detectar el ide, sobretodo en tipado dinámico que no se queja el compilador y los bugs pasan desapercibidos.

## Automatizar chequeos

En la rama main debería haber una build que se encargue de no permitirle integrar sus cambios al desarrollador si no cumple con, por ejemplo, tests, un linter, etc.

## Arreglar problemas en la build rápido

_"Nadie tiene una mayor prioridad que arreglar la build"_, Kent Beck.
Algunos equipos usan una rama previa a main, para correr la build antes, de esta manera main no se contamina de commits con bugs, y nadie trabaja con errores ni deben hacer revert de commits con bugs.

## Mantener la build rápida

No debe tardar más de 10 minutos.  
Los tests que más tardan son los que abarcan recursos externos como bases de datos, esos podrían llevar horas. Lo que se hace para resolverlo es mockear la base de datos, y tener dos escalones de testeo, uno que corra los unitarios y rápidos, por cada commit. 

Y otra build secundaria que corra los largos, lo más frecuentemente posible, tomando un commit verde.  
De esta manera todos trabajan con una build corta, a la espera de ver qué pasa con la larga.  
Cada error en la build larga requerirá un test en la commit build.  
Hay que revisar actualizaciones de las dependencias diariamente.

## Testear en clones de Producción

Hacer builds de testeos por cada plataforma, sistema, ip, puertos, y condiciones en las que un usuario consumirá el producto. Incluso emular mal internet, un mal dispositivo.

## Que todos sepan lo que está pasando

Algunos equipos logran que discord, slack, o la plataforma que usen para comunicarse, les notifique cuando hubo un commit rojo o verde. Los que comparten un ámbito físico quizás tienen una pantalla que muestra el color de los ultimos commits.

## Automatizar el despliegue

Se deben tener scripts para desplegar sin mucho esfuerzo. Esto garantiza desplegar más rápido, varias veces en el día, en producción, con técnicas para no exponer en la interfaz de usuario los nuevos cambios.

Se puede tener también un mecanismo para revertir los últimos cambios hasta el último commit verde por si acaso.

# Tipos de integración

## Integración Pre-lanzamiento
Todos trabajan en cosas distintas sin saber sobre el resto y cuando todos tienen su parte terminada, se integran todas esas partes.

## Semi-integración
Por cada funcionalidad realizada por un individuo, los otros tienen que pullearla, mergearsela y continuar trabajando

## Integración continua
Todos pullean y pushean a diario. Se resuelven muchos conflictos y se adaptan merges muy seguido, pero son tiempos de corrección menores

# Pros de CI
- Menos riesgo de tardar días, semanas o meses integrando, y es más previsible lo que se tardará en integrar
- Menos tiempo perdido en integración
- Menos bugs, se encuentran más rápido y más pequeños
- Más capacidad de refactor, equipos que integran continuamente pueden refactorear continuamente, cambios pequeños que mantengan el comportamiento y mejoren la calidad del diseño
- Los lanzamientos son decision de la empresa: al estar todo integrado, la linea main está siempre lista para lanzarse cuando está en verde.

# Cuando NO usar CI
- cuando no se trata de un equipo dedicado fulltime al proyecto
- cuando el equipo no tiene una red fuerte de testeo, porque llevaría a miles de bugs sin encontrar.

# Preguntas frecuentes
De dónde viene CI? 
> Kent beck, en extreme programming

Se puede usar un servicio CI en ramas por funcionalidad?
> Sí, pero la idea es que sea en mainline para obligarte a pushear seguido.

Puede un equipo hacer feature branching y CI a la vez?
> No, son enfoques distintos. Y usar un servicio CI en feature branching No es hacer CI.

MARTIN FOWLER