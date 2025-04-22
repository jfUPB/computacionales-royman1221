Función de cada tipo de instrucción:
* A-Instrucciones (Instrucciones de A):
  
Las A-Instrucciones son las que se utilizan para cargar una dirección de memoria en el registro A, o un valor inmediato, que puede ser un número literal. Esto es esencial para el acceso y manipulación de la memoria dentro del programa.

* Función: Establece la dirección de memoria en el registro A o carga un valor inmediato.

* Representación binaria: Se representa como un 0 seguido de 15 bits que corresponden al valor numérico que se va a cargar.

Formato binario: 0vvvv vvvv vvvv vvvv (donde v son los valores en binario)

Ejemplos:

1. @50: Carga el valor 50 en el registro A.

* Binario: 0000 0000 0011 0010

2. @200: Carga el valor 200 en el registro A.

* Binario: 0000 0000 1100 1000

3. @1000: Carga el valor 1000 en el registro A.

* Binario: 0000 0011 1110 1000

C-Instrucciones (Instrucciones de C):

Las C-Instrucciones son mucho más versátiles, ya que permiten realizar cálculos, almacenar resultados en registros, y controlar el flujo del programa mediante saltos condicionales. Estas instrucciones están divididas en tres componentes: la operación de cálculo (comp), los registros de destino donde se almacenarán los resultados (dest), y las condiciones de salto (jump).

* Función: Permite ejecutar operaciones de cálculo, asignar resultados a registros y realizar saltos condicionales.

* Representación binaria: Se representa con un 1 al principio, seguido de 6 bits para la operación (comp), 3 bits para los registros destino (dest), y 3 bits para el salto (jump).

* Formato binario: 111 a c1 c2 c3 c4 c5 c6 d1 d2 d3 j1 j2 j3

Ejemplos:

1. D = A + D:

* Suma el valor del registro A y el registro D, y almacena el resultado en D.

* Binario: 111 000 010 100 000 000
Explicación: comp = A + D, dest = D, jump = 000 (sin salto).

2. M = D - A:

* Realiza una resta entre el valor de D y A, y guarda el resultado en la posición de memoria a la que apunta el registro A.

* Binario: 111 000 011 010 000 000
Explicación: comp = D - A, dest = M, jump = 000 (sin salto).

3. D;JMP:

* Realiza un salto incondicional si el valor de D es diferente de cero, saltando a la dirección indicada por la instrucción.

* Binario: 111 000 000 000 000 001
Explicación: comp = D, dest = 000 (sin destino), jump = JMP (salto incondicional).
