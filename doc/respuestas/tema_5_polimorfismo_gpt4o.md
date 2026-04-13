<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Polimorfismo". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: Clases y Objetos, Encapsulación, Excepciones, Composición y Herencia.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->
# Tema 5. Polimorfismo

## 1. Brevemente, ¿qué es el **"polimorfismo"** y para qué sirve en programación orientada a objetos? ¿qué es la **"sobreescritura"** de métodos?

Polimorfismo significa “muchas formas”. En programación orientada a objetos permite que una misma referencia a una clase base pueda utilizarse para invocar comportamientos diferentes dependiendo del objeto real al que apunte.

¿Para qué sirve?

Facilita la reutilización de código.
Permite diseñar sistemas más flexibles y extensibles.
Hace posible tratar objetos diferentes de forma uniforme.

Sobreescritura (Overriding):
Consiste en redefinir en una subclase un método ya existente en la clase base, proporcionando una implementación específica.

class Animal {
    void hacerSonido() {
        System.out.println("Sonido genérico");
    }
}

class Perro extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("Guau");
    }
}


## 2. ¿En qué consiste la **"ligadura dinámica"** o **"enlace tardío"**? ¿qué relación tiene con el polimorfismo? ¿hay que indicarlos explícitamente al programar o depende esto del lenguaje? Compara C++ y Java. Indicalo después también para Python.

La ligadura dinámica o enlace tardío es el mecanismo mediante el cual la llamada a un método se resuelve en tiempo de ejecución, dependiendo del tipo real del objeto.

Relación con el polimorfismo:
Es el mecanismo que permite que el polimorfismo funcione.

¿Hay que indicarlo explícitamente?

Lenguaje	Comportamiento
Java	Todos los métodos no static, final o private son virtuales por defecto.
C++	Es necesario usar la palabra clave virtual para habilitar el enlace dinámico.
Python	Todo es dinámico por naturaleza; no se requiere ninguna indicación especial.


## 3. Pon un ejemplo sencillo en Java, de un `Soldado`, con un método `saluda`, con dos subclases: `Zapador` y `Artillero`, donde `Zapador` sobreescribe el método `saludar`, sustituyendo por completo su comportamiento. Ilustra el funcionamiento del polimorfismo creando un array de `Soldados` de dos tipos y luego recorriéndolo empleando referencias de tipo `Soldado` y llamando a `saludar`.

class Soldado {
    public void saludar() {
        System.out.println("¡Saludos, soy un soldado!");
    }
}

class Zapador extends Soldado {
    @Override
    public void saludar() {
        System.out.println("¡Zapador a sus órdenes!");
    }
}

class Artillero extends Soldado {
    // Hereda el comportamiento del soldado
}

public class Main {
    public static void main(String[] args) {
        Soldado[] ejercito = {
            new Soldado(),
            new Zapador(),
            new Artillero()
        };

        for (Soldado s : ejercito) {
            s.saludar(); // Polimorfismo
        }
    }
}


## 4. Si sobreescribo un método, ¿puedo invocar el método base para trabajar a partir de su resultado? Haz que zapador cambie ligeramente la forma de saludar, que salude de forma normal, tal cual hace el soldado base, pero que además añada un "ZAPADOR A SUS ORDENES" ¿qué palabra clave del lenguaje has usado para invocar al método de la clase base?

Sí, es posible invocar el método original de la clase base utilizando la palabra clave super.

class Zapador extends Soldado {
    @Override
    public void saludar() {
        super.saludar();
        System.out.println("ZAPADOR A SUS ORDENES");
    }
}


## 5. Al sobreescribir un método en Java, ¿qué restricciones existen sobre los tipos de los parámetros y el tipo de retorno? ¿Qué diferencia hay entre sobreescritura (*overriding*) y sobrecarga (*overloading*)? ¿Para qué sirve la anotación `@Override` y por qué es recomendable usarla siempre?

Restricciones en Overriding
Mismo nombre del método.
Mismos parámetros.
Tipo de retorno igual o covariante.
No reducir la visibilidad (por ejemplo, de public a private).
Puede lanzar menos o las mismas excepciones comprobadas.

Overriding vs Overloading
Característica	Overriding	Overloading
Herencia	Sí	No necesariamente
Parámetros	Iguales	Diferentes
Resolución	En tiempo de ejecución	En tiempo de compilación
Polimorfismo	Sí	No


## 6. Entonces, cuando se estudia Java, ¿se emplea el polimorfismo desde el principio? Por ejemplo, sobreescribiendo `toString` o sobreescribiendo `equals`, ¿ya estoy usando polimorfismo?

Sí. Al sobrescribir métodos como toString(), equals() o hashCode() de la clase Object, ya estás utilizando polimorfismo, ya que estos métodos se ejecutan según el tipo real del objeto.


## 7. ¿Qué es una **"clase abstracta"**? ¿Qué es un **"método abstracto"**? ¿Puedo crear instancias de una clase abstracta? Pongamos un ejemplo en Java: Redefinamos `Soldado`, hagamos que, además del método `saluda` que ya tenía, tenga un método `atacar`, que sea abstracto y que cada tipo de soldado haga su acción cuando se le pida atacar. ¿Donde debemos poner `abstract`?

