Miembros de instancia:

* Son variables que pertenecen exclusivamente a cada objeto creado a partir de una clase.

* Cada objeto mantiene su propia copia, almacenada en memoria de manera independiente.

* Su ubicación depende del modo de creación del objeto:

* Si se instancia directamente, suele ubicarse en la pila (stack).

* Si se crea dinámicamente, se aloja en el montículo (heap).

* Ventajas: Permiten encapsular el estado propio de cada objeto, lo cual favorece el diseño orientado a objetos.

* Desventajas: Si se crean muchas instancias, puede implicar un mayor consumo de memoria, ya que cada una conserva sus propios datos.

* Cuándo usarlos: Cuando cada objeto necesita manejar información distinta a los demás.



Miembros estáticos:

* No pertenecen a instancias concretas, sino a la clase como tal.

* Existe una sola copia compartida entre todos los objetos de esa clase.

* Se almacenan en el segmento de datos estáticos del programa, al igual que las variables globales.

* Ventajas: Ahorra memoria cuando se necesita un valor común entre todos los objetos; ideal para contadores o configuraciones globales de clase.

* Desventajas: Introduce un estado global que puede generar conflictos si no se maneja correctamente, especialmente en entornos multihilo.

* Casos de uso: Muy útil para llevar registro del número de objetos creados, implementar constantes globales, o funciones compartidas.




Distribución en memoria
* c1 y c2: Son objetos locales creados en main, por lo que residen en la pila. Se destruyen automáticamente al finalizar el alcance de la función.

* c3: Es un puntero, y como tal, su dirección está en la pila, pero apunta a un objeto creado dinámicamente con new, que vive en el montículo (heap) hasta que se libera con delete.

* Objeto al que apunta c3: Está en el heap, gestionado manualmente por el programador.

* Contador::total: Al ser estático, se encuentra en la sección de datos globales (data segment). Su ciclo de vida abarca toda la ejecución del programa, independientemente de cuántos objetos existan.
