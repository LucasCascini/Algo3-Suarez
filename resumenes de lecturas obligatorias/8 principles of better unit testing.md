# 8 Principles of better Unit Testing
Los tests unitarios son cortos, rápidos y chequean una funcionalidad particular de un método. Y al fallar se nota CLARAMENTE el motivo.  

1. Saber qué estás testeando: A veces un mismo método lleva muchos tests, idealmente uno precondicion, postcondicion, condicional o acción que realiza.
2. Ser autosuficiente: evadir librerías, configuraciones, registros, bases de datos, etc. 
3. Para un mismo código, tiene que funcionar siempre, no depender por ejemplo de la máquina. Esquivar datos random porque si hay un bug después es imposible reproducir el error
4. Nombre muy descriptivo sin importar que sea largo
5. En unit testing no es mala práctica repetir código, si varios tests hacen cosas muy parecidas sobre el mismo feature, es preferible tenerlos por separado a unificarlos
6. Probar resultados (returns, excepciones, metodos publicos) y no implementación (metodos privados, funcionamiento interno de la clase)
7. No hacer tests super estrictos que por ejemplo testeen que un método sea llamado tres veces, mejor usar comportamiento default de los otros objetos.
8. Usar isolation frameworks que sirven para crear e instancias objetos falsos, para usarlos cuando se quiere testear un objeto con dependencias.

#### AUTOR: DROR HELPER