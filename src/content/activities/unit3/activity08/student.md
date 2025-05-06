Direcciones de memoria:

* pStack es un objeto creado en el stack, y su dirección de memoria se asigna automáticamente.
![pstack](https://github.com/user-attachments/assets/eedac8d9-91da-4abd-9d10-6faa87dcb919)


* pHeap es un puntero que contiene la dirección de un objeto creado en el heap usando new.
* ![pheap](https://github.com/user-attachments/assets/dbe7e364-d513-4de1-85a6-d65b03c0e395)

pStack y pHeap:

* pStack: Es un objeto (no un puntero). Está almacenado en el stack y su memoria se gestiona automáticamente.

* pHeap: Es un puntero que almacena la dirección de un objeto creado dinámicamente en el heap. El objeto en sí reside en el heap, y la memoria debe ser liberada con delete.

En memory1

* Al inspeccionar la dirección de pHeap en Memory1, verás la dirección de la memoria del objeto en el heap.

* Al inspeccionar &pHeap, verás la dirección del puntero en el stack.

* pHeap
![pHeap 1](https://github.com/user-attachments/assets/8b71daa8-6f08-4152-aa7d-cf442209d075)

* &pHeap
![pHeap](https://github.com/user-attachments/assets/49cc0c40-d88f-4e61-8a5c-dbd5fe17370c)
