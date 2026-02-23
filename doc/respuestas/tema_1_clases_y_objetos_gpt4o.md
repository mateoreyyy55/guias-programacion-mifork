<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Clases y Objetos". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: ninguno.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->

# TEMA 1. Clases y objetos

## 1. ¿Cuáles son las cuatro características básicas de la programación orientada a objetos? Describe brevemente cada una

Las cuatro características básicas de la programación orientada a objetos son encapsulación, abstracción, herencia y polimorfismo. Estas permiten organizar el código de forma más clara, reutilizable y mantenible, modelando los programas como si fueran objetos del mundo real.

La encapsulación consiste en agrupar los datos (atributos) y los métodos que operan sobre esos datos dentro de una misma clase, y además restringir el acceso directo a ellos. De esta manera se protege la información interna del objeto y solo se permite interactuar con él mediante métodos definidos, lo que mejora la seguridad y el control del programa.

La abstracción permite mostrar únicamente la información esencial de un objeto y ocultar los detalles internos de implementación. Así, el usuario de la clase no necesita saber cómo está hecho algo por dentro, sino solo cómo utilizarlo. Esto facilita el uso y la comprensión del código.

La herencia permite crear nuevas clases a partir de otras ya existentes, reutilizando sus atributos y métodos. Esto evita repetir código y permite establecer relaciones entre clases. Por último, el polimorfismo permite que distintos objetos puedan responder de manera diferente ante el mismo método, lo que aporta flexibilidad y permite escribir código más general y reutilizable.


## 2. Cita cuatro lenguajes populares que permitan la programación orientada a objetos

Existen muchos lenguajes de programación que permiten trabajar con programación orientada a objetos. Entre los más populares se encuentran Java, C++, Python y C#. Todos ellos permiten definir clases, crear objetos y aplicar conceptos como herencia, encapsulación y polimorfismo.

Java es uno de los lenguajes más conocidos en el ámbito educativo y empresarial, ya que está completamente orientado a objetos y se utiliza ampliamente en aplicaciones web, móviles y de escritorio. C++, por su parte, combina programación estructurada con programación orientada a objetos y es muy utilizado en sistemas, videojuegos y aplicaciones de alto rendimiento.

Python también soporta programación orientada a objetos y es muy popular por su sintaxis sencilla y fácil de aprender, lo que lo hace ideal para principiantes. Finalmente, C# es un lenguaje desarrollado por Microsoft que se usa mucho en el desarrollo de aplicaciones de escritorio, web y videojuegos con Unity.


## 3. Los paradigmas anteriores a la POO, ¿Qué es la **programación estructurada**? y, todavía mejor, ¿Qué es la **programación modular**?

Antes de la programación orientada a objetos, uno de los paradigmas más utilizados era la programación estructurada. Este enfoque organiza el programa utilizando estructuras de control como secuencias, condicionales (if/else) y bucles (for, while), evitando el uso de saltos desordenados como el goto. El objetivo es que el código sea más claro, legible y fácil de mantener, siguiendo una estructura lógica bien definida.

Por otro lado, la programación modular es un enfoque que consiste en dividir un programa grande en partes más pequeñas llamadas módulos o funciones. Cada módulo se encarga de realizar una tarea específica y puede desarrollarse y probarse de manera independiente. Esto permite organizar mejor el código y facilita su reutilización.

Mientras que la programación estructurada se centra en la forma en que se organiza el flujo del programa, la programación modular pone el foco en dividir el problema en partes más pequeñas y manejables. Ambos enfoques buscan mejorar la claridad y el mantenimiento del software, y sirvieron como base para la evolución hacia la programación orientada a objetos.

## 4. ¿Qué tres elementos definen a un objeto en programación orientada a objetos?

En programación orientada a objetos, un objeto se define por tres elementos fundamentales: atributos, métodos y estado.

Atributos: Son las propiedades o características del objeto, que almacenan información sobre él. Por ejemplo, un objeto Coche puede tener atributos como color, marca y modelo.

