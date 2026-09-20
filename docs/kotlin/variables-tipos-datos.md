# Variables y tipos de datos en Kotlin

Vamos a comenzar por lo básico: las variables y los tipos de datos en Kotlin. En esta sección, aprenderemos cómo declarar variables, los diferentes tipos de datos disponibles y cómo utilizarlos en nuestros programas.

## Declaración de variables

Comenzaremos por la declaración de variables. En Kotlin, podemos declarar variables utilizando las palabras clave `val` y `var`. La diferencia entre ambas es que `val` se utiliza para declarar variables inmutables (constantes), mientras que `var` se utiliza para declarar variables mutables.

La sintaxis básica para declarar una variable es la siguiente:

```kotlin
val nombreVariable: TipoDeDato = valorInicial
```

Donde `nombreVariable` es el nombre que le damos a la variable, `TipoDeDato` es el tipo de dato que queremos asignarle y `valorInicial` es el valor que queremos asignar a la variable.

### Mutabilidad

Como hemos comentado, `val` se utiliza para declarar variables inmutables, lo que significa que una vez que se les asigna un valor, no se puede cambiar. Por otro lado, `var` se utiliza para declarar variables mutables, lo que significa que su valor puede cambiar a lo largo del tiempo.

El concepto de mutabilidad es importante en la programación, ya que nos permite controlar el estado de nuestras variables y evitar errores relacionados con cambios inesperados en su valor.

Cuando se declara una variable con `val`, se garantiza que su valor no cambiará, lo que puede ayudar a prevenir errores y hacer que nuestro código sea más seguro y fácil de entender. Por otro lado, cuando se declara una variable con `var`, debemos tener cuidado al modificar su valor, ya que esto puede llevar a errores si no se maneja correctamente.

### Tipos de datos

Vamos a ver los tipos de datos más comunes en Kotlin. Algunos de los tipos de datos más utilizados son:

| Tipo de dato | Descripción | Rango de valores |
|--------------|-------------|-----------------|
| Int          | Enteros     | -2,147,483,648 a 2,147,483,647 |
| Long         | Enteros largos | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807 |
| Float        | Números decimales de precisión simple | Aproximadamente ±3.40282347E+38F (6-7 dígitos decimales) |
| Double       | Números decimales de precisión doble | Aproximadamente ±1.79769313486231570E+308 (15-16 dígitos decimales) |
| Boolean      | Valores lógicos (verdadero o falso) | true o false |
| String       | Cadenas de texto | Secuencia de caracteres Unicode |
| Char         | Caracteres individuales | Un solo carácter Unicode |

Más adelante, veremos cómo crear nuestros propios tipos de datos y cómo utilizarlos en nuestros programas. Por ahora, es importante familiarizarse con estos tipos de datos básicos y entender cómo se utilizan en Kotlin.

## Ejemplo de uso de variables y tipos de datos

Veamos un ejemplo sencillo de cómo declarar y utilizar variables en Kotlin:

```kotlin
fun main() {
    val nombre: String = "Juan"
    var edad: Int = 25
    println("Nombre: $nombre")
    println("Edad: $edad")
    edad = 26 // Cambiamos el valor de la variable mutable
    println("Edad actualizada: $edad")
}
```

Veamos algunos puntos importantes de este ejemplo:

1. Hemos declarado una variable inmutable `nombre` de tipo `String` y le hemos asignado el valor "Juan".
2. Hemos declarado una variable mutable `edad` de tipo `Int` y le hemos asignado el valor 25.
3. Hemos utilizado la función `println` para imprimir los valores de las variables en la consola.
4. Hemos cambiado el valor de la variable `edad` a 26, demostrando que las variables mutables pueden ser modificadas.

!!! info
    Habrás visto que hemos utilizado la interpolación de cadenas para imprimir los valores de las variables. Esto nos permite incluir el valor de una variable dentro de una cadena de texto utilizando el símbolo `$` seguido del nombre de la variable. Esto permite realizar operaciones de concatenación de manera más sencilla y legible.

## Comentarios

Antes de continuar, es importante mencionar que en Kotlin podemos agregar comentarios a nuestro código para explicar su funcionamiento o para dejar notas para nosotros mismos o para otros desarrolladores. Los comentarios no afectan la ejecución del programa y son ignorados por el compilador.

Podemos encontrar dos tipos de comentarios en Kotlin:

* **Comentarios de una sola línea**: Se utilizan para agregar comentarios breves en una sola línea. Se escriben utilizando el símbolo `//`. Por ejemplo:

```kotlin
// Este es un comentario de una sola línea
val nombre: String = "Juan" // Declaramos una variable inmutable
```

* **Comentarios de varias líneas**: Se utilizan para agregar comentarios más extensos que abarcan varias líneas. Se escriben utilizando los símbolos `/*` al inicio y `*/` al final del comentario. Por ejemplo:

```kotlin
/*
Este es un comentario de varias líneas.
Podemos utilizarlo para explicar el funcionamiento de un bloque de código o para dejar notas más detalladas.
*/
```

!!! info
    Existe un tercer tipo de comentario llamado **comentario de documentación**, que se utiliza para generar documentación automática del código. Se escribe utilizando los símbolos `/**` al inicio y `*/` al final del comentario. Utiliza la misma sintaxis de Javadoc y permite agregar etiquetas especiales para describir parámetros, valores de retorno y excepciones.