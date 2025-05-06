En el Stack:

* El objeto es creado dentro de un bloque {} y su existencia está limitada a ese alcance.

* Se llama al constructor al iniciar el bloque y al destructor al finalizarlo.

* La memoria se libera automáticamente, sin necesidad de intervención del programador.


En el Heap:

* El objeto se construye con new y permanece en memoria hasta que se libera explícitamente con delete.

* El constructor se ejecuta al hacer new, y el destructor solo se invoca si se hace delete.

* La memoria debe ser gestionada manualmente por el desarrollador.



* ¿Por qué pBloque se destruye y pBloque2 no?
  
pBloque es un objeto directo en el stack, su memoria se gestiona automáticamente y se destruye al salir del bloque.
pBloque2 es un puntero, y el objeto al que apunta vive en el heap. Como el heap no se libera automáticamente, ese objeto permanece hasta que se haga delete.

* ¿pBloque2 es un objeto o una referencia?
  
Es un puntero, o sea, una variable que contiene una dirección de memoria de otro objeto.

* ¿Dónde está almacenado pBloque2?
  
En el stack, porque es una variable local del main.

* ¿Y el objeto al que apunta pBloque2?
  
Ese vive en el heap, ya que fue creado dinámicamente con new.