Clase abstracta: No puede ser instanciada y puede contener métodos abstractos y concretos.
Método abstracto: Se declara sin implementación y debe ser implementado por las subclases.
abstract class Soldado {
    public void saludar() {
        System.out.println("¡Saludos, soy un soldado!");
    }

    public abstract void atacar(); // Método abstracto
}

class Zapador extends Soldado {
    @Override
    public void atacar() {
        System.out.println("El zapador coloca explosivos.");
    }
}

class Artillero extends Soldado {
    @Override
    public void atacar() {
        System.out.println("El artillero dispara el cañón.");
    }
}

¿Dónde colocar abstract?

En la declaración de la clase: abstract class Soldado
En el método: public abstract void atacar();


## 8. ¿Qué efecto tiene la palabra clave `final` sobre métodos y clases en Java? ¿Cómo se relaciona con el polimorfismo? ¿Conoces algún ejemplo de clase `final` en la propia API estándar de Java?

En métodos: Impide que sean sobreescritos.
En clases: Impide que sean heredadas.

Relación con el polimorfismo: Limita el uso del polimorfismo al evitar la redefinición de comportamientos.

Ejemplo de clase final en Java:

String

Otras: Math, Integer, Double.


## 9. En Java, qué son las **"interfaces"**? ¿Son como clases abstractas? ¿Una clase puede implementar más de una interfaz?

Las interfaces definen un contrato que las clases deben cumplir.

¿Son como clases abstractas?

Similares, pero las interfaces no tienen estado (salvo constantes).
Permiten herencia múltiple.

¿Puede una clase implementar varias interfaces?

Sí.
interface Volador {
    void volar();
}

interface Nadador {
    void nadar();
}

class Pato implements Volador, Nadador {
    public void volar() { }
    public void nadar() { }
}


## 10. Vamos a poner un ejemplo nuevo con polimorfismo. Queremos implementar una clase `Punto`, con un método `calcularDistanciaA`, que permite calcular la distancia a otro `Punto`. Sin embargo, como queremos trabajar con puntos 2D y 3D, haz que ese método sea abstracto y haya dos implementaciones de ese cálculo de distancia. Emplea `instanceof` y *downcasting* para verificar que se recibe un punto compatible y poder calcular correctamente la distancia siempre entre puntos del mismo subtipo. Aprovecha este diseño para crear ahora una clase `Linea`, que acepta `Punto`, sin saber de qué tipo es, y es capaz de dar su longitud independientemente de las dimensiones de sus puntos (las cuales desconoce).

abstract class Punto {
    public abstract double calcularDistanciaA(Punto otro);
}

class Punto2D extends Punto {
    double x, y;

    public Punto2D(double x, double y) {
        this.x = x;
        this.y = y;
    }

    @Override
    public double calcularDistanciaA(Punto otro) {
        if (!(otro instanceof Punto2D)) {
            throw new IllegalArgumentException("Los puntos deben ser del mismo tipo");
        }
        Punto2D p = (Punto2D) otro;
        return Math.sqrt(Math.pow(x - p.x, 2) + Math.pow(y - p.y, 2));
    }
}

class Punto3D extends Punto {
    double x, y, z;

    public Punto3D(double x, double y, double z) {
        this.x = x;
        this.y = y;
        this.z = z;
    }

    @Override
    public double calcularDistanciaA(Punto otro) {
        if (!(otro instanceof Punto3D)) {
            throw new IllegalArgumentException("Los puntos deben ser del mismo tipo");
        }
        Punto3D p = (Punto3D) otro;
        return Math.sqrt(
            Math.pow(x - p.x, 2) +
            Math.pow(y - p.y, 2) +
            Math.pow(z - p.z, 2)
        );
    }
}

class Linea {
    private Punto p1, p2;

    public Linea(Punto p1, Punto p2) {
        this.p1 = p1;
        this.p2 = p2;
    }

    public double longitud() {
        return p1.calcularDistanciaA(p2);
    }
}


## 11. ¿Qué es la **"herencia de interfaces"** en Java? ¿Existe **"herencia múltiple de interfaces"**? Pon un ejemplo de una interfaz `Fichero` que tenga un método para leer su contenido en forma de `String` y luego dicha interfaz sea extendida por otra que sea `FicheroEscribible` que permita enviar contenido e incluso eliminar el fichero.

La herencia de interfaces permite que una interfaz extienda a otra, heredando sus métodos.

Sí, existe la herencia múltiple de interfaces.

interface Fichero {
    String leer();
}

interface FicheroEscribible extends Fichero {
    void escribir(String contenido);
    void eliminar();
}

class FicheroTexto implements FicheroEscribible {
    private String contenido = "";

    @Override
    public String leer() {
        return contenido;
    }

    @Override
    public void escribir(String contenido) {
        this.contenido = contenido;
    }

    @Override
    public void eliminar() {
        this.contenido = "";
    }
}
