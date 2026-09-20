# Colecciones en Kotlin

El uso de colecciones es fundamental en la programación, ya que nos permite almacenar y manipular conjuntos de datos de manera eficiente. Kotlin ofrece una amplia variedad de colecciones desde arrays hasta listas, conjuntos y mapas, tanto mutables como inmutables. En esta sección, exploraremos las diferentes colecciones disponibles en Kotlin y cómo utilizarlas.

## Array

Un `Array` es una estructura de datos que almacena una colección de elementos del mismo tipo. En Kotlin, los arrays son objetos y tienen métodos y propiedades específicos. Podemos crear un array utilizando la función `arrayOf()` o utilizando la clase `Array`. Por ejemplo:

```kotlin
val numeros:Array<Int> = arrayOf(1, 2, 3, 4, 5)
```

!!! info
    Los arrays en Kotlin son de tamaño fijo, lo que significa que no se pueden agregar ni eliminar elementos después de su creación. Si necesitamos una colección que pueda cambiar de tamaño, podemos utilizar listas mutables.

Los Arrays en Kotlin también pueden ser de tipos primitivos, como `IntArray`, `DoubleArray`, `BooleanArray`, entre otros. Por ejemplo:

```kotlin
val numerosPrimitivos:IntArray = intArrayOf(1, 2, 3, 4, 5)
```
También podemos usar el operador diamante (`<>`) para inferir el tipo de datos del array:

```kotlin
val numeros:Array<Int> = arrayOf(1, 2, 3, 4, 5)
```

Para acceder a los elementos del array, podemos utilizar el índice del elemento:

```kotlin
val primerNumero = numeros[0] // Accede al primer elemento (1)
```

Se puede obtener la longitud del array utilizando la propiedad `size`:

```kotlin
val longitud = numeros.size // Devuelve 5
```

!!! info
    Los indices de las listas en Kotlin comienzan en 0, por lo que el primer elemento tiene un índice de 0, el segundo elemento tiene un índice de 1, y así sucesivamente.


!!! info
    Kotlin proporciona varias funciones de extensión para trabajar con arrays, como `forEach`, `map`, `filter`, entre otras. Estas funciones nos permiten realizar operaciones en los elementos del array de manera más concisa y legible. Estas funciones son parte de la biblioteca estándar de Kotlin y se pueden utilizar con cualquier tipo de array.

Ejemplo de uso de la función `forEach`:

```kotlin
numeros.forEach { numero ->
    println(numero) // Imprime cada número en el array
}
```

Habrás podido notar el uso de -> en el ejemplo anterior. Este es un operador de flecha que se utiliza para definir una función lambda en Kotlin. Una función lambda es una función anónima que se puede pasar como argumento a otra función. En este caso, estamos pasando una función lambda a la función `forEach`, que se ejecutará para cada elemento del array. Más adelante, profundizaremos en el uso de funciones lambda y cómo aprovecharlas para trabajar con colecciones en Kotlin.

## Otras colecciones

Existen dos tipos principales de colecciones en Kotlin: inmutables y mutables. Las colecciones inmutables no pueden ser modificadas después de su creación, mientras que las colecciones mutables permiten agregar, eliminar o cambiar elementos.

### Colecciones inmutables

Las colecciones inmutables son aquellas que no pueden ser modificadas después de su creación. Esto significa que no se pueden agregar, eliminar ni cambiar elementos en la colección. Kotlin proporciona varias clases para trabajar con colecciones inmutables, como `List`, `Set` y `Map`.

Estas colecciones son útiles cuando queremos garantizar que los datos no se modifiquen accidentalmente, lo que puede ayudar a prevenir errores y hacer que nuestro código sea más seguro y fácil de entender.

#### List

Una `List` es una colección ordenada de elementos que permite duplicados. En Kotlin, podemos crear una lista inmutable utilizando la función `listOf()`. Por ejemplo:

```kotlin
val numeros:List<Int> = listOf(1, 2, 3, 4, 5)
```

Para acceder a los elementos de la lista, podemos utilizar el índice del elemento:

```kotlin
val primerNumero = numeros[0] // Accede al primer elemento (1)
```

#### Set

Un `Set` es una colección de elementos únicos, lo que significa que no permite duplicados. En Kotlin, podemos crear un conjunto inmutable utilizando la función `setOf()`. Por ejemplo:

```kotlin
val frutas = setOf("Manzana", "Banana", "Naranja")
```

Para verificar si un elemento está presente en el conjunto, podemos utilizar la función `contains()`:

```kotlin
val tieneManzana = frutas.contains("Manzana") // Devuelve true
```

#### Map

Un `Map` es una colección de pares clave-valor, donde cada clave es única y se asocia con un valor. En Kotlin, podemos crear un mapa inmutable utilizando la función `mapOf()`. Por ejemplo:

```kotlin
val edades = mapOf("Juan" to 25, "María" to 30, "Pedro" to 28)
```

El uso de mapas es útil cuando necesitamos asociar datos relacionados, como nombres y edades, y acceder a ellos de manera eficiente utilizando las claves.

Para saber si una clave está presente en el mapa, podemos utilizar la función `containsKey()`:

```kotlin
val tieneJuan = edades.containsKey("Juan") // Devuelve true
```

O si queremos obtener el valor asociado a una clave, podemos utilizar la función `get()`:

```kotlin
val edadJuan = edades.get("Juan") // Devuelve 25
```

### Colecciones mutables

Una colección mutable es aquella que puede ser modificada después de su creación. Esto significa que se pueden agregar, eliminar o cambiar elementos en la colección. Kotlin proporciona varias clases para trabajar con colecciones mutables, como `MutableList`, `MutableSet` y `MutableMap`.

Cada una de estas colecciones mutables tiene métodos específicos para agregar, eliminar y modificar elementos, lo que nos permite trabajar con datos de manera más flexible.

#### MutableList

Una `MutableList` es una lista que permite modificar sus elementos. Podemos crear una lista mutable utilizando la función `mutableListOf()`. Por ejemplo:

```kotlin
val numerosMutables = mutableListOf(1, 2, 3, 4, 5)
```

Para agregar un elemento a la lista, podemos utilizar el método `add()`:

```kotlin
numerosMutables.add(6) // Agrega el número 6 a la lista
```

Si queremos eliminar un elemento, podemos utilizar el método `remove()`:

```kotlin
numerosMutables.remove(3) // Elimina el número 3 de la lista
```

#### MutableSet

Al igual que un `Set` inmutable, un `MutableSet` es una colección de elementos únicos, pero permite modificaciones. Podemos crear un conjunto mutable utilizando la función `mutableSetOf()`. Por ejemplo:

```kotlin
val frutasMutables = mutableSetOf("Manzana", "Banana", "Naranja")
```

Para agregar un elemento al conjunto, podemos utilizar el método `add()`:

```kotlin
frutasMutables.add("Pera") // Agrega "Pera" al conjunto
```

Y para eliminar un elemento, podemos utilizar el método `remove()`:

```kotlin
frutasMutables.remove("Banana") // Elimina "Banana" del conjunto
```

#### MutableMap

Un `MutableMap` es un mapa que permite modificar sus pares clave-valor. Podemos crear un mapa mutable utilizando la función `mutableMapOf()`. Por ejemplo:

```kotlin
val edadesMutables = mutableMapOf("Juan" to 25, "María" to 30, "Pedro" to 28)
```

Para agregar un nuevo par clave-valor, podemos utilizar el método `put()`:

```kotlin
edadesMutables.put("Ana", 22) // Agrega el par "Ana" to 22 al mapa
```