* int *pvar = var;
Declara una variable pvar que es un puntero a un entero.
Esto significa que pvar no almacena un valor entero directamente, sino la dirección en memoria donde se guarda un valor entero.

* *pvar = var;
Guarda el valor de var en la dirección de memoria a la que apunta pvar.
O sea, accede al contenido de la dirección que apunta pvar y le asigna el valor de var.
Es una escritura indirecta, usando el puntero.

* var2 = *pvar;
Asigna a var2 el valor que está almacenado en la dirección de memoria a la que apunta pvar.
Es decir, lee el contenido de esa dirección y lo guarda en var2.
Esto es una lectura indirecta.

* pvar = &var3;
Asigna a pvar la dirección de memoria de la variable var3.
Ahora pvar apunta a var3, o sea, si luego haces *pvar, estarías accediendo al valor de var3.