Métodos: Son las funciones o acciones que el objeto puede realizar. Siguiendo el ejemplo del Coche, los métodos podrían ser arrancar(), acelerar() o frenar().

Estado: Es la información actual de los atributos del objeto en un momento dado. Por ejemplo, un coche puede tener el estado color = rojo, velocidad = 0 km/h. El estado cambia a medida que se usan los métodos del objeto.

## 5. ¿Qué es una clase? ¿Es lo mismo que un objeto? ¿Qué es una instancia? ¿Todos los lenguajes orientados a objetos manejan el concepto de clase?

¿Qué es una clase?
Una clase es como un molde o plantilla que define cómo serán los objetos de un cierto tipo. Contiene la definición de atributos (propiedades) y métodos (acciones) que tendrán los objetos creados a partir de ella. Por ejemplo, la clase Coche define que todos los coches tendrán color, marca y modelo, y podrán realizar acciones como arrancar() o frenar().

¿Es lo mismo que un objeto?
No, no es lo mismo. La clase es solo el modelo, mientras que el objeto es una entidad concreta creada a partir de ese modelo. Siguiendo el ejemplo, un coche rojo de marca Toyota es un objeto; la clase Coche solo describe cómo es un coche en general.

¿Qué es una instancia?
Una instancia es un objeto específico creado a partir de una clase. Es decir, cuando "instancias" una clase, estás creando un objeto real con atributos propios. Por ejemplo:

coche1 = Coche()
coche1.color = "rojo"
coche1.marca = "Toyota"

Aquí coche1 es una instancia de la clase Coche.

¿Todos los lenguajes orientados a objetos manejan el concepto de clase?
No necesariamente. La mayoría de los lenguajes orientados a objetos tradicionales como Java, C++ y C# usan clases, pero hay lenguajes como JavaScript o Python (que es mixto) que permiten crear objetos directamente sin necesidad de definir explícitamente una clase. En algunos lenguajes más modernos o dinámicos, los objetos pueden ser más flexibles y no siempre provienen de una clase formal.


## 6. ¿Dónde se almacenan en memoria los objetos? ¿Es igual en todos los lenguajes? ¿Qué es la **recolección de basura**? 

¿Dónde se almacenan los objetos en memoria?
Los objetos se almacenan principalmente en la memoria dinámica o heap. Esto significa que cuando creas un objeto, el sistema reserva un espacio en memoria para guardar sus atributos y datos internos, mientras que la variable que apunta al objeto suele estar en la pila (stack).

Por ejemplo, en:

coche1 = Coche()

La variable coche1 apunta a un objeto que está en el heap.

Los atributos de coche1 (color, marca, modelo) se almacenan dentro de ese objeto en el heap.

¿Es igual en todos los lenguajes?
No. Cada lenguaje maneja la memoria de forma diferente:

En Java y C#, todos los objetos se almacenan en el heap y la memoria se gestiona automáticamente.

En C++, el programador puede elegir entre crear objetos en el stack (automático) o en el heap (dinámico con new).

En Python, los objetos siempre van al heap y la gestión de memoria es automática.

