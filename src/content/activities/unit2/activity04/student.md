´´´cpp

int a = 10;      // a tiene el valor 10
int* p;          // p es un puntero
p = &a;          // p guarda la dirección de a
*p = 20;         // cambia el valor de a (usando p) a 20

´´´

en Hack Assembler, no hay tipos ni punteros como tal, pero podemos simular un puntero al guardar la dirección de una variable en otra ubicación de memoria. Así:

* a estará en una dirección, por ejemplo RAM[16]
* p estará en otra dirección, digamos RAM[17], y guardará el valor 16 (la dirección de a)
  
Luego, cuando hacemos *p = 20;, primero leemos el valor de p (que es 16), y vamos a esa dirección para escribir el 20.

´´´asm
// int a = 10;
@10
D=A
@a      // a se almacena en RAM[16]
M=D     // M[a] = 10

// int* p;
// p = &a;
@a
D=A     // D tiene la dirección de a (que es 16)
@p      // p se almacena en RAM[17]
M=D     // M[p] = 16

// *p = 20;
@p
A=M     // A = contenido de p => A = 16
@20
D=A
M=D     // M[16] = 20 (a = 20)

// Bucle infinito (opcional para detener el programa)
(END)
@END
0;JMP
´´´
