# DESARROLLO DE SISTEMAS MÓVILES
***Semana 1***

Tareita de Desarrollo de Sistemas Móviles, hacer los codelabs 1 Y 2 del Equipo de Google para el desarrrollo Android.

## Resumen
### Codelab 01
Jetpack Compose es la forma moderna de crear interfaces de usuario (IUs) para las apps de Android.
Existe un compilador online de Kotlin: [Playground Kotlin](https://developer.android.com/training/kotlinplayground?hl=es-419&_gl=1*ye7gzi*_up*MQ..&gclid=Cj0KCQjwna6_BhCbARIsALId2Z0w3uRHNG2sqhtY5KEHS77iDpmlg1ONC3INGGnnfkNx93W3wqzV1rMaArmbEALw_wcB&gclsrc=aw.ds)

#### Algo de sintaxis de Kotlin
Esta es la definición de la función main en Kotlin.
```Kotlin
fun main(){
	println("Hola mundo")
}
```
##### Recomendaciones en la escritura del código
- Los nombres deben seguir la escritura camello.
- Cada sentencia en su propia línea, no se usa punto y coma.
- La llave de cierre debe aparecer al final de la función, en la siguiente línea
- Debe haber un espacio entre los paréntesis de parámetros y la llave de apertura de la función.
- El cuerpo de la función debe tener una sangría de 4 espacios, ¡no usar la tabulación!

 Para profundizar sobre el estilo de escritura en Kotlin, sería mejor revisar la [Guía estilo Kotlin](https://developer.android.com/kotlin/style-guide?hl=es-419&_gl=1*1fqpk72*_up*MQ..&gclid=Cj0KCQjwna6_BhCbARIsALId2Z0w3uRHNG2sqhtY5KEHS77iDpmlg1ONC3INGGnnfkNx93W3wqzV1rMaArmbEALw_wcB&gclsrc=aw.ds)

##### Tipos de datos de Kotlin
| Tipo de datos | Qué puede contener en nuestro lenguaje | Ejemplos       |
| ------------- | -------------------------------------- | -------------- |
| String        | Texto                                  | "Add contract" |
| Int           | Número entero                          | 32             |
| Double        | Número decimal                         | 25.01          |
| Float         | Número decimal de menor presición      | 5.41f          |
| Boolean       | Valores `true` o `false`               | true           |

Para saber más sobre los rangos de valores para cada dato, consultar [Tipos básicos en Kotlin](https://kotlinlang.org/docs/basic-types.html#numbers)

##### Declaración de una variable
Se usa la siguiente sintaxis
```Kotlin
val nombre : tipoDeDato = valorInicial
val contador : Int = 7
```
El compilador de Kotlin también puede inferir el tipo de dato cuando se inicializa
```Kotlin
val nombre = valorInicial
val numeroDeManzanas = 7
```
##### Mostrar el valor de una variable dentro de una string
Se puede usar un _escapador_ como $ antes de la variable para que se muestre, así com el sigueinte ejemplo.
```Kotlin
fun main() {
    val nombre : nombreAmigo = "Marx"
    println("Me llamo $nombreAmigo")
}
```
También se puede utilizar + para unir Strings y variables
```Kotlin
fun main() {
    val nextMeeting = "Next meeting is"
    val date = "January 1"
    val recordatorio = nextMeeting + date
    println(recordatorio)
}
```
Si se quiere escribir caracteres especiales, basta con _escaparlos_ con una \
```Kotlin
fun main() {
   val texto = "Hola puedo \"holear\""
}
```
Para hacer un comentario se puede usar // o /\*\*/ con un * en cada linea.
##### Funciones en Kotlin
Se puede definir una función y llamarla de la siguiente manera. Igual que, por ejemplo en c++
```Kotlin
fun main() {
    birthdayGreeting()
}

fun birthdayGreeting() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
```
Si queremos devolver un valor en una función, entonces deberá tener esta sintaxis. O sea, agregar el tipo de dato que devolverá. En caso contrario será una función _void_. También se puede especificar los parámetros u omitirlos.
```Kotlin
fun name(par1: tipo1, par2: tipo2, ...) : tipoDeDato {
	cuerpo
	return VariableADevolver
}

//Ejemplo

fun main() {
	println(mensajeDeCumpleanios(10))
}

fun mensajeDeCumpleanios(edad : Int) : String {
    val mensaje : String = "Feliz cum"
    return mensaje + ", hoy cumples "+edad;
}
```
También se puede pasar los parámetros en diferente orden, pero especificando los nombres de cada uno.
```Kotlin
println(birthdayGreeting(age = 2, name = "Rex"))
println(birthdayGreeting(name = "Rex", age = 2))
```
Se pueden definir argumentos predeterminados para los parámetros, esto serviría para que se muestren por defecto, en caso de no definirlos cuando se utiliza la función.
```Kotlin
fun birthdayGreeting(name: String = "Rover", age: Int): String {
    return "Happy Birthday, $name! You are now $age years old!"
}
```
#### Problemas prácticos en Kotlin
##### Impresión de mensajes
```Kotlin
fun main() {
	println("Use the val keyword when the value doesn't change.\nUse the var keyword when the value can change.\nWhen you define a function, you define the parameters that can be passed to it.\nWhen you call a function, you pass arguments for the parameters.")
}
```
##### Corrección de un error de compilación
```Kotlin
fun main() {
	println("New chat message from a friend'}
}
```
1. **¿Puedes determinar la causa raíz de los errores de compilación de este programa y corregirlos?**
	Sí, el error está en el uso del paréntesis de cierre de la segunda línea, está un corchete; además del cierre con comillas dobles, solo hay una.
2. **¿El código usa los símbolos apropiados para indicar la apertura y el cierre de la cadena y el argumento de la función?**
	No, debe cambiarse el corchete por un paréntesis.
3. **Código corregido**
```Kotlin
fun main() {
	println("New chat message from a friend")
}
```
##### Plantillas de strings
```Kotlin
fun main() {
	val discountPercentage: Int = 0
	val offer: String = ""
	val item = "Google Chromecast"
	discountPercentage = 20
	offer = "Sale - Up to $discountPercentage% discount on $item! Hurry up!"
	println(offer)
}
```
1. **¿Puedes determinar la causa raíz de esos errores y corregirlos?**
	Las variables val, no pueden ser reasignadas; en cambio, debe usarse una variable var.
2. **¿Puedes determinar el resultado de este programa antes de ejecutar el código en Kotlin Playground?**
	Sí.
3. **Código corregido**
```Kotlin
fun main() {
	var discountPercentage: Int = 0
	var offer: String = ""
	var item = "Google Chromecast"
	discountPercentage = 20
	offer = "Sale - Up to $discountPercentage% discount on $item! Hurry up!"
	println(offer)
}
```
##### Concatenación de strings
```Kotlin
fun main() {
	val numberOfAdults = "20"
	val numberOfKids = "30"
	val total = numberOfAdults + numberOfKids
	println("The total party size is: $total")
}
```
Hay un error, en este caso, solo se está juntando el 20 y el 30, porque han sido declaradas como string, para que se sumen se deben declarar sin comillas.
**Código corregido**
```Kotlin
fun main() {
	val numberOfAdults = 20
	val numberOfKids = 30
	val total = numberOfAdults + numberOfKids
	println("The total party size is: $total")
}
```
##### Implementación de matemáticas básicas
```Kotlin
fun main() {
	val firstNumber = 10
	val secondNumber = 5
	println("$firstNumber + $secondNumber = $result")
}
```
Hay un problema, falta definir la variable result. Adicionalmente, se pide que defina una función para sumar llamada add().
```Kotlin
fun main() {
	val firstNumber = 10
	val secondNumber = 5
	var resultado : Int = add(firstNumber, secondNumber) 
	println("$firstNumber + $secondNumber = $resultado")
}

fun add(valor1: Int, valor2: Int): Int {
	return valor1 + valor2
}
```
##### Parámetros predeterminados
```Kotlin
fun main() {
	val operatingSystem = "Chrome OS"
	val emailId = "sample@gmail.com"
	println(displayAlertMessage(operatingSystem, emailId))
	}
	// Define your displayAlertMessage() below this line.
```
Se pide implementar esa función
```Kotlin
fun main() {
	val operatingSystem = "Chrome OS"
	val emailId = "sample@gmail.com"
	println(displayAlertMessage())
    println(displayAlertMessage("hola", "hola"))
    println(displayAlertMessage("adios", "adios"))
}
fun displayAlertMessage(operatingSystem: String = "Unknown OS", emailId: String = "use_one@gmail.com"): String {
    val message = "There's a new sing-in request on $operatingSystem for your Google Account $emailId"
    return message
}
```
##### Podómetro
Ajusta el código a las prácticas recomendadas
```Kotlin
fun main() {
    val steps = 4000
    val caloriesBurned = calculateCaloriesFromSteps(steps)
    println("Walking $steps steps burns $caloriesBurned calories")
}

fun calculateCaloriesFromSteps(steps: Int): Double {
    val caloriesPerStep = 0.04
    val totalCaloriesBurned = steps * caloriesPerStep
    return totalCaloriesBurned
}
```
##### Comparación de dos números
```Kotlin
fun main() {
	println(usoDelTelefono(100, 150))
	println(usoDelTelefono(70, 70))
	println(usoDelTelefono(200, 50))
	
}
fun usoDelTelefono(minutosAyer: Int, minutosHoy: Int): Boolean {
	var pasasteMasTiempo: Boolean = false
	if(minutosAyer > minutosHoy) {
		pasasteMasTiempo = true
	}
	return pasasteMasTiempo
}
```
##### Movimiento del código duplicado a una función
En este programa, se muestra el clima de diferentes ciudades. Incluye el nombre de la ciudad, las temperaturas máxima y mínima del día, y las probabilidades de lluvia.

```Kotlin
fun main() {
	println("City: Ankara")
	println("Low temperature: 27, High temperature: 31")
	println("Chance of rain: 82%")
	println()
	println("City: Tokyo")
	println("Low temperature: 32, High temperature: 36")
	println("Chance of rain: 10%")
	println()
	println("City: Cape Town")
	println("Low temperature: 59, High temperature: 64")
	println("Chance of rain: 2%")
	println()
	println("City: Guatemala City")
	println("Low temperature: 50, High temperature: 55")
	println("Chance of rain: 7%")
	println()
}
```

Para optimizar el código haría una función para evitar la redundancia de ciudades con sus temperaturas.
```Kotlin
fun main() {
    println(climaCiudad("Ankara", 27, 31, 82))
    println()
    println(climaCiudad("Tokyo", 32, 36, 10))
    println()
    println(climaCiudad("Cape Town", 59, 64, 2))
    println()
    println(climaCiudad("Guatemala City", 50, 55, 7))
}

fun climaCiudad(city: String, lowT: Int, highT: Int, chanceRain: Int): String {
    return "City: $city\nLow temperature: $lowT, High temperature: $highT\nChance of rain: $chanceRain%"
}
```

### Codelab 02
Cuando creamos una plantilla vacía, tenemos lo siguiente:
```Kotlin
package com.example.greetingcard  
  
import android.os.Bundle  
import androidx.activity.ComponentActivity  
import androidx.activity.compose.setContent  
import androidx.activity.enableEdgeToEdge  
import androidx.compose.foundation.layout.fillMaxSize  
import androidx.compose.foundation.layout.padding  
import androidx.compose.material3.Scaffold  
import androidx.compose.material3.Text  
import androidx.compose.runtime.Composable  
import androidx.compose.ui.Modifier  
import androidx.compose.ui.tooling.preview.Preview  
import com.example.greetingcard.ui.theme.GreetingCardTheme  
  
class MainActivity : ComponentActivity() {  
    override fun onCreate(savedInstanceState: Bundle?) {  
        super.onCreate(savedInstanceState)  
        enableEdgeToEdge()  
        setContent {  
            GreetingCardTheme {  
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->  
                    Greeting(  
                        name = "Android",  
                        modifier = Modifier.padding(innerPadding)  
                    )  
                }  
            }        }    }  
}  
  
@Composable  
fun Greeting(name: String, modifier: Modifier = Modifier) {  
    Text(  
        text = "Hello $name!",  
        modifier = modifier  
    )  
}  
  
@Preview(showBackground = true)  
@Composable  
fun GreetingPreview() {  
    GreetingCardTheme {  
        Greeting("Android")  
    }  
}
```
**Explicación**
La función onCreate() es la que llamará a otras funciones para compilar la interfaz de usuario. Es como un main().
El bloque setContent dentro de onCreate() define la interfaz gráfica usando Jetpack Compose, acá se puede llamar todas las funciones con el @Composable, esta anotación le indica al compilador que JetPack Compose usa esta función para generar la IU.

La función Greting() es una función definida en la que recibe un String y un Modifier.

La función GreetingPreview() permite ver el aspecto de la función de componibilidadsin tener que compilar la app por completo, para esto se aplica las anotaciones @Preview y @Composable. Sirve para ver el código funcionando sin compilarlo.

#### Algunos componentes
##### Surface
Es un contenedor que representa a una sección de la IU, como un bloque en el que se puede modificar el fondo, bordes, etc.

>Para poder englobar a un bloque de cógio, podemos utilizar alt+enter y luego sorround with widget.

Para más info de [Material Desing 3](https://m3.material.io/foundations/layout/understanding-layout/spacing#abccd6ce-1092-4ad0-9351-de75aeae0edf)
##### Modifier
Es una clase que sirve para decorar un elemento compatible como el siguiente ejemplo
```Kotlin
@Composable
fun Greeting(name: String, modifier: Modifier = Modifier) {
    Surface(color = Color.Cyan) {
    Text(
	    text = "Hi, my name is $name!",
	    modifier = modifier.padding(24.dp)
		)
	}
}
```
_el padding hace referencia al fondo del bloque de texto_
