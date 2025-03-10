¿En qué direcciones de memoria se implementan las variables i y sum?
En el ensamblador Hack, las variables como i y sum se almacenan en direcciones de memoria específicas asignadas por el ensamblador. Generalmente, si no se indica una dirección explícita, las variables empiezan a asignarse desde la dirección de memoria 16 en adelante (RAM[16], RAM[17], etc.).
En este caso:

* i puede estar en RAM[16]
* sum en RAM[17]
  
Aunque la ubicación exacta puede variar, en el simulador del curso suele asignarse así automáticamente.

¿Cuál es la diferencia entre la dirección de una variable y su contenido?

La dirección de una variable es el lugar específico en la memoria donde se guarda el valor de la variable (como una casilla numerada). Por ejemplo, si i está en RAM[16], entonces 16 es la dirección.
El contenido de la variable es el valor que esa dirección almacena en un momento dado. Por ejemplo, si i = 50, entonces en RAM[16] se encuentra el número 50.
En el simulador, puedes ver claramente esta diferencia al observar la dirección y lo que contiene cada celda de RAM.

¿Cómo se implementa la condición i <= 100?
La condición i <= 100 se traduce en estas instrucciones:

``` asm
@i
D=M        // D = i
@100
D=D-A      // D = i - 100
@END
D;JGT      // Si (i - 100) > 0, salta a END
```


ste código compara el valor de i con 100 restando 100 - i. Si el resultado es mayor que 0 (D;JGT), significa que i ha superado 100 y el programa debe salir del ciclo (goto END). Si no, el ciclo continúa.
En términos de lógica:

* Si i es menor o igual a 100, el ciclo sigue.
* Si i es mayor que 100, se sale del ciclo.
