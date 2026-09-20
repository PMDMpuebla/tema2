# Herencia

La herencia es un concepto fundamental en la programación orientada a objetos que permite crear nuevas clases basadas en clases existentes. La clase que se hereda se llama clase base o superclase, mientras que la clase que hereda se llama clase derivada o subclase.

En kotlin, todas las clases son finales por defecto, lo que significa que no se pueden heredar. Para permitir la herencia, debemos marcar la clase base con la palabra clave `open`. Por ejemplo:

```kotlin
open class Animal {
    fun comer() {
        println("El animal está comiendo")
    }
}
```

```kotlin
class Perro : Animal() {
    fun ladrar() {
        println("El perro está ladrando")
    }
}
```

!!! info
    Una clase `final` no puede ser heredada, mientras que una clase `open` puede ser heredada. Por defecto, todas las clases en Kotlin son `final`, lo que significa que no se pueden heredar. Para permitir la herencia, debemos marcar la clase base con la palabra clave `open`. Esto es diferente a otros lenguajes de programación como Java, donde las clases son heredables por defecto.

En este ejemplo, hemos definido una clase `Animal` que está marcada como `open`, lo que permite que otras clases hereden de ella. La clase `Animal` tiene un método `comer()` que imprime un mensaje indicando que el animal está comiendo.

Habrás podido ver que se establece una función en la clase base cuando se establece la herencia en la clase `Perro`; esto se debe a que establece una relación de herencia entre la clase `Perro` y la clase `Animal`. La clase `Perro` hereda todas las propiedades y métodos de la clase `Animal`, lo que significa que puede acceder al método `comer()` definido en la clase base.

## Sobrescritura de métodos

En Kotlin, podemos sobrescribir métodos de la clase base en las clases derivadas utilizando la palabra clave `override`. Por ejemplo, podemos crear una clase `Perro` que herede de la clase `Animal` y sobrescriba el método `comer()`:

```kotlin
class Perro : Animal() {
    override fun comer() {
        println("El perro está comiendo")
    }
}
```

En este ejemplo, hemos definido una clase `Perro` que hereda de la clase `Animal`. La clase `Perro` sobrescribe el método `comer()` de la clase base, proporcionando su propia implementación que imprime un mensaje indicando que el perro está comiendo.

### Sobreescritura de propiedades

En Kotlin, también podemos sobrescribir propiedades de la clase base en las clases derivadas utilizando la palabra clave `override`. Por ejemplo, podemos crear una clase `Perro` que herede de la clase `Animal` y sobrescriba una propiedad `nombre`:

```kotlin
open class Animal {
    open val nombre: String = "Animal"
}

class Perro : Animal() {
    override val nombre: String = "Perro"
}
```

En este caso, hemos definido una propiedad `nombre` en la clase base `Animal` y la hemos marcado como `open`, lo que permite que las clases derivadas la sobrescriban. La clase `Perro` sobrescribe la propiedad `nombre`, proporcionando su propia implementación que devuelve el valor "Perro".

## Constructores y herencia

En Kotlin, los constructores de las clases base pueden ser llamados desde las clases derivadas utilizando la sintaxis `super()`. Por ejemplo, si tenemos una clase base `Animal` con un constructor que recibe un parámetro `nombre`, podemos llamar a ese constructor desde una clase derivada `Perro`:

```kotlin
open class Animal(val nombre: String) {
    fun comer() {
        println("$nombre está comiendo")
    }
}

class Perro(nombre: String) : Animal(nombre) {
    fun ladrar() {
        println("$nombre está ladrando")
    }
}
```

En este caso , hemos definido un constructor en la clase base `Animal` que recibe un parámetro `nombre`. La clase derivada `Perro` llama al constructor de la clase base utilizando `super(nombre)`, pasando el valor del parámetro `nombre` al constructor de la clase base. Esto permite que la clase derivada inicialice correctamente las propiedades heredadas de la clase base.

### Super

Para llamar a los métodos de la clase base desde una clase derivada, podemos utilizar la palabra clave `super`. Por ejemplo, si queremos llamar al método `comer()` de la clase base `Animal` desde la clase derivada `Perro`, podemos hacerlo de la siguiente manera:

```kotlin
class Perro(nombre: String) : Animal(nombre) {
    override fun comer() {
        super.comer() // Llamamos al método comer() de la clase base
        println("$nombre está comiendo como un perro")
    }
}
```

## Clases abstractas

Vamos a ver las clases abstractas. Una clase abstracta es una clase que no se puede instanciar directamente y que puede contener métodos abstractos, es decir, métodos que no tienen implementación y que deben ser implementados por las clases derivadas.

Veamos un ejemplo de una clase abstracta `Animal` con un método abstracto `hacerSonido()`:

```kotlin
abstract class Animal {
    abstract fun hacerSonido()
}
class Perro : Animal() {
    override fun hacerSonido() {
        println("El perro hace guau")
    }
}
class Gato : Animal() {
    override fun hacerSonido() {
        println("El gato hace miau")
    }
}
``` 

En este ejemplo, hemos definido una clase abstracta `Animal` que contiene un método abstracto `hacerSonido()`. Las clases derivadas `Perro` y `Gato` implementan el método `hacerSonido()` proporcionando su propia implementación que imprime un mensaje indicando el sonido que hace cada animal.

El uso de clases abstractas nos permite definir una interfaz común para un grupo de clases relacionadas, mientras que las clases derivadas proporcionan implementaciones específicas para los métodos abstractos. Esto fomenta la reutilización de código y la creación de jerarquías de clases más flexibles y mantenibles.

## Polimorfismo

El polimorfismo es un concepto fundamental en la programación orientada a objetos que permite que diferentes clases puedan ser tratadas de manera uniforme a través de una interfaz común. En Kotlin, podemos lograr el polimorfismo mediante la herencia y la implementación de interfaces.

También podemos definir varias funciones que tengan el mismo nombre pero diferentes parámetros, lo que se conoce como sobrecarga de funciones. Por ejemplo, podemos agregar un método `saludar` adicional a la clase `Persona` que acepte un parámetro opcional para personalizar el saludo:

```kotlin
class Persona(val nombre: String, var edad: Int) {
    fun saludar() {
        println("Hola, mi nombre es $nombre y tengo $edad años.")
    }
    fun saludar(saludo: String) {
        println("$saludo, mi nombre es $nombre y tengo $edad años.")
    }
}
```

## Extensiones de clases

Kotlin tiene casos especiales donde se puede extender una clase sin necesidad de heredar de ella. Esto se logra mediante las funciones de extensión, que nos permiten agregar nuevas funcionalidades a las clases existentes sin modificar su código fuente. Por ejemplo, podemos agregar una función de extensión `saludar()` a la clase `String`:

```kotlin
fun String.saludar() {
    println("Hola, $this!")
}
```

En este ejemplo, hemos definido una función de extensión `saludar()` para la clase `String`. La función utiliza la palabra clave `this` para referirse a la instancia de la clase `String` en la que se llama la función. Podemos llamar a esta función de extensión en cualquier objeto de tipo `String`:

```kotlin
val nombre = "Kotlin"
nombre.saludar() // Imprime: Hola, Kotlin!
```