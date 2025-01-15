# CalculadoraKotlin

CalculadoraJava es una aplicación extremadamente simple realizada en Android Studio usando el lenguaje de programación Kotliny una interfaz realizada usando *Jetpack Compose*. El objetivo de la aplicación es el aprendizaje de las herramientas utilizadas y tener cierta experiencia en la creación de aplicaciones móviles, aprendiendo en el proceso las bases de la tecnología *Jetpack Compose*.

## Interfaz *Jetpack Compose*

Se ha creado la interfaz para la aplicación utilizando *Jetpack Compose*. Es una interfaz muy simple que incluye dos campos de texto, un botón de suma y un campo en el que se escribirá el resultado. El código es el siguiente:

```java
@Composable
fun Content(modifier: Modifier = Modifier) {
    var firstNumber by remember { mutableStateOf("") }
    var secondNumber by remember { mutableStateOf("") }
    var result by remember { mutableStateOf("") }
    Column(
        modifier = modifier
            .fillMaxSize()
            .padding(top = 50.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Top
    )

    {
        TextField(
            value = firstNumber,
            keyboardOptions = KeyboardOptions.Default.copy(keyboardType = KeyboardType.Number),
            onValueChange = { firstNumber = it },
            label = { Text("First Number") }
        )


        Button(onClick = {
            val first = firstNumber.toIntOrNull() ?: 0
            val second = secondNumber.toIntOrNull() ?: 0
            result = (first + second).toString()
        }) {
            Text("+")
        }

        TextField(
            value = secondNumber,
            keyboardOptions = KeyboardOptions.Default.copy(keyboardType = KeyboardType.Number),
            onValueChange = { secondNumber = it },
            label = { Text("Second Number") }
        )
        Text(
            text = result
        )
    }
}
```

## Interfaz en el dispositivo

Dicho código de *Jetpack Compose* resulta en la siguiente interfaz gráfica en los dispositivo Android:
![imagen](https://github.com/user-attachments/assets/4d5314c9-1aa9-4993-bbab-e54e5011727d)



## Creado por Víctor Gómez
