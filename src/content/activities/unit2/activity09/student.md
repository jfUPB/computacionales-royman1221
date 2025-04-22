En esta arquitectura, las instrucciones se representan con 16 bits. Hay dos tipos de instrucciones:
   
•	Instrucciones A (direcciones de memoria): Comienzan con 0, seguidas de 15 bits que especifican la dirección.

•	Instrucciones C (operaciones): Comienzan con 111, seguidas por los campos de destino (dest), operación (comp), y salto (jump).

Obteniendo el Tamaño del Arreglo SCREEN

Sabemos que la pantalla tiene una resolución de 512x256 píxeles, y que cada posición del arreglo SCREEN representa 16 píxeles.

•	Número total de píxeles en la pantalla:
512×256=131,072  

•	Tamaño del arreglo SCREEN (el número de posiciones del arreglo):
131,072 / 16 =   8,192

Así que el arreglo SCREEN tiene 8,192 posiciones.

```
using System;
class HelloWorld {
  static void Main() {
    int Screen = new int [8192];
    Act_pos = 0;
    int KBD = 0;
    while(true){
      if(KBD !=0){
        Screen[Act_pos] = 1;
        if(Act_pos <= 8192)
        Act_pos++;

        }
        else if (KBD ==0 ){
        Screen[Act_pos] = -1;
        if(Act_pos >= 0)
        Act_pos=Act_pos - 1;
        }
    }

  }
}
```
