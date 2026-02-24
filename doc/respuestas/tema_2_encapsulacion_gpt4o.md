<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Encapsulación". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: Clases y Objetos.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->
# TEMA 2. Encapsulación

## 1. En Programación Orientada a Objetos (POO), ¿Qué buscan la **encapsulación** y **la ocultación** de información? Enumera brevemente algunas ventajas de la ocultación de información.

### Respuesta

La encapsulación busca agrupar datos y comportamientos relacionados dentro de una unidad, típicamente una clase, y controlar el acceso a sus componentes internos. La ocultación de información es una parte fundamental de la encapsulación, y consiste en proteger los detalles internos de un objeto para que solo puedan ser accedidos o modificados a través de su interfaz pública.

Entre las ventajas de la ocultación de información destacan: evitar modificaciones accidentales o indebidas de los datos internos, facilitar el mantenimiento al poder cambiar la implementación interna sin afectar a usuarios de la clase, mejorar la modularidad y promover un diseño más robusto y seguro.

---

## 2. ¿Qué se entiende por la **interfaz pública** de un objeto o clase en POO? Describe brevemente cómo se relaciona con la ocultación de información.

### Respuesta

La interfaz pública de una clase o un objeto es el conjunto de métodos y atributos accesibles desde fuera que definen cómo se puede interactuar con ese objeto. Es la "cara visible" que otros componentes del programa utilizan para comunicarse con la clase.

La interfaz pública está relacionada con la ocultación de información porque limita el acceso directo a los detalles internos, exponiendo solo lo necesario para que otros puedan usar el objeto correctamente, mientras que protege el estado interno y la implementación.

---

## 3. Brevemente: ¿Por qué hay que ser conscientes y diseñar con cuidado la **interfaz pública** de una clase? ¿Es fácil cambiarla?

### Respuesta

La interfaz pública debe diseñarse cuidadosamente porque define el contrato que la clase ofrece a otros. Cambiarla posteriormente puede afectar a todo el código que dependa de ella, generando incompatibilidades y errores.

Por lo general, no es fácil modificar la interfaz pública sin repercusiones, por lo que se recomienda mantenerla estable y bien pensada para minimizar problemas a largo plazo.

---

## 4. ¿Qué son las **invariantes de clase** y por qué la ocultación de información nos ayuda?

### Respuesta

Las invariantes de clase son condiciones o propiedades que deben mantenerse verdaderas en todo momento para asegurar el correcto estado y funcionamiento de un objeto. Por ejemplo, un atributo que nunca debe ser negativo.

La ocultación de información ayuda a preservar estas invariantes porque restringe el acceso directo a los datos internos, permitiendo controlar y validar cualquier cambio solo mediante métodos específicos que garantizan que las invariantes se respeten.

---

## 5. Pon un ejemplo de una clase `Punto` en `Java`, con dos coordenadas, `x` e `y`, de tipo `double`, con un método `calcularDistanciaAOrigen`, y que haga uso de la ocultación de información. ¿Cuál es la interfaz pública de la clase `Punto`? ¿Qué significa `public` y `private`?

### Respuesta

```java id="s3t1wr"
public class Punto {
    private double x;
    private double y;

    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double calcularDistanciaAOrigen() {
        return Math.sqrt(x * x + y * y);
    }
}
```

La interfaz pública de la clase `Punto` está formada por el constructor y el método `calcularDistanciaAOrigen`, accesibles desde fuera de la clase.

La palabra clave `public` indica que un miembro es accesible desde cualquier otra clase, mientras que `private` significa que el miembro solo es accesible dentro de la propia clase, ocultando los detalles internos.

---

## 6. En Java, ¿A quiénes se pueden aplicar los modificadores `public` o `private`?

### Respuesta

En Java, los modificadores `public` y `private` pueden aplicarse a atributos, métodos, constructores y clases internas (clases anidadas). Un miembro `public` es accesible desde cualquier lugar, mientras que un miembro `private` solo es accesible dentro de la clase que lo declara.

No se pueden aplicar directamente a clases externas, que solo pueden ser públicas o tener visibilidad por defecto.

---

