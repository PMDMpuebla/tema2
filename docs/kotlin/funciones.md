# Funciones en Kotlin

En kotlin existen dos tipos de funciones: las funciones de nivel superior y las funciones miembro. Las funciones de nivel superior se definen fuera de cualquier clase, mientras que las funciones miembro se definen dentro de una clase.

## Funciones de nivel superior

Una función de nivel superior se define fuera de cualquier clase y puede ser llamada desde cualquier parte del código. Por ejemplo:

```kotlin
fun sumar(a: Int, b: Int): Int {
    return a + b
}
```

Como se puede observar, la función `sumar` recibe dos parámetros de tipo `Int` y devuelve un valor de tipo `Int`. Veamos la sintaxis de la función:

```kotlin
fun nombreDeLaFuncion(parametro1: Tipo1, parametro2: Tipo2): TipoDeRetorno {
    // Cuerpo de la función
}

```

El nombre de la función es `nombreDeLaFuncion`, y los parámetros se definen entre paréntesis, separados por comas. Cada parámetro tiene un nombre y un tipo. El tipo de retorno se especifica después de los dos puntos `:`. El cuerpo de la función se encuentra entre llaves `{}`.

!!! note
    Si no se establece el tipo de retorno, Kotlin lo infiere automáticamente. Si la función no devuelve ningún valor, se puede omitir el tipo de retorno o especificar `Unit`, que es equivalente a `void` en otros lenguajes.

Para llamar a la función, simplemente escribimos su nombre y pasamos los argumentos correspondientes:

```kotlin
val resultado = sumar(3, 5) // resultado será 8
```

### Parámetros con valores por defecto

Se pueden definir valores por defecto para los parámetros de una función. Esto permite que la función sea llamada sin necesidad de proporcionar todos los argumentos. Por ejemplo:

```kotlinkotlin
fun saludar(nombre: String = "Mundo") {
    println("Hola, $nombre!")
}
```

Si no se establece un valor para el parámetro `nombre`, se utilizará el valor por defecto "Mundo". Por lo tanto, podemos llamar a la función de las siguientes maneras:

```kotlin
saludar() // Imprime "Hola, Mundo!"
saludar("Kotlin") // Imprime "Hola, Kotlin!"
```

### Parámetros nombrados

Otro de los aspectos interesantes de Kotlin es que permite llamar a las funciones utilizando parámetros nombrados. Esto significa que podemos especificar el nombre del parámetro al pasar un argumento, lo que hace que el código sea más legible y claro. Por ejemplo:

```kotlin
fun crearUsuario(nombre: String, edad: Int) {
    println("Nombre: $nombre, Edad: $edad")
}
crearUsuario(nombre = "Alice", edad = 30) // Nombre: Alice, Edad: 30
crearUsuario(edad = 25, nombre = "Bob") // Nombre: Bob, Edad: 25
```

Aquí, al utilizar parámetros nombrados, podemos cambiar el orden de los argumentos al llamar a la función, siempre y cuando especifiquemos el nombre del parámetro correspondiente.

### Funciones Single-Expression

Podemos definir una función de una sola expresión utilizando la sintaxis de `=`. Esto es útil para funciones que realizan una operación simple y devuelven un valor. Por ejemplo:

```kotlin
fun multiplicar(a: Int, b: Int): Int = a * b
```

Como vemos en este caso, la función `multiplicar` toma dos parámetros de tipo `Int` y devuelve su producto. La sintaxis de una función de una sola expresión es más concisa y legible.

### Parámetros variables

Kotlin permite definir funciones con un número variable de argumentos utilizando el modificador `vararg`. Esto significa que podemos pasar cero o más argumentos del mismo tipo a la función. Por ejemplo:

```kotlin
fun sumarNumeros(vararg numeros: Int): Int {
    var suma = 0
    for (numero in numeros) {
        suma += numero
    }
    return suma
}
val resultado = sumarNumeros(1, 2, 3, 4, 5) // resultado será 15
```

### Funciones Infix

Las funciones infix son funciones que se pueden llamar utilizando una sintaxis especial, sin necesidad de utilizar paréntesis ni el operador de punto. Para definir una función infix, debemos marcarla con la palabra clave `infix`. Por ejemplo:

```kotlin
infix fun Int.sumarOtro(valor: Int): Int {
    return this + valor
}
val resultado = 5 sumarOtro 3 // resultado será 8
```

