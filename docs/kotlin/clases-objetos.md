# Orientación a objetos en Kotlin

En este apartado ya vamos a ver cómo crear nuestras propias clases y objetos en Kotlin. La programación orientada a objetos (POO) es un paradigma de programación que se basa en el concepto de "objetos", que son instancias de clases que encapsulan datos y comportamientos relacionados.

## Clases

En Kotlin, una clase se define utilizando la palabra clave `class`, seguida del nombre de la clase. Por ejemplo, podemos definir una clase llamada `Persona` de la siguiente manera:

```kotlin
class Persona {
    var nombre: String = ""
    var edad: Int = 0
}
```

En este ejemplo, hemos definido una clase `Persona` con dos propiedades: `nombre` de tipo `String` y `edad` de tipo `Int`. Las propiedades se definen utilizando la palabra clave `var`, lo que significa que son mutables y pueden cambiar su valor a lo largo del tiempo.

### Objetos

Un objeto es una instancia específica de una clase. En Kotlin, podemos crear objetos de la clase `Persona` de la siguiente manera:

```kotlin
val persona1 = Persona()
```

La orientación a objetos nos permite crear múltiples instancias de la clase `Persona`, cada una con sus propios valores para las propiedades `nombre` y `edad`. Por ejemplo:

```kotlin
val persona1 = Persona()
persona1.nombre = "Juan"
persona1.edad = 25
```

### Constructores

En Kotlin, podemos definir un constructor primario para una clase utilizando la sintaxis de paréntesis después del nombre de la clase. Por ejemplo, podemos modificar la clase `Persona` para incluir un constructor primario que acepte parámetros para inicializar las propiedades `nombre` y `edad`:

```kotlin
class Persona(val nombre: String, var edad: Int)
```

Habrás podido notar que hemos utilizado `val` para la propiedad `nombre`, lo que significa que es inmutable y no se puede cambiar después de la creación del objeto, mientras que `edad` es mutable y puede cambiar su valor.

También podemos crear un objeto de la clase `Persona` utilizando el constructor primario de la siguiente manera:

```kotlin
val persona1 = Persona("Juan", 25)
```

Recuerda que en Kotlin, a diferencia de Java, no es necesario utilizar la palabra clave `new` para crear un objeto. Simplemente llamamos al constructor de la clase como si fuera una función.

#### Bloque inicializador

También podemos utilizar un bloque inicializador (`init`) dentro de la clase para realizar acciones adicionales durante la creación del objeto. Por ejemplo, podemos agregar un bloque inicializador a la clase `Persona` para imprimir un mensaje cuando se crea un objeto:

```kotlin
class Persona(val nombre: String, var edad: Int) {
    init {
        println("Se ha creado una persona llamada $nombre con edad $edad.")
    }
}
```

#### Constructores secundarios

En kotlin, también podemos definir constructores secundarios utilizando la palabra clave `constructor`. Los constructores secundarios nos permiten crear objetos de una clase de diferentes maneras, proporcionando flexibilidad en la inicialización de las propiedades. Por ejemplo, podemos agregar un constructor secundario a la clase `Persona` que acepte solo el nombre y establezca un valor predeterminado para la edad:


```kotlin
class Persona(val nombre: String, var edad: Int) {
    constructor(nombre: String) : this(nombre, 0)
}
```

### Propiedades y métodos

Vamos a ver cómo agregar propiedades y métodos a nuestra clase `Persona`. Las propiedades son variables que pertenecen a la clase, mientras que los métodos son funciones que definen el comportamiento de la clase. Por ejemplo, podemos agregar un método llamado `saludar` a la clase `Persona` que imprima un mensaje de saludo utilizando el nombre de la persona:

```kotlin
class Persona(val nombre: String, var edad: Int) {
    fun saludar() {
        println("Hola, mi nombre es $nombre y tengo $edad años.")
    }
}
```

En este ejemplo, hemos agregado un método `saludar` que utiliza las propiedades `nombre` y `edad` para imprimir un mensaje de saludo en la consola. Podemos llamar a este método desde un objeto de la clase `Persona` de la siguiente manera:

```kotlin
val persona1 = Persona("Juan", 25)
persona1.saludar() // Imprime: Hola, mi nombre es Juan y tengo 25 años.
```

### Data classes

En Kotlin, podemos definir clases de datos (data classes) utilizando la palabra clave `data`. Las data classes son clases que se utilizan principalmente para almacenar datos y proporcionan automáticamente métodos como `toString()`, `equals()`, `hashCode()` y `copy()`. Por ejemplo, podemos definir una data class llamada `Persona` de la siguiente manera:

```kotlin
data class Persona(val nombre: String, var edad: Int)
```

Esto es muy útil cuando queremos crear clases que representen entidades de datos, ya que nos ahorra tiempo al generar automáticamente los métodos mencionados anteriormente.


