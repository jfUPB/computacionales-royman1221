* ¿Qué ocurre después de llamar a la función cambiarNombre? ¿Por qué aparece el mensaje Destructor: Punto cambiado(70, 80) destruido.?
Cuando llamamos a la función cambiarNombre pasando el objeto original por valor:
```c++
void cambiarNombre(Punto p, string nuevoNombre) {
    p.name = nuevoNombre;
}
```
Aquí se realiza una copia del objeto original en el parámetro p de la función. Lo que ocurre es que dentro de la función, se modifica el nombre del objeto p, pero esa modificación solo afecta a la copia local. Cuando la función termina, la copia se destruye y se llama al destructor de esa copia, lo que genera el mensaje de destrucción.

* ¿Por qué aparece el mensaje del destructor?

Porque el objeto p es creado en la pila de la función (es una copia del objeto original), y cuando la función termina, el objeto p es destruido automáticamente, lo que invoca su destructor.

* ¿Por qué original sigue existiendo luego de llamar cambiarNombre?

El objeto original sigue existiendo porque fue pasado por valor, lo que significa que no se modificó directamente. Solo se modificó la copia dentro de la función cambiarNombre, pero el objeto original en la función main no se ve afectado. En C++, cuando pasas un objeto por valor, se crea una copia local del objeto, y cualquier cambio realizado sobre la copia no afecta al objeto original.

* ¿En qué parte del mapa de memoria se encuentra original y en qué parte se encuentra p?
  ¿Son el mismo objeto?
  
original: Se encuentra en la pila (stack) en la función main.

p: Se encuentra en la pila también, pero es una copia local dentro de la función cambiarNombre.

¿Son el mismo objeto? No, no son el mismo objeto. original es el objeto original en main, y p es una copia de ese objeto creada dentro de la función cambiarNombre.


* Modificar la función cambiarNombre a pasar por referencia:

```c++
void cambiarNombre(Punto& p, string nuevoNombre) {
    p.name = nuevoNombre;
}
```
¿Qué ocurre ahora? ¿Por qué?
Al pasar el objeto por referencia (Punto& p), ya no se crea una copia local del objeto. En su lugar, se pasa una referencia al objeto original. Por lo tanto, cualquier cambio realizado dentro de la función afectará directamente al objeto original. En este caso, cuando se llama a cambiarNombre, el nombre de original se modifica y no se destruye ninguna copia.


* Modificar cambiarNombre y main para pasar un puntero:

```c++
void cambiarNombre(Punto* p, string nuevoNombre) {
    p->name = nuevoNombre;
}

int main() {
    // Objeto original
    Punto original("original",70, 80);
    original.imprimir();

    cambiarNombre(&original, "cambiado");
    original.imprimir();
    return 0;
}

```

¿Qué ocurre ahora? ¿Por qué?

Cuando pasamos el objeto original como un puntero (&original), estamos pasando la dirección de memoria del objeto original. Dentro de la función cambiarNombre, usamos el puntero p para acceder al objeto original y modificar su nombre a través del operador ->. Esto significa que se modifica directamente el objeto original, sin crear copias. La diferencia clave aquí es que, al usar un puntero, se accede y se modifica directamente el objeto en la memoria, lo cual es lo mismo que hacerlo por referencia, pero con punteros se trabaja explícitamente con direcciones de memoria.

* Diferencia entre pasar un objeto por valor, por referencia y por puntero:
  
  * Por valor: Se pasa una copia del objeto. Los cambios en la función no afectan al objeto original, y cuando la función termina, la copia local se destruye.

  * Por referencia: Se pasa una referencia al objeto original, lo que significa que cualquier cambio en la función afectará directamente al objeto original.

  * Por puntero: Se pasa la dirección de memoria del objeto original. Se accede al objeto mediante el puntero y cualquier cambio realizado en la función afecta al objeto original. La principal diferencia con la referencia es que se trabaja explícitamente con la dirección de memoria.

