## 7. En POO, la visibilidad puede ser pública o privada, pero ¿existen más tipos de visibilidad? ¿Qué ocurre en Java? ¿Y en otros lenguajes?

### Respuesta

Sí, además de `public` y `private`, existen otros niveles de visibilidad. En Java, además están:

* `protected`: accesible dentro del mismo paquete y por subclases.
* Default (sin modificador): accesible solo dentro del mismo paquete.

En otros lenguajes, como C++, existen niveles adicionales como `friend` o `internal` en C#, que definen distintos grados de acceso.

---

## 8. Responde: Los miembros de instancia privados de un objeto están ocultos para (a) otras clases o (b) otras instancias, aunque sean de la misma clase. Pon un ejemplo añadiendo un método `calcularDistanciaAPunto(Punto otro)` y explica la respuesta.

### Respuesta

Los miembros privados están ocultos para (a) otras clases, pero no para (b) otras instancias de la misma clase. Es decir, dentro de una clase se puede acceder a los atributos privados de cualquier instancia de esa clase.

Ejemplo:

```java id="jjdr4g"
public double calcularDistanciaAPunto(Punto otro) {
    double dx = this.x - otro.x;  // Se puede acceder a 'x' de 'otro' aunque sea privado
    double dy = this.y - otro.y;
    return Math.sqrt(dx * dx + dy * dy);
}
```

Aquí, aunque `x` y `y` sean `private`, el método puede acceder a los atributos privados del objeto `otro` porque pertenece a la misma clase.

---

## 9. ¿Qué son los métodos "getter" y "setter" en los lenguajes orientados a objetos?

### Respuesta

Los métodos "getter" y "setter" son funciones públicas que permiten leer (get) y modificar (set) el valor de atributos privados de una clase. Son parte de la interfaz pública y permiten controlar el acceso a los datos, pudiendo validar o limitar cambios.

El uso de getters y setters ayuda a mantener la encapsulación, evitando el acceso directo a los atributos y facilitando la preservación de invariantes.

---

## 10. Cuando nos referimos a que la ocultación de información mejora la "seguridad" del programa, ¿nos referimos a que no pueda ser "hackeado"?

### Respuesta

No, la "seguridad" a la que se refiere la ocultación de información es principalmente la integridad interna del programa, evitando que partes del código modifiquen datos de forma incorrecta o accidental.

No está relacionada directamente con la seguridad frente a ataques externos o "hackeos", sino con evitar errores de diseño y mantener la consistencia del estado de los objetos.

---

## 11. ¿Qué diferencia hay entre **miembro de instancia** y **miembro de clase**? ¿Los miembros de clase también se pueden ocultar?

### Respuesta

Un miembro de instancia pertenece a cada objeto individual creado a partir de una clase, cada uno tiene su propia copia. Un miembro de clase, declarado con `static` en Java, pertenece a la clase en sí y es compartido por todas las instancias.

Ambos tipos pueden tener modificadores de visibilidad, por lo que los miembros de clase también se pueden ocultar con `private` y proteger el acceso.

---

## 12. Brevemente: ¿Tiene sentido que los constructores sean privados?

### Respuesta

Sí, tiene sentido en patrones de diseño donde se desea controlar la creación de objetos, como en singletons o métodos factoría, donde el constructor privado impide crear instancias directamente desde fuera.

Esto fuerza a usar métodos estáticos dentro de la clase para la creación controlada de objetos.

---

## 13. ¿Cómo se indican los **miembros de clase** en Java? Pon un ejemplo, en la clase `Punto` definida anteriormente, para que incluya miembros de clase que permitan saber cuáles son los valores `x` e `y` máximos que se han establecido en todos los puntos que se hayan creado hasta el momento.

### Respuesta

En Java, los miembros de clase se indican con la palabra clave `static`. Son compartidos por todas las instancias.

Ejemplo:

```java id="a2et6d"
public class Punto {
    private double x;
    private double y;

    private static double maxX = Double.NEGATIVE_INFINITY;
    private static double maxY = Double.NEGATIVE_INFINITY;

    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
        if (x > maxX) maxX = x;
        if (y > maxY) maxY = y;
    }

    public static double getMaxX() {
        return maxX;
    }

    public static double getMaxY() {
        return maxY;
    }
}
```

---

## 14. Como sería un método factoría dentro de la clase `Punto` para construir un `Punto` a partir de dos coordenadas, pero que las redondee al entero más cercano. Escribe sólo el código del método, no toda la clase ¿Has usado `static`?

### Respuesta

```java id="ewunx6"
public static Punto crearRedondeado(double x, double y) {
    return new Punto(Math.round(x), Math.round(y));
}
```

Sí, el método factoría se declara `static` para poder llamarlo sin necesidad de una instancia previa.

---

## 15. Cambia la implementación de `Punto`. En vez de dos `double`, emplea un array interno de dos posiciones, intentando no modificar la interfaz pública de la clase.

### Respuesta

```java id="7ybh0t"
public class Punto {
    private double[] coords = new double[2];

    public Punto(double x, double y) {
        coords[0] = x;
        coords[1] = y;
    }

    public double calcularDistanciaAOrigen() {
        return Math.sqrt(coords[0] * coords[0] + coords[1] * coords[1]);
    }
}
```

La interfaz pública permanece igual, solo cambia la implementación interna usando un array para las coordenadas.

---

## 16. Si un atributo va a tener un método "getter" y "setter" públicos, ¿no es mejor declararlo público? ¿Cuál es la convención más habitual sobre los atributos, que sean públicos o privados? ¿Tiene esto algo que ver con las "invariantes de clase"?

### Respuesta

No es recomendable declarar un atributo público aunque tenga getter y setter públicos, porque eso elimina el control sobre su acceso y modificación.

La convención más habitual es que los atributos sean `private` y que el acceso se realice mediante métodos getter y setter, que pueden validar o restringir cambios, protegiendo así las invariantes de clase y asegurando la consistencia del objeto.

---

## 17. ¿Qué significa que una clase sea **inmutable**? ¿qué es un método modificador? ¿Un método modificador es siempre un "setter"? ¿Tiene ventajas que una clase sea inmutable?

### Respuesta

Una clase es inmutable cuando sus objetos no pueden cambiar su estado después de ser creados. Todos sus atributos permanecen constantes durante la vida del objeto.

Un método modificador es cualquier método que altera el estado interno de un objeto, no siempre es un setter; puede modificar atributos indirectamente.

Las clases inmutables tienen ventajas como seguridad en entornos concurrentes, facilidad de razonamiento y evitar efectos secundarios inesperados.

---

## 18. ¿Es recomendable incluir métodos "setter" siempre y como convención?

### Respuesta

No es recomendable incluir setters indiscriminadamente. Solo debe proporcionarse un setter cuando sea necesario permitir la modificación controlada de un atributo.

Incluir setters sin necesidad puede romper invariantes o permitir cambios no deseados, afectando la integridad del objeto.

---

## 19. ¿La clase `String` en Java es mutable o inmutable? ¿Qué ocurre al concatenar dos cadenas? ¿Qué debemos hacer si vamos a hacer una operación que implique concatenar muchas veces para construir paso a paso una cadena muy larga?

### Respuesta

La clase `String` en Java es inmutable. Al concatenar dos cadenas se crea un nuevo objeto `String` con el resultado, sin modificar las originales.

Si se va a construir una cadena muy larga con muchas concatenaciones, se recomienda usar `StringBuilder` o `StringBuffer`, que permiten modificar el contenido sin crear nuevos objetos, mejorando la eficiencia.

---

## 20. En POO ¿Cómo se comparan objetos de una misma clase? ¿Por su contenido o por su identidad? ¿Qué es el método equals en Java? ¿Qué hace por defecto? ¿Cómo se deben comparar dos cadenas en Java?

### Respuesta

Por defecto, en Java los objetos se comparan por identidad, es decir, si son la misma instancia (mismo puntero en memoria). El método `equals` heredado de `Object` hace esta comparación.

Para comparar contenido, se debe sobrescribir `equals` para definir cuándo dos objetos son equivalentes en su estado.

Para comparar dos cadenas en Java por contenido, se usa el método `equals`, no el operador `==`, porque este último compara referencias.

---

## 21. ¿Qué son las clases "wrapper" en un lenguaje de programación orientado a objetos? ¿Cómo se hace? ¿Es un proceso automático? ¿Qué ventajas tienen? ¿Todos los lenguajes orientados a objetos tienen tipos primitivos y necesitan wrappers?

### Respuesta

Las clases wrapper son objetos que encapsulan tipos primitivos (como int o double) para permitir usarlos como objetos, con métodos y capacidades adicionales.

En Java, por ejemplo, `Integer` envuelve un `int`. La conversión automática entre primitivo y wrapper se llama autoboxing.

Las ventajas incluyen poder usar tipos primitivos en colecciones y beneficiarse de métodos de objetos.

No todos los lenguajes orientados a objetos tienen tipos primitivos; algunos manejan todo como objetos y no necesitan wrappers.

---

## 22. ¿En POO qué es un **tipo de dato enumerado**? ¿En Java, un tipo de dato enumerado es una clase? ¿Qué ventajas tienen en términos de encapsulación los enumerados en Java?

### Respuesta

Un tipo de dato enumerado (enum) es un conjunto finito y nombrado de constantes, que permite representar valores discretos con significado.

En Java, un enum es una clase especial que puede contener atributos, métodos y constructores, combinando la simplicidad de las constantes con la potencia de los objetos.

Esto mejora la encapsulación al poder asociar comportamiento y datos a cada valor enumerado, manteniendo la seguridad y claridad.

---

## 23. Crea un tipo enumerado en Java que se llame `Mes`, con doce posibles instancias y que además proporcione métodos para obtener cuántos días tiene ese mes, el ordinal de ese mes en el año (1-12), empleando atributos privados y constructores del tipo enumerado.

### Respuesta

```java id="l1woa1"
public enum Mes {
    ENERO(31, 1),
    FEBRERO(28, 2),
    MARZO(31, 3),
    ABRIL(30, 4),
    MAYO(31, 5),
    JUNIO(30, 6),
    JULIO(31, 7),
    AGOSTO(31, 8),
    SEPTIEMBRE(30, 9),
    OCTUBRE(31, 10),
    NOVIEMBRE(30, 11),
    DICIEMBRE(31, 12);

    private final int dias;
    private final int ordinal;

    private Mes(int dias, int ordinal) {
        this.dias = dias;
        this.ordinal = ordinal;
    }

    public int getDias() {
        return dias;
    }

    public int getOrdinal() {
        return ordinal;
    }
}
```

---

## 24. Añade a la clase `Mes` del ejercicio anterior cuatro métodos para devolver si ese mes tiene algunos días de invierno, primavera, verano u otoño, indicando con un booleano el hemisferio (norte o sur, parámetro `enHemisferioNorte`). Es decir: `esDePrimavera(boolean esHemisferioNorte)`, `esDeVerano(boolean esHemisferioNorte)`, `esDeOtoño(boolean esHemisferioNorte)`, `esDeInvierno(boolean esHemisferioNorte)`

### Respuesta

```java id="q1v2fu"
public boolean esDePrimavera(boolean enHemisferioNorte) {
    if (enHemisferioNorte) {
        return this == MARZO || this == ABRIL || this == MAYO;
    } else {
        return this == SEPTIEMBRE || this == OCTUBRE || this == NOVIEMBRE;
    }
}

public boolean esDeVerano(boolean enHemisferioNorte) {
    if (enHemisferioNorte) {
        return this == JUNIO || this == JULIO || this == AGOSTO;
    } else {
        return this == DICIEMBRE || this == ENERO || this == FEBRERO;
    }
}

public boolean esDeOtoño(boolean enHemisferioNorte) {
    if (enHemisferioNorte) {
        return this == SEPTIEMBRE || this == OCTUBRE || this == NOVIEMBRE;
    } else {
        return this == MARZO || this == ABRIL || this == MAYO;
    }
}

public boolean esDeInvierno(boolean enHemisferioNorte) {
    if (enHemisferioNorte) {
        return this == DICIEMBRE || this == ENERO || this == FEBRERO;
    } else {
        return this == JUNIO || this == JULIO || this == AGOSTO;
    }
}
```

---



