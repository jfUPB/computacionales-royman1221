Valores en la Memoria:
* En hexadecimal, 0a es 10 en decimal.

* En hexadecimal, 14 es 20 en decimal.

Observación: Los bytes se almacenan en orden little-endian, lo que significa que el byte de menor peso se almacena primero en la memoria. Esto es característico de muchas arquitecturas modernas, como x86.


Diferencia entre Constructor y Destructor en C++:
* Constructor: Un constructor es una función especial de la clase que se invoca cuando se crea un objeto. Su propósito principal es inicializar los datos del objeto. En este caso, se usa para asignar valores a las coordenadas x y y del objeto Punto.

* Destructor: El destructor se llama automáticamente cuando el objeto sale de su ámbito (por ejemplo, al final del bloque de código donde se declara). Su principal objetivo es realizar la limpieza necesaria, como liberar recursos que el objeto pudo haber adquirido durante su vida útil (por ejemplo, memoria dinámica, archivos abiertos).


Diferencia entre Objeto y Clase en C++:
* Clase: Una clase es una plantilla o molde que define el diseño de un objeto. Es una estructura que define los datos y comportamientos que los objetos creados a partir de ella tendrán.

* Objeto: Un objeto es una instancia concreta de una clase. En otras palabras, es un "miembro" o una "copia" que existe en la memoria en el momento de ejecución, con datos específicos asignados a sus atributos.


Diferencias entre Punto en C++ y C#:
* C++: En C++, la declaración Punto p(10, 20); crea un objeto de la clase Punto directamente en la memoria stack. Esto significa que el objeto se almacena dentro de la pila del sistema, y será destruido automáticamente cuando salga del ámbito.

* C#: En C#, Punto p = new Punto(10, 20); crea un objeto en el heap, y la variable p es simplemente una referencia que apunta a la dirección de memoria del objeto. El recolector de basura (garbage collector) se encarga de liberar la memoria del objeto cuando ya no es utilizado.


¿Qué es p en C++ y qué es p en C#?
* C++: En C++, p es un objeto en sí mismo. Al ser creado en el stack, el sistema de ejecución asigna la memoria directamente para el objeto p.

* C#: En C#, p es una referencia a un objeto. No almacena el objeto en sí, sino que mantiene una dirección de memoria en el heap donde reside el objeto real.


Parte de Memoria donde se Almacena p:
* C++: En C++, cuando declaras Punto p(10, 20);, el objeto se almacena en el stack. El stack es una región de memoria que gestiona automáticamente la creación y destrucción de objetos según su ámbito.

* C#: En C#, la referencia p se almacena en el stack, pero el objeto real de tipo Punto se encuentra en el heap. La referencia es un puntero que indica la dirección del objeto en el heap.


¿Qué es un Objeto en C++ Según lo Observado?

Un objeto en C++ es una instancia concreta de una clase, con sus propios valores específicos y métodos. En este caso, Punto es la clase que define los datos x e y, y p es el objeto que tiene valores concretos para esas coordenadas. El objeto es almacenado en la memoria stack (si no se usa new), y su ciclo de vida está vinculado al ámbito donde se crea.




