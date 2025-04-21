¿Qué ocurre al copiar un objeto en C++ y en C#?

* En C++, se crea una copia independiente del objeto, por lo que los cambios en la copia no afectan al original.

* En C#, se copia la referencia al objeto, lo que significa que tanto la copia como el objeto original comparten la misma ubicación en memoria, y los cambios en uno afectan al otro.

¿Qué es copia en C++ y en C#? ¿Es una copia independiente de original?

* En C++, la copia es independiente porque se crea una nueva instancia del objeto.

* En C#, la copia no es independiente, ya que ambas variables apuntan al mismo objeto en memoria.
