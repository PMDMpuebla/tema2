# Null-Safety en Kotlin

Una de las características más destacadas de Kotlin es su sistema de null-safety, que ayuda a prevenir errores relacionados con valores nulos en tiempo de compilación. En Kotlin, los tipos de datos son no nulos por defecto, lo que significa que no se puede asignar un valor nulo a una variable a menos que se indique explícitamente que puede ser nula.

Para declarar una variable que pueda ser nula, debemos usar el operador `?` después del tipo de dato. Por ejemplo:

```kotlin
var nombre: String? = null // La variable nombre puede ser nula
nombre = "Juan" // Asignamos un valor no nulo a la variable
```

El uso de `?` permite que la variable `nombre` pueda contener un valor nulo, mientras que si no se utiliza, la variable no podrá ser nula y el compilador generará un error si intentamos asignarle un valor nulo.

Existen varias formas de manejar valores nulos en Kotlin, como el operador de llamada segura `?.`, el operador Elvis `?:`, y la función `let`. A continuación, se presentan algunos ejemplos de cómo utilizar estas herramientas para trabajar con valores nulos de manera segura.

### Operador de llamada segura `?.`

El operador de llamada segura `?.` nos permite acceder a las propiedades o métodos de un objeto solo si este no es nulo. Si el objeto es nulo, la expresión completa devuelve null en lugar de lanzar una excepción. Por ejemplo:

```kotlin
val longitud: Int? = nombre?.length // Devuelve la longitud del nombre si no es nulo, de lo contrario devuelve null
```

#### Operador Elvis `?:`

El operador Elvis `?:` nos permite proporcionar un valor predeterminado en caso de que una expresión sea nula. Por ejemplo:

```kotlin
val longitud: Int = nombre?.length ?: 0 // Devuelve la longitud del nombre si no es nulo, de lo contrario devuelve 0
```

### Función `let`

La función `let` nos permite ejecutar un bloque de código solo si el objeto no es nulo. Dentro del bloque, podemos acceder al objeto utilizando la palabra clave `it`. Por ejemplo:

```kotlin
nombre?.let {
    println("El nombre tiene ${it.length} caracteres")
}
```

En este ejemplo, el bloque de código dentro de `let` solo se ejecutará si ` nombre` no es nulo, y podremos acceder a su longitud utilizando `it.length`.