¿Qué es la recolección de basura (garbage collection)?
La recolección de basura es un proceso automático que liberan algunos lenguajes de programación (como Java, Python o C#).

Detecta los objetos que ya no tienen referencias (nadie los está usando).

Libera la memoria que ocupaban, evitando que el programa consuma más memoria de la necesaria.

Por ejemplo:

coche1 = Coche()
coche1 = None  # Ahora el objeto original ya no tiene referencias

En este momento, el objeto Coche creado puede ser eliminado por el recolector de basura.


## 7. ¿Qué es un método? ¿Qué es la **sobrecarga de métodos**? 

¿Qué es un método?
Un método es una función que está definida dentro de una clase y que describe una acción que puede realizar un objeto. Los métodos operan sobre los datos del objeto (sus atributos) y permiten que el objeto haga cosas o cambie su estado.

Por ejemplo, en una clase Coche:

class Coche:
    def arrancar(self):
        print("El coche ha arrancado")
    
    def acelerar(self, velocidad):
        print(f"El coche va a {velocidad} km/h")

arrancar() y acelerar() son métodos del objeto Coche.

¿Qué es la sobrecarga de métodos?
La sobrecarga de métodos es la capacidad de una clase de tener varios métodos con el mismo nombre pero con diferentes parámetros. Esto permite que un mismo método pueda comportarse de formas distintas según los datos que reciba.

Ejemplo en pseudocódigo:

class Calculadora {
    int sumar(int a, int b) { return a + b; }
    double sumar(double a, double b) { return a + b; }
}

Aquí sumar está sobrecargado: puede sumar enteros o decimales según el tipo de dato que le pases.

Esto mejora la flexibilidad del código y la legibilidad.


## 8. Ejemplo mínimo de clase en Java, que se llame Punto, con dos atributos, x e y, con un método que se llame `calculaDistanciaAOrigen`, que calcule la distancia a la posición 0,0. Por sencillez, los atributos deben tener visibilidad por defecto. Crea además un ejemplo de uso con una instancia y uso del método

Clase Punto
public class Punto {
    // Atributos con visibilidad por defecto
    double x;
    double y;

    // Método que calcula la distancia al origen (0,0)
    double calculaDistanciaAOrigen() {
        return Math.sqrt(x * x + y * y);
    }
}
Ejemplo de uso
public class Main {
    public static void main(String[] args) {
        // Crear una instancia de Punto
        Punto p = new Punto();
        p.x = 3;  // Asignar valor a x
        p.y = 4;  // Asignar valor a y

        // Usar el método calculaDistanciaAOrigen
        double distancia = p.calculaDistanciaAOrigen();

        System.out.println("La distancia al origen es: " + distancia);
    }
}


## 9. ¿Cuál es el punto de entrada en un programa en Java? ¿Qué es `static` y para qué vale? ¿Sólo se emplea para ese método `main`? ¿Para qué se combina con `final`?

Punto de entrada en un programa Java

En Java, el punto de entrada siempre es el método main.

public static void main(String[] args) {
    // Código que se ejecuta al iniciar el programa
}

Cuando ejecutas un programa, la JVM busca este método para empezar a correr el código.

Sin main, Java no sabe por dónde empezar.

¿Qué es static y para qué sirve?

La palabra clave static significa que el miembro (método o atributo) pertenece a la clase, no a un objeto específico.

Esto permite usarlo sin crear una instancia de la clase.

Ejemplo:

class Utilidades {
    static int sumar(int a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        int resultado = Utilidades.sumar(3, 4);  // No se necesita crear objeto
        System.out.println(resultado);
    }
}

sumar es static, así que podemos llamarlo directamente usando la clase Utilidades, sin crear un objeto.

 ¿Sólo se emplea static para main?

No. static se puede usar en:

Métodos: para que puedan usarse sin crear un objeto.

Atributos: para que todos los objetos compartan el mismo valor (por ejemplo, un contador de instancias).

Bloques y clases internas también pueden ser static en ciertos casos.

El main debe ser static porque Java aún no ha creado objetos al iniciar el programa.

¿Para qué se combina static con final?

final significa que el valor no puede cambiar.

Cuando combinamos static final, obtenemos constantes de clase.

Ejemplo:

class Configuracion {
    static final double PI = 3.14159;
}

PI pertenece a la clase, no a un objeto.

Su valor nunca puede cambiar.

Se suele usar para valores fijos que todos los objetos deben conocer.

## 10. Intenta ejecutar un poco de Java de forma básica, con los comandos `javac` y `java`. ¿Cómo podemos compilar el programa y ejecutarlo desde linea de comandos? ¿Java es compilado? ¿Qué es la **máquina virtual**? ¿Qué es el *byte-code* y los ficheros `.class`?

Cómo compilar y ejecutar un programa Java desde la línea de comandos

Supongamos que tienes un archivo HolaMundo.java así:

public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, mundo!");
    }
}
 Paso 1: Abrir terminal / CMD

