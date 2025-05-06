``` c++
#include <iostream>
using namespace std;

class CuentaBancaria {
private:
    string titular;
    double saldo;
    static int totalCuentas;  // Variable estática (compartida entre todas las instancias)

public:
    // Constructor
    CuentaBancaria(string nombre, double montoInicial) : titular(nombre), saldo(montoInicial) {
        totalCuentas++;
        cout << "Cuenta creada para " << titular << ". Total de cuentas: " << totalCuentas << endl;
    }

    // Destructor
    ~CuentaBancaria() {
        cout << "Cuenta de " << titular << " eliminada." << endl;
        totalCuentas--;
    }

    // Método para depositar (paso por valor)
    void depositar(double cantidad) {
        saldo += cantidad;
    }

    // Método para transferir (paso por referencia)
    void transferir(CuentaBancaria& destino, double cantidad) {
        if (saldo >= cantidad) {
            saldo -= cantidad;
            destino.saldo += cantidad;
        }
    }

    void imprimir() const {
        cout << "Titular: " << titular << ", Saldo: $" << saldo << endl;
    }

    // Método estático
    static int obtenerTotalCuentas() {
        return totalCuentas;
    }
};

int CuentaBancaria::totalCuentas = 0;

void crearCuentaEnBloque() {
    CuentaBancaria cuentaTemporal("Temporal", 100);
    cuentaTemporal.imprimir();
    // La cuenta será destruida automáticamente al salir de este bloque (stack)
}

int main() {
    // Objeto creado en el stack
    CuentaBancaria cuenta1("Alice", 500);

    // Objeto creado dinámicamente en el heap
    CuentaBancaria* cuenta2 = new CuentaBancaria("Bob", 1000);

    cuenta1.depositar(200);
    cuenta2->depositar(150);

    cuenta1.transferir(*cuenta2, 300);

    cuenta1.imprimir();
    cuenta2->imprimir();

    cout << "Total de cuentas activas: " << CuentaBancaria::obtenerTotalCuentas() << endl;

    crearCuentaEnBloque(); // Objeto temporal que se destruye al salir del bloque

    delete cuenta2; // Liberar el objeto creado en el heap

    cout << "Total de cuentas después de delete: " << CuentaBancaria::obtenerTotalCuentas() << endl;

    return 0;
}
#include <iostream>
using namespace std;

class CuentaBancaria {
private:
    string titular;
    double saldo;
    static int totalCuentas;  // Variable estática (compartida entre todas las instancias)

public:
    // Constructor
    CuentaBancaria(string nombre, double montoInicial) : titular(nombre), saldo(montoInicial) {
        totalCuentas++;
        cout << "Cuenta creada para " << titular << ". Total de cuentas: " << totalCuentas << endl;
    }

    // Destructor
    ~CuentaBancaria() {
        cout << "Cuenta de " << titular << " eliminada." << endl;
        totalCuentas--;
    }

    // Método para depositar (paso por valor)
    void depositar(double cantidad) {
        saldo += cantidad;
    }

    // Método para transferir (paso por referencia)
    void transferir(CuentaBancaria& destino, double cantidad) {
        if (saldo >= cantidad) {
            saldo -= cantidad;
            destino.saldo += cantidad;
        }
    }

    void imprimir() const {
        cout << "Titular: " << titular << ", Saldo: $" << saldo << endl;
    }

    // Método estático
    static int obtenerTotalCuentas() {
        return totalCuentas;
    }
};

int CuentaBancaria::totalCuentas = 0;

void crearCuentaEnBloque() {
    CuentaBancaria cuentaTemporal("Temporal", 100);
    cuentaTemporal.imprimir();
    // La cuenta será destruida automáticamente al salir de este bloque (stack)
}

int main() {
    // Objeto creado en el stack
    CuentaBancaria cuenta1("Alice", 500);

    // Objeto creado dinámicamente en el heap
    CuentaBancaria* cuenta2 = new CuentaBancaria("Bob", 1000);

    cuenta1.depositar(200);
    cuenta2->depositar(150);

    cuenta1.transferir(*cuenta2, 300);

    cuenta1.imprimir();
    cuenta2->imprimir();

    cout << "Total de cuentas activas: " << CuentaBancaria::obtenerTotalCuentas() << endl;

    crearCuentaEnBloque(); // Objeto temporal que se destruye al salir del bloque

    delete cuenta2; // Liberar el objeto creado en el heap

    cout << "Total de cuentas después de delete: " << CuentaBancaria::obtenerTotalCuentas() << endl;

    return 0;
}

``` 


Aplicación en el programa

* Clases y objetos = Se define la clase CuentaBancaria y se crean varios objetos de esta clase.
* Paso por valor = El método depositar recibe cantidad por valor.
* Paso por referencia = El método transferir recibe una referencia a otra cuenta.
* Constructores y destructores = Se usa el constructor para inicializar los objetos y el destructor para mostrar cuando se destruyen.
* Métodos y atributos = Métodos como depositar, transferir, imprimir acceden a los atributos titular y saldo.
* Stack y Heap = cuenta1 está en el stack, cuenta2 está en el heap (creado con new).
* Punteros y referencias = cuenta2 es un puntero, y en transferir se usa una referencia.
* Variables estáticas = totalCuentas se comparte entre todas las instancias.
* Depuración = Se pueden colocar breakpoints para observar el ciclo de vida de los objetos, el uso de memoria y valores.

Análisis Detallado de la Memoria

* cuenta1	Stack	Objeto local del main, su memoria se libera automáticamente.
* cuenta2	Stack	El puntero como tal está en el stack.
* *cuenta2	Heap	El objeto real (la cuenta de Bob) está en el heap, se destruye con delete.
* cuentaTemporal	Stack	Se destruye automáticamente al salir del bloque crearCuentaEnBloque().
* totalCuentas	Segmento de Datos (estático/global)	Se mantiene durante toda la ejecución del programa.
* Variables de función	Stack	Parámetros como cantidad, destino viven en el stack.


