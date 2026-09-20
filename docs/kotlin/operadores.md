# Operadores

En Kotlin, los operadores son símbolos especiales que realizan operaciones sobre uno o más operandos. Estos operadores nos permiten realizar cálculos, comparaciones y otras operaciones fundamentales en nuestros programas.

## Operadores aritméticos

Los operadores aritméticos se utilizan para realizar operaciones matemáticas básicas. Algunos de los operadores aritméticos más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `+`      | Suma        | `val resultado = 5 + 3` |
| `-`      | Resta       | `val resultado = 5 - 3` |
| `*`      | Multiplicación | `val resultado = 5 * 3` |
| `/`      | División    | `val resultado = 5 / 3` |
| `%`      | Módulo      | `val resultado = 5 % 3` |

## Operadores de comparación

Los operadores de comparación se utilizan para comparar valores y devolver un resultado booleano (`true` o `false`). Algunos de los operadores de comparación más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `==`     | Igualdad    | `val esIgual = (5 == 3)` |
| `!=`     | Desigualdad | `val esDiferente = (5 != 3)` |
| `<`      | Menor que   | `val esMenor = (5 < 3)` |
| `>`      | Mayor que   | `val esMayor = (5 > 3)` |
| `<=`     | Menor o igual que | `val esMenorOIgual = (5 <= 3)` |
| `>=`     | Mayor o igual que | `val esMayorOIgual = (5 >= 3)` |

## Operadores lógicos

Los operadores lógicos se utilizan para combinar expresiones booleanas y devolver un resultado booleano. Algunos de los operadores lógicos más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `&&`     | AND lógico  | `val resultado = (true && false)` |
| `||`     | OR lógico   | `val resultado = (true || false)` |
| `!`      | NOT lógico  | `val resultado = !true` |

## Operadores de asignación

Los operadores de asignación se utilizan para asignar valores a variables. Algunos de los operadores de asignación más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `=`      | Asignación  | `var x = 5` |
| `+=`     | Asignación con suma | `x += 3` (equivalente a `x = x + 3`) |
| `-=`     | Asignación con resta | `x -= 3` (equivalente a `x = x - 3`) |
| `*=`     | Asignación con multiplicación | `x *= 3` (equivalente a `x = x * 3`) |
| `/=`     | Asignación con división | `x /= 3` (equivalente a `x = x / 3`) |
| `%=`     | Asignación con módulo | `x %= 3` (equivalente a `x = x % 3`) |

## Operadores de incremento y decremento

Los operadores de incremento y decremento se utilizan para aumentar o disminuir el valor de una variable en 1. Algunos de los operadores de incremento y decremento más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `++`     | Incremento  | `x++` (equivalente a `x = x + 1`) |
| `--`     | Decremento  |  `x--` (equivalente a `x = x - 1`) |

## Operadores de rango

Los operadores de rango se utilizan para crear rangos de valores. Algunos de los operadores de rango más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `..`     | Rango inclusivo | `val rango = 1..5` (incluye 1, 2, 3, 4, 5) |

## Operadores de pertenencia

Los operadores de pertenencia se utilizan para verificar si un valor pertenece a un rango o colección. Algunos de los operadores de pertenencia más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `in`     | Pertenencia | `val pertenece = 3 in 1..5` (devuelve `true`) |
| `!in`    | No pertenencia | `val noPertenece = 6 !in 1..5` (devuelve `true`) |

## Operadores de identidad

Los operadores de identidad se utilizan para verificar si dos referencias apuntan al mismo objeto en memoria. Algunos de los operadores de identidad más comunes en Kotlin son:

| Operador | Descripción | Ejemplo |
|----------|-------------|---------|
| `===`    | Identidad   | `val esMismoObjeto = (obj1 === obj2)` |
| `!==`    | No identidad | `val noEsMismoObjeto = (obj1 !== obj2)` |