Ve a la carpeta donde está HolaMundo.java.

cd C:\Users\Mateo\Documents\java
 Paso 2: Compilar con javac
javac HolaMundo.java

Esto no ejecuta el programa.

Crea un archivo HolaMundo.class que contiene el byte-code.

 Si hay errores, te los mostrará y no se generará el .class.

 Paso 3: Ejecutar con java
java HolaMundo

Aquí Java ejecuta la máquina virtual (JVM) que interpreta el byte-code.

Salida esperada:

¡Hola, mundo!

¿Java es compilado?

Sí… pero con matices:

Java se compila a byte-code, no a código máquina directamente.

Luego, la JVM interpreta ese byte-code en cada sistema operativo.

Por eso Java es “compilado e interpretado”: compilas a byte-code y la máquina virtual lo ejecuta.

¿Qué es la máquina virtual (JVM)?

La JVM (Java Virtual Machine) es un programa que:

Lee el byte-code del archivo .class

Lo interpreta y ejecuta en la computadora

Permite que Java sea multiplataforma, porque el mismo .class funciona en Windows, Mac o Linux.

¿Qué es el byte-code y los ficheros .class?

Byte-code: código intermedio generado por el compilador javac.

No es código máquina, pero sí instrucciones que la JVM entiende.

Archivo .class: contiene el byte-code listo para ejecutar.


## 11. En el código anterior de la clase `Punto` ¿Qué es `new`? ¿Qué es un **constructor**? Pon un ejemplo de constructor en una clase `Empleado` que tenga DNI, nombre y apellidos

¿Qué es new?

En Java, new crea un objeto en memoria (en el heap).

Asigna espacio para los atributos y devuelve una referencia que guardamos en la variable.

Ejemplo con tu clase Punto:

Punto p = new Punto();  // 'new' crea un objeto Punto

p apunta al objeto que new acaba de crear.

¿Qué es un constructor?

Es un método especial de la clase que se llama automáticamente al crear un objeto con new.

Sirve para inicializar los atributos del objeto.

Tiene el mismo nombre que la clase y no tiene tipo de retorno.

Ejemplo de constructor en clase Empleado
public class Empleado {
    // Atributos
    String dni;
    String nombre;
    String apellidos;

    // Constructor
    public Empleado(String dni, String nombre, String apellidos) {
        this.dni = dni;           // inicializa los atributos
        this.nombre = nombre;
        this.apellidos = apellidos;
    }

    // Método para mostrar datos
    void mostrarDatos() {
        System.out.println("DNI: " + dni);
        System.out.println("Nombre: " + nombre + " " + apellidos);
    }
}

Ejemplo de uso
public class Main {
    public static void main(String[] args) {
        // Crear un objeto Empleado usando el constructor
        Empleado e1 = new Empleado("12345678A", "Juan", "Pérez");

        // Llamar al método
        e1.mostrarDatos();
    }
}

Salida esperada:

DNI: 12345678A
Nombre: Juan Pérez


## 12. ¿Qué es la referencia `this`? ¿Se llama igual en todos los lenguajes? Pon un ejemplo del uso de `this` en la clase `Punto`

¿Qué es la referencia this?

this es una referencia al propio objeto que está usando un método o constructor.

Permite diferenciar entre atributos de la clase y variables locales con el mismo nombre.

Solo tiene sentido dentro de la clase, no fuera.

¿Se llama igual en todos los lenguajes?

No, depende del lenguaje:

Lenguaje	Referencia al objeto actual
Java	this
C++	this (puntero al objeto)
Python	self
JavaScript	this (contexto de ejecución)

Así que en Java siempre es this, pero en otros lenguajes puede cambiar.

Ejemplo de uso en la clase Punto
public class Punto {
    double x;
    double y;

    // Constructor usando 'this' para diferenciar atributos de parámetros
    public Punto(double x, double y) {
        this.x = x;  // 'this.x' se refiere al atributo del objeto
        this.y = y;  // 'this.y' se refiere al atributo del objeto
    }

    double calculaDistanciaAOrigen() {
        return Math.sqrt(this.x * this.x + this.y * this.y);
    }
}

Ejemplo de uso del objeto
public class Main {
    public static void main(String[] args) {
        Punto p1 = new Punto(3, 4);
        System.out.println("Distancia al origen: " + p1.calculaDistanciaAOrigen());
    }
}

Salida esperada:

Distancia al origen: 5.0


## 13. Añade ahora otro nuevo método que se llame `distanciaA`, que reciba un `Punto` como parámetro y calcule la distancia entre `this` y el punto proporcionado

Clase Punto con nuevo método distanciaA
public class Punto {
    double x;
    double y;

    // Constructor
    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
    }

    // Método que calcula la distancia al origen
    double calculaDistanciaAOrigen() {
        return Math.sqrt(this.x * this.x + this.y * this.y);
    }

    // Nuevo método: distancia a otro punto
    double distanciaA(Punto otro) {
        double dx = this.x - otro.x;
        double dy = this.y - otro.y;
        return Math.sqrt(dx * dx + dy * dy);
    }
}
Ejemplo de uso
public class Main {
    public static void main(String[] args) {
        Punto p1 = new Punto(3, 4);
        Punto p2 = new Punto(6, 8);

        double distanciaOrigen = p1.calculaDistanciaAOrigen();
        System.out.println("Distancia de p1 al origen: " + distanciaOrigen);

        double distanciaEntrePuntos = p1.distanciaA(p2);
        System.out.println("Distancia entre p1 y p2: " + distanciaEntrePuntos);
    }
}

Salida esperada:

Distancia de p1 al origen: 5.0
Distancia entre p1 y p2: 5.0


## 14. El paso del `Punto` como parámetro a un método, es **por copia** o **por referencia**, es decir, si se cambia el valor de algún atributo del punto pasado como parámetro, dichos cambios afectan al objeto fuera del método? ¿Qué ocurre si en vez de un `Punto`, se recibiese un entero (`int`) y dicho entero se modificase dentro de la función? 

Paso de objetos (Punto) a un método

En Java:

Siempre se pasa “por valor”… pero cuidado:

Para tipos primitivos (int, double, boolean…), se pasa el valor real.

Para objetos (como Punto), se pasa una copia de la referencia al objeto.

 Esto significa:

Si modificas los atributos del objeto dentro del método, los cambios afectan al objeto original.

Ejemplo de reasignación de referencia:
void cambiarReferencia(Punto p) {
    p = new Punto(0, 0);  // Esto apunta a otro objeto, NO cambia el original
}

public static void main(String[] args) {
    Punto p1 = new Punto(3, 4);
    cambiarReferencia(p1);
    System.out.println(p1.x + ", " + p1.y); // Imprime: 3, 4
}

Aquí la referencia p apunta a un nuevo objeto dentro del método, pero p1 sigue apuntando al original.

Paso de primitivos (int)

Los tipos primitivos se pasan por valor, es decir, solo se copia el valor.

Cambiarlo dentro del método NO afecta al original.

void incrementar(int n) {
    n = n + 1;
}

public static void main(String[] args) {
    int a = 5;
    incrementar(a);
    System.out.println(a); // Imprime: 5
}

 Resultado: a no cambia


## 15. ¿Qué es el método `toString()` en Java? ¿Existe en otros lenguajes? Pon un ejemplo de `toString()` en la clase `Punto` en Java

¿Qué es toString() en Java?

toString() es un método heredado de la clase Object (la superclase de todas las clases en Java).

Su función principal es devolver una representación en texto del objeto.

Se llama automáticamente cuando, por ejemplo, haces:

System.out.println(p1);

Si no lo sobreescribes, Java devuelve algo como:

Punto@15db9742

Que es poco legible (clase + hashcode).

¿Existe en otros lenguajes?

Sí, con nombres distintos:

Lenguaje	Método equivalente
C++	operator<< o función propia
Python	__str__() o __repr__()
C#	ToString()

La idea es la misma: convertir un objeto en texto legible.

Ejemplo en la clase Punto en Java
public class Punto {
    double x;
    double y;

    // Constructor
    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
    }

    // Método toString sobreescrito
    @Override
    public String toString() {
        return "Punto(" + x + ", " + y + ")";
    }
}

Ejemplo de uso
public class Main {
    public static void main(String[] args) {
        Punto p1 = new Punto(3, 4);
        System.out.println(p1);  // Llama automáticamente a p1.toString()
    }
}

Salida esperada:

Punto(3.0, 4.0)


## 16. Reflexiona: ¿una clase es como un `struct` en C? ¿Qué le falta al `struct` para ser como una clase y las variables de ese tipo ser instancias?

¿Una clase es como un struct en C?

En C, un struct es un grupo de variables bajo un mismo nombre, que permite agrupar datos relacionados.

En Java (y otros lenguajes orientados a objetos), una clase también agrupa datos (atributos), pero va mucho más allá:

Concepto	struct en C	Clase en Java/C++
Datos	Sí, solo variables	Sí, atributos y más
Métodos	 No puede tener	Sí, funciones/métodos
Encapsulación	 No hay control de acceso	Sí, public/private/protected
Herencia	 No	Sí, puedes heredar de otra clase
Polimorfismo	 No	Sí, los métodos pueden ser sobrecargados o sobrescritos
Instancias	Solo variables normales	Sí, cada objeto es una instancia de la clase

¿Qué le falta al struct para ser como una clase?

Métodos → en C un struct solo almacena datos, no puede tener funciones que operen sobre sí mismo.

Encapsulación → no hay control de acceso a los datos, todos los campos son públicos.

Constructores / inicialización → no hay un mecanismo integrado para inicializar un struct al crearlo.

Instancias “inteligentes” → en C, cada struct es solo un bloque de memoria; en Java, cada objeto es una instancia con identidad propia en el heap.

Herencia y polimorfismo → un struct no puede extender otro struct ni redefinir comportamiento

Conclusión

Un struct es como un “bloque de datos”.

Una clase es un molde completo que combina datos + comportamiento + reglas de acceso + identidad de instancias.

Para que un struct fuese como una clase, necesitaría:

Métodos

Constructores

Control de acceso a sus campos

Capacidad de instanciar objetos con identidad

Herencia/polimorfismo



## 17. Quitemos un poco de magia a todo esto: ¿Como se podría “emular”, con `struct` en C, la clase `Punto`, con su función para calcular la distancia al origen? ¿Qué ha pasado con `this`?

Emular la clase Punto con un struct

En C, un struct solo puede contener datos, así que para simular métodos usamos funciones externas que reciben un puntero al struct como parámetro, para “apuntarle” al objeto.

#include <stdio.h>
#include <math.h>

// Definición del struct
typedef struct {
    double x;
    double y;
} Punto;

// Función que calcula la distancia al origen
double calculaDistanciaAOrigen(Punto* p) {
    return sqrt(p->x * p->x + p->y * p->y);
}

int main() {
    // Crear una "instancia" de Punto
    Punto p1;
    p1.x = 3;
    p1.y = 4;

    // Llamar a la "función método"
    double distancia = calculaDistanciaAOrigen(&p1);

    printf("Distancia al origen: %.2f\n", distancia);
    return 0;
}

Salida esperada:

Distancia al origen: 5.00

Qué ha pasado con this

En Java, this apunta al objeto actual que llama al método.

En C, como las funciones no son parte del struct, no existe this.

Para simularlo, pasamos un puntero al struct (Punto* p) como primer argumento de la función.

Dentro de la función usamos p->x en lugar de this.x.

Comparación conceptual
Concepto Java	Cómo se emula en C
Clase	struct
Atributos	Campos del struct
Método	Función que recibe un puntero al struct
this	Puntero al struct (p)
Instancia	Variable del struct
