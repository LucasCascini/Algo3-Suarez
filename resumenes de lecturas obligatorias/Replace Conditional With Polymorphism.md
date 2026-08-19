# Replace Conditional With Polymorphism

En este artículo se explica paso a paso cómo reemplazar condicionales o switch que se basan en:
- La clase del objeto o interfaz que implementa
- Valor del atributo de un objeto
- Resultado de llamar un metodo de un objeto

Es necesario hacerle un refactor y usar polimorfismo porque la aparición de un nuevo tipo o atributo haría que tuvieras que ir a cada switch a agregarlo.  

La solución es que cada una de esas clases hereden de una clase abstracta o implementen una interfaz.