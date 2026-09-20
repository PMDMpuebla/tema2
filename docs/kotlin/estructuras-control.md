# Estructuras de Control

Las estructuras de control son fundamentales en cualquier lenguaje de programación, ya que nos permiten controlar el flujo de ejecución de nuestro código. En Kotlin, contamos con varias estructuras de control que nos permiten tomar decisiones y repetir bloques de código según ciertas condiciones.

### Estructuras de control condicionales

Las estructuras de control condicionales nos permiten ejecutar diferentes bloques de código según se cumpla o no una determinada condición. En Kotlin, las principales estructuras de control condicionales son `if`, `else if` y `else`.

### If-else

La primera estructura de control condicional que veremos es `if-else`. Esta estructura nos permite ejecutar un bloque de código si se cumple una condición y otro bloque de código si no se cumple.

Su sintaxis básica es la siguiente:

```kotlin
if (condición) {
    // Bloque de código a ejecutar si la condición es verdadera
} else {
    // Bloque de código a ejecutar si la condición es falsa
}
```

La condición es una expresión que devuelve un valor booleano (`true` o `false`). Si la condición es verdadera, se ejecutará el primer bloque de código; de lo contrario, se ejecutará el bloque de código dentro del `else`.

#### Asignaciones condicionales con if

A diferencia de Java, kotlin permite asignar valores a variables utilizando la estructura `if` de manera directa. Esto significa que podemos utilizar `if` como una expresión que devuelve un valor, lo que nos permite asignar el resultado de la evaluación de la condición a una variable.

Veamos un ejemplo de cómo utilizar `if` para asignar valores a variables:

```kotlin
val numero = 10
val resultado = if (numero > 0) {
    "El número es positivo"
} else {
    "El número es negativo o cero"
}
println(resultado) // Imprime: El número es positivo
```

En este ejemplo, la variable `resultado` se asigna con el valor devuelto por la estructura `if`. Si la condición `numero > 0` es verdadera, se asignará el valor "El número es positivo"; de lo contrario, se asignará "El número es negativo o cero". Esto nos permite simplificar nuestro código y evitar la necesidad de utilizar variables adicionales para almacenar los resultados intermedios.

!!! info "Operador Ternario"
    En Kotlin, no existe un operador ternario como en otros lenguajes de programación. Sin embargo, podemos lograr un comportamiento similar utilizando la estructura `if` como una expresión que devuelve un valor, como se mostró en el ejemplo anterior. Esto nos permite asignar valores a variables de manera concisa y legible.

### When

La estructura `when` es una alternativa más poderosa y flexible al `if-else`. Nos permite evaluar múltiples condiciones de manera más clara y concisa. La sintaxis básica de `when` es la siguiente:

```kotlin
when (expresión) {
    valor1 -> {
        // Bloque de código a ejecutar si la expresión es igual a valor1
    }
    valor2 -> {
        // Bloque de código a ejecutar si la expresión es igual a valor2
    }
    else -> {
        // Bloque de código a ejecutar si ninguna de las condiciones anteriores se cumple
    }
}
```

Se parece mucho a la estructura `switch` de otros lenguajes, pero con más funcionalidades. Podemos evaluar cualquier tipo de expresión y no solo valores constantes. Además, podemos utilizar rangos, tipos y condiciones más complejas.

Veamos un ejemplo de cómo utilizar `when` para evaluar diferentes valores:

```kotlin
val numero = 3
when {
    numero % 2 == 0 -> println("El número es par")
    numero % 2 != 0 -> println("El número es impar")
    else -> println("El número es cero")
}
```

También podemos utilizar `when` como una expresión que devuelve un valor, lo que nos permite asignar el resultado de la evaluación a una variable:

```kotlin
val numero = 3
val resultado = when {
    numero % 2 == 0 -> "El número es par"
    numero % 2 != 0 -> "El número es impar"
    else -> "El número es cero"
}
println(resultado) // Imprime: El número es impar
```

## Estructuras de control Repetitivas

Las estructuras de control repetitivas nos permiten ejecutar un bloque de código varias veces mientras se cumpla una determinada condición. En Kotlin, las principales estructuras de control repetitivas son `for`, `while` y `do-while`.

### While

La estructura `while` nos permite ejecutar un bloque de código mientras se cumpla una condición. La sintaxis básica de `while` es la siguiente:

```kotlin
while (condición) {
    // Bloque de código a ejecutar mientras la condición sea verdadera
}
```

La condición es una expresión que devuelve un valor booleano (`true` o `false`). Mientras la condición sea verdadera, se ejecutará el bloque de código dentro del `while`. Una vez que la condición sea falsa, se saldrá del bucle y se continuará con la ejecución del código siguiente.

### do-while

La estructura `do-while` es similar a `while`, pero garantiza que el bloque de código se ejecute al menos una vez, ya que la condición se evalúa después de ejecutar el bloque de código. La sintaxis básica de `do-while` es la siguiente:

```kotlin
do {
    // Bloque de código a ejecutar al menos una vez
} while (condición)
```

La principal diferencia entre `while` y `do-while` es que en `do-while`, el bloque de código se ejecuta primero y luego se evalúa la condición. Esto significa que incluso si la condición es falsa desde el principio, el bloque de código se ejecutará al menos una vez.

### For

La estructura `for` nos permite iterar sobre una colección de elementos, como listas, arreglos o rangos. La sintaxis básica de `for` es la siguiente:

```kotlin
for (elemento in colección) {
    // Bloque de código a ejecutar para cada elemento de la colección
}
```

Nos referimos a cada elemento de la colección utilizando la variable `elemento`, y podemos realizar operaciones o acciones con cada uno de ellos dentro del bloque de código. También pueden usarse rangos para iterar sobre un conjunto de valores numéricos. Por ejemplo:

```kotlin
for (i in 1..5) {
    println(i) // Imprime los números del 1 al 5
}
```

El uso de `for` es muy útil cuando necesitamos realizar acciones repetitivas sobre una colección de elementos o un rango de valores, y nos permite escribir código más limpio y legible.

A diferencia de java, en Kotlin no es necesario utilizar un índice para acceder a los elementos de una colección, ya que podemos iterar directamente sobre los elementos utilizando la sintaxis `for (elemento in colección)`. Esto hace que el código sea más conciso y fácil de leer.