# Uso de Kotlin en Android

Como hemos visto en la introducción, Kotlin es un lenguaje de programación moderno y conciso que se ha convertido en el lenguaje preferido para el desarrollo de aplicaciones Android. En este curso, aprenderemos a utilizar Kotlin para desarrollar aplicaciones Android, aprovechando sus características y ventajas para crear aplicaciones más robustas y mantenibles.

En este capítulo, nos centraremos en cómo utilizar Kotlin para crear aplicaciones Android, desde la creación de interfaces de usuario hasta el manejo de datos y la integración con servicios externos.

En el primer tema, vimos como creamos un proyecto de Android en Android Studio y cómo configuramos el entorno de desarrollo para trabajar con Kotlin. Ahora, vamos a profundizar en el uso de Kotlin dentro del ecosistema Android, explorando sus características y cómo aplicarlas en el desarrollo de aplicaciones móviles.

Es importante destacar que Kotlin es totalmente interoperable con Java, lo que significa que podemos utilizar bibliotecas y frameworks existentes en Java sin problemas. Esto nos permite aprovechar el ecosistema de Android y utilizar código Java dentro de nuestros archivos Kotlin.

Veamos un ejemplo de un `Activity` en Kotlin que utiliza código Java:

```kotlin
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val lista = ArrayList<String>()
        lista.add("Hola")
        println(lista[0])
    }
}
```

!!! note
    Las sentencias `import` nos permiten importar clases y paquetes de Java y Kotlin para utilizarlos en nuestro código. En este ejemplo, hemos importado la clase `AppCompatActivity` de AndroidX para crear nuestra actividad principal. Esto demuestra la interoperabilidad entre ambos lenguajes y nos permite aprovechar las bibliotecas y frameworks existentes en Java mientras escribimos nuestro código en Kotlin.

Más adelante, veremos cómo crear interfaces de usuario utilizando XML y cómo manejar eventos y datos en nuestras aplicaciones Android utilizando Kotlin. También exploraremos cómo trabajar con bases de datos, servicios web y otras funcionalidades avanzadas para crear aplicaciones móviles completas y funcionales.