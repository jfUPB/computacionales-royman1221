Los dos programas en C++ son equivalentes porque realizan exactamente la misma operación: sumar los números del 1 al 100. La diferencia está en la forma en que se expresan:

* El while inicializa la variable antes del ciclo y luego incrementa i dentro del cuerpo del ciclo.
* El for agrupa la inicialización, la condición y el incremento en una sola línea, pero la lógica es la misma.
  
Versión en ensamblador de la estructura for:


´´´asm 
// Adds 1+...+100 usando for.
@sum      // sum = 0
M=0
@i        // i = 1
M=1

(LOOP)
@i
D=M       // D = i
@100
D=D-A     // D = i - 100
@END
D;JGT     // Si i > 100, salta a END

@i
D=M       // D = i
@sum
M=D+M     // sum = sum + i

@i
M=M+1     // i = i + 1

@LOOP
0;JMP     // Vuelve al inicio del ciclo LOOP

(END)
@END
0;JMP     // Bucle infinito para terminar el programa
´´´'"""