## Funciones miembro

Una función miembro se define dentro de una clase y puede acceder a los miembros de esa clase. Por ejemplo:

```kotlin
class Calculadora {
    fun sumar(a: Int, b: Int): Int {
        return a + b
    }
}
val calculadora = Calculadora()
val resultado = calculadora.sumar(3, 5) // resultado será 8
```

Más adelante, veremos cómo crear nuestras propias funciones miembro y cómo utilizarlas en nuestras clases. Por ahora, es importante entender la diferencia entre funciones de nivel superior y funciones miembro, y cómo se utilizan en Kotlin.

## Funciones Lambda

Una vez vistas las funciones de nivel superior y las funciones miembro, es importante mencionar las funciones lambda. Las funciones lambda son funciones anónimas que se pueden pasar como argumentos a otras funciones o asignar a variables. Se definen utilizando la sintaxis `{ parametros -> cuerpo }`. Por ejemplo:

```kotlin
val sumar: (Int, Int) -> Int = { a, b -> a + b }
val resultado = sumar(3, 5) // resultado será 8
```

Las funciones lambda son muy útiles en Kotlin, especialmente cuando se trabaja con colecciones y funciones de orden superior. Son unas de las características más poderosas del lenguaje y permiten escribir código más conciso y expresivo.

Es importante destacar que las funciones lambda pueden capturar variables del contexto en el que se definen, lo que les permite acceder a variables locales y miembros de la clase. Esto hace que las funciones lambda sean muy flexibles y útiles en una amplia variedad de situaciones.

Por ejemplo se pueden utilizar para filtrar elementos de una lista:

```kotlin
val numeros = listOf(1, 2, 3, 4, 5)
val numerosPares = numeros.filter { it % 2 == 0 } // Filtra los números pares
println(numerosPares) // Imprime [2, 4]
```

Las funciones lambda pueden usarse en diferentes contextos, como en la programación funcional, para crear funciones de orden superior, y para trabajar con colecciones y flujos de datos. Son una herramienta poderosa que permite a los desarrolladores escribir código más limpio, legible y expresivo.

Podemos crear "parámetros funcionales" que son funciones que se pasan como argumentos a otras funciones. Esto nos permite crear funciones más genéricas y reutilizables. Por ejemplo, podemos crear una función que reciba otra función como parámetro y la aplique a cada elemento de una lista:

```kotlin
fun <T> aplicarFuncion(lista: List<T>, funcion: (T) -> T): List<T> {
    return lista.map { funcion(it) }
}
val numeros = listOf(1, 2, 3, 4, 5)
val numerosMultiplicados = aplicarFuncion(numeros) { it * 2 } // Multiplica cada número por 2
println(numerosMultiplicados) // Imprime [2, 4, 6, 8, 10]
```

!!! info
    Habrás podido notar el uso de tipos genéricos en la función `aplicarFuncion`. Los tipos genéricos nos permiten crear funciones y clases que pueden trabajar con diferentes tipos de datos, lo que hace que nuestro código sea más flexible y reutilizable. En este caso, la función `aplicarFuncion` puede trabajar con listas de cualquier tipo de dato, ya que utiliza un parámetro genérico `T`.

### it: palabra clave para referirse al parámetro de la función lambda

En Kotlin, cuando una función lambda tiene un solo parámetro, podemos referirnos a ese parámetro utilizando la palabra clave `it`. Esto nos permite escribir funciones lambda más concisas y legibles. Por ejemplo:

```kotlin
val numeros = listOf(1, 2, 3, 4, 5)
val numerosPares = numeros.filter { it % 2 == 0 } // Filtra los números pares
println(numerosPares) // Imprime [2, 4]
```

### Funciones anónimas

Otro aspecto interesante de Kotlin es que permite definir funciones anónimas, que son funciones sin nombre. Las funciones anónimas se pueden utilizar en situaciones donde necesitamos una función temporal o cuando queremos pasar una función como argumento a otra función. Por ejemplo:

```kotlin
val numeros = listOf(1, 2, 3, 4, 5)
val numerosPares = numeros.filter(fun(numero) = numero % 2 == 0)
println(numerosPares) // Imprime [2, 4]
```

En este caso directamente se define y utiliza una función anónima para filtrar los números pares de la lista. Las funciones anónimas son útiles cuando necesitamos una función temporal y no queremos definir una función con nombre en otro lugar del código.