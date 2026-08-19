# Getter Eradicator

Hay gente que dice que los getters son una violación del encapsulamiento.  

Fowler sugiere crear los getters cuando **realmente** los necesites.  

Encapsulamiento no es esconder datos porque sí, es esconder el diseño y la implementación, sobretodo donde esté sujeto a cambiar.  

Según Kent Beck y Martin Fowler, hay que tener cuidado en los casos en que se llama más de un método en el mismo objeto.  

Las clases anémicas deben llamar la atención del programador, hay que ver quién está usando sus getters y ver si se puede llevar la clase a ahí o preguntarse: ¿Me puedo deshacer de este getter?  

Las cosas que cambian juntas tienen que estar juntas, ya sea a nivel de paquete o de clase.

Autor: Martin Fowler