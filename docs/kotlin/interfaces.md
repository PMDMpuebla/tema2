# Interfaces

En Kotlin, las interfaces son similares a las clases abstractas, pero permiten definir métodos con implementación por defecto y propiedades. Las interfaces no pueden ser instanciadas directamente, pero pueden ser implementadas por clases.

Una interface se define con la palabra clave `interface`:

```kotlin
interface Vehiculo {
    val velocidadMaxima: Int
    fun conducir()
    fun frenar() {
        println("El vehículo está frenando")
    }
}
```

En este ejemplo, hemos definido una interface llamada `Vehiculo` que tiene una propiedad `velocidadMaxima`, un método abstracto `conducir()` y un método con implementación por defecto `frenar()`.

!!! info
    Las interfaces en Kotlin pueden contener propiedades abstractas y métodos con implementación por defecto. Las clases que implementen la interface deben proporcionar una implementación para los métodos abstractos y pueden optar por sobrescribir los métodos con implementación por defecto si lo desean.

## Herencia de interfaces

En kotlin si se permiten heredar de múltiples interfaces. Una clase puede implementar varias interfaces separándolas con comas:

```kotlin
class Coche : Vehiculo, OtraInterface {
    override val velocidadMaxima: Int = 200
    override fun conducir() {
        println("El coche está conduciendo a $velocidadMaxima km/h")
    }
}
```

En este ejemplo, la clase `Coche` implementa la interface `Vehiculo` y proporciona una implementación para la propiedad `velocidadMaxima` y el método `conducir()`. La clase también puede optar por sobrescribir el método `frenar()` si lo desea.

