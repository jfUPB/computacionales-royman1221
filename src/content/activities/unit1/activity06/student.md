1. ¿Qué es el direccionamiento directo? ¿Cómo se utiliza en el lenguaje ensamblador Hack?

El direccionamiento directo es un método para acceder a posiciones específicas de memoria, utilizando una dirección concreta. En el lenguaje Hack, se emplea la instrucción @n, donde n representa una dirección de memoria exacta. Por ejemplo, @5 hace referencia a la dirección de memoria 5.

2. ¿Qué significa M=D en lenguaje ensamblador Hack? ¿Y D=M?

* M=D: Asigna el valor del registro D a la dirección de memoria indicada por el registro A.
Ejemplo: Si D=25 y A=6, la instrucción M=D colocará 25 en RAM[6].

* D=M: Carga en el registro D el valor que se encuentra almacenado en la dirección de memoria especificada por A.
Ejemplo: Si RAM[3] = 42 y A=3, la instrucción D=M pondrá 42 en D.

3. ¿Qué es un “puntero” en el contexto de la memoria?

Un puntero es una variable que guarda la dirección de otra ubicación en memoria, permitiendo acceder a esa información de manera indirecta. En Hack, el registro A actúa como un puntero, almacenando direcciones de memoria.


```asm
@50    // Se coloca la dirección 50 en el registro A (A actúa como puntero)
D=A    // El valor 50 se copia en el registro D
@200   // Ahora A apunta a la dirección 200
M=D    // El valor de D (50) se almacena en RAM[200]
@200   // A apunta nuevamente a la dirección 200
A=M    // A ahora contiene el valor almacenado en RAM[200], que es 50
D=M    // D obtiene el valor almacenado en la dirección apuntada por A, que es 50

```
