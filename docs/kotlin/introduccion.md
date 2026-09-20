# Introducción a Kotlin

Kotlin es un lenguaje de programación moderno y conciso que se ejecuta en la máquina virtual de Java (JVM) y es totalmente interoperable con Java. Fue desarrollado por JetBrains y se ha convertido en un lenguaje oficial para el desarrollo de aplicaciones Android. Kotlin combina características de programación orientada a objetos y funcional, lo que permite a los desarrolladores escribir código más limpio, seguro y expresivo.

Kotlin ofrece varias ventajas sobre Java, como una sintaxis más concisa, la eliminación de la necesidad de escribir código repetitivo (boilerplate), y características avanzadas como null safety, extensiones de funciones y corutinas para programación asíncrona. Estas características hacen que Kotlin sea una opción atractiva para el desarrollo de aplicaciones móviles, ya que permite a los desarrolladores crear aplicaciones más rápidas y eficientes.

Algunas de las características clave de Kotlin incluyen:

* **Sintaxis concisa**: Kotlin reduce la cantidad de código necesario para realizar tareas comunes, lo que facilita la lectura y el mantenimiento del código.
* **Null safety**: Kotlin tiene un sistema de tipos que ayuda a prevenir errores de null pointer, lo que mejora la seguridad y estabilidad de las aplicaciones.
* **Interoperabilidad con Java**: Kotlin puede coexistir con código Java, lo que permite a los desarrolladores migrar gradualmente sus proyectos existentes a Kotlin sin tener que reescribir todo el código.
* **Funciones de extensión**: Kotlin permite agregar nuevas funcionalidades a las clases existentes sin tener que heredar de ellas, lo que facilita la creación de APIs más limpias y expresivas.
* **Corutinas**: Kotlin proporciona soporte nativo para corutinas, lo que facilita la programación asíncrona y concurrente, mejorando el rendimiento de las aplicaciones.
* **Multiplataforma**: Kotlin se puede utilizar para desarrollar aplicaciones en diferentes plataformas, incluyendo Android, iOS, web y backend, lo que permite a los desarrolladores compartir código entre diferentes proyectos.

## Instalación de Kotlin usando IntelliJ IDEA

Aunque el curso de Android se basa en el uso de Android Studio, que ya incluye soporte para Kotlin, es recomendable instalar IntelliJ IDEA, un IDE desarrollado por JetBrains, la misma compañía que creó Kotlin. IntelliJ IDEA ofrece un entorno de desarrollo completo y optimizado para trabajar con Kotlin, lo que facilita la escritura, depuración y ejecución de código Kotlin.

Puedes descargar la versión Community de IntelliJ IDEA desde el sitio web oficial: [https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/). Una vez instalado, puedes crear un nuevo proyecto Kotlin y comenzar a explorar las características del lenguaje.

Para crear un proyecto Kotlin en IntelliJ IDEA, sigue estos pasos:

1. Abre IntelliJ IDEA y selecciona "New Project".
2. En la ventana de creación de proyectos, selecciona "Kotlin" en el panel izquierdo y elige "JVM | IDEA" como tipo de proyecto.
3. Configura el nombre del proyecto y la ubicación donde deseas guardarlo, luego haz clic en "Finish".
4. Una vez creado el proyecto, puedes agregar un nuevo archivo Kotlin con extensión `.kt` y comenzar a escribir tu código.

## Hola Mundo en Kotlin

Vamos a ver el Hola mundo en Kotlin. Para ello, crearemos un archivo con extensión `.kt` y escribiremos el siguiente código:

```kotlin
fun main() {
    println("Hola mundo")
}
```

Como habrás podido ver, la sintaxis de Kotlin es bastante simple y directa. La función `main` es el punto de entrada de la aplicación, y `println` se utiliza para imprimir texto en la consola. Al ejecutar este programa, verás el mensaje "Hola mundo" en la salida de la consola.

!!! note
    En Kotlin, a diferencia de java no es necesario terminar las instrucciones con punto y coma (;). Esto hace que el código sea más limpio y fácil de leer. Sin embargo, si lo deseas, puedes usar punto y coma para separar múltiples instrucciones en una sola línea.