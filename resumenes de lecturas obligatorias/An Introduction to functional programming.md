# Definición
Se caracteriza por la ausencia de efectos colaterales. No depende de, ni modifica a, cosas de fuera de la función.  
Usar operaciones que no son funcionales (modifican el elemento recibido por parámetro), hace que nuestras funciones dejen de ser funcionales puras.

## Map
Toma una función y una colección, y devuelve una nueva colección con los resultados de aplicarle la función a cada elemento de la colección original

## Reduce
Toma una función y una colección de elementos, y devuelve un nuevo elemento que es una combinación de los originales. Ejemplo de un Sum hecho con reduce:

reduce(lambda a, x: a + x, [0, 1, 2, 3, 4])

(a) es el acumulador, (x) es el elemento siendo evaluado en la iteración, y retorna (a) al terminar de recorrer los elementos. Inicia la iteración con (a) valiendo lo mismo que el primer elemento, u ofrece un tercer parámetro para pasarle el valor inicial de (a)


## Por qué map y reduce?
- Son de una línea
- Son operaciones elementales. Quien lea el código leerá más fácil esa línea que todo un for
- Las partes importantes de la iteración están siempre en el mismo lugar en los map y reduce
- El codigo en un loop puede tener efectos laterales

### Escribir código de manera declarativa

Escribir código de manera declarativa es, usar funciones con un buen nombre que describa qué hacer, no cómo hacerlo.

### Usar Funciones
El programa puede ser más declarativo agrupando secciones de código en funciones.  
Vuelve el código más legible y quita comentarios.  
Priorizar recursividad por sobre iteración  

### Para saber que un programa es funcional
- Las funciones reciben parámetros
- No hay variables compartidas ni globales
- No se declaran variables en las funciones.

### Usar pipelines
El trabajo de un pipeline es recibir una colección de elementos y una colección de funciones. Pasa cada elemento de la colección por la primer función y agrupa los resultados en una nueva colección de elementos. Después los pasa por la segunda función, y así hasta que termine.  

### ¿Y para qué lo uso?
Convive muy bien con código de otros paradigmas y lenguajes.  

## Conclusión
- Convertir las iteraciones en maps y reduces
- Descomponer el código en funciones, volverlas funcionales y hace una recursión
- Convertir una secuencia de operaciones un pipeline

