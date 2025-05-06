
 Condicionales
 
``` c++
int x = 5;
if (x > 0) {
    x = x * 2;
}
```
```
@x
M=5      // x = 5
@x
D=M      // D = x
@END
D;JLE    // Salta si x <= 0
@x
M=M*2    // x = x * 2
(END)
```
Ciclo while
``` c++
int count = 3;
while (count > 0) {
    count--;
}
```
```
@count
M=3      // count = 3
(LOOP)
@count
D=M      // D = count
@END
D;JLE    // Salta si count <= 0
@count
M=M-1    // count--
@LOOP
0;JMP    // Repetir
(END)
```
Ciclo for
```c++
for (int i=0; i<5; i++) {
    // Cuerpo vacío
}
```
```
@i
M=0      // i=0
(LOOP)
@i
D=M
@5
D=D-A
@END
D;JGE    // Salta si i >=5
@i
M=M+1    // i++
@LOOP
0;JMP
(END)
```
Escritura con punteros
``` c++
int num = 10;
int* ptr = &num;
*ptr = 20;
```
```
@num
M=10     // num=10
@ptr
M=@num   // ptr = dirección de num
@20
D=A
@ptr
A=M      // Accede a la dirección almacenada en ptr
M=D      // *ptr = 20
```
 Lectura con punteros
```c++
int value = *ptr;
```
```
@ptr
A=M      // Apunta a la dirección almacenada en ptr
D=M      // Lee el valor
@value
M=D      // value = *ptr
```
Arreglos con punteros
```c++
int arr[3] = {7, 8, 9};
int* ptr = arr;
ptr[1] = 10;  // Modifica el segundo elemento
```
```
// Inicialización del arreglo
@arr
M=7
M+1=8
M+1=9

@arr
D=A
@ptr
M=D      // ptr = dirección base del arreglo

@ptr
A=M+1    // Accede a arr[1]
M=10     // arr[1] = 10
```
Función con parámetros
```c++
void sumar(int a, int b) {
    a + b;
}
sumar(3, 4);
```
```
// Llamada: sumar(3,4)
@3
D=A
@R13     // Registro temporal para a
M=D
@4
D=A
@R14     // Registro temporal para b
M=D

// Cuerpo de la función
@R13
D=M
@R14
D=D+M    // D = a + b
// (El resultado se ignora en este ejemplo)
```
Función con retorno
```c++
int duplicar(int n) {
    return n * 2;
}
int resultado = duplicar(5);
```
```
// Llamada: duplicar(5)
@5
D=A
@R15     // Registro para parámetro n
M=D

// Cuerpo de la función
@R15
D=M
M=D+M    // n = n * 2

// Retorno
@R15
D=M
@resultado
M=D      // resultado = n
```
