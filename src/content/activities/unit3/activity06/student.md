 Experimento 5 – Variables locales estáticas vs no estáticas
En este experimento se analiza la diferencia entre variables locales con y sin el modificador static.

La variable local no estática (var_no_estatica) se define dentro de una función y se inicializa en cada llamada. Como se almacena en el segmento de Stack, su tiempo de vida está limitado al bloque donde se declara. Por lo tanto, al entrar y salir de la función, esta variable se destruye, y su valor siempre inicia en 100 cada vez que se ejecuta la función.

Por otro lado, la variable local estática (var_estatica) también se declara dentro de una función, pero gracias a la palabra clave static, se guarda en el segmento de datos. Esto significa que conserva su valor entre llamadas. En el experimento, su valor comienza en 100, pero a medida que se llama varias veces a la función, su valor se incrementa y se mantiene en memoria.

Este comportamiento permite comprobar que:

* Las variables locales no estáticas se destruyen al finalizar la función.

* Las variables locales estáticas conservan su estado entre invocaciones y no se reinicializan.

Experimento 6 – Modificar el segmento de Heap
En este experimento se asigna memoria dinámica para un arreglo usando new[], lo cual coloca los datos en el segmento de Heap. Luego, se inicializan los elementos y se imprimen sus valores y direcciones de memoria. Después, se libera la memoria con delete[].

Posteriormente, se intenta acceder al arreglo después de haberlo liberado. Esta acción genera un comportamiento indefinido, ya que el programa intenta acceder a memoria que ya fue marcada como libre por el sistema. Aunque a veces no genera un error inmediato, puede provocar bloqueos o fallos impredecibles, como un segmentation fault o corrupción de memoria.


Diferencias entre el Heap y el Stack:

Stack:

* La memoria se gestiona automáticamente.

* Se libera al salir del ámbito de la función.

* Más rápido, pero con espacio limitado.

* Ideal para variables temporales y locales.

Heap:

* La memoria se gestiona manualmente con new y delete.

* Permite reservar memoria durante la ejecución.

* Es más flexible, pero propenso a errores si no se gestiona correctamente.

* Ideal para estructuras dinámicas (como arreglos que crecen).

Consecuencia

* En los experimentos realizados, se observó que las variables locales estáticas conservan su valor entre llamadas a funciones, mientras que las no estáticas se reinician en cada ejecución de la función. En cuanto a la gestión de memoria, el uso de la memoria dinámica en el Heap requiere asignación y liberación manual mediante new y delete[], y acceder a memoria liberada provoca un comportamiento indefinido, como fallos o corrupción de memoria. Las diferencias entre Heap y Stack radican en la flexibilidad del Heap frente a la automatización y limitación del Stack, y es crucial liberar correctamente la memoria en el Heap para evitar fugas, que pueden ralentizar o inhabilitar el programa.
