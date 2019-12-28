# Curso de EdTeam de JavaScript

# [Características de Javascript](https://ed.team/clase/49/464/2201)

- Dinámicamente tipado
  - No le dices que especificar el tipo de dato

- La desventaja es que cuando las aplicaciones son grandes, se tiene que intentar deducir el tipo de dato.
- Interpretado (hay 2 interpretes)
  - Navegador 
  - Servidor (node.js)
- Prototipado
- Multiparadigma
  - Se puede programar te multiples formas con Javascript

- Microsoft (Visual Studio Code)

# [Empezar con Javascript](https://ed.team/clase/49/464/2202)

Para poder ejecutar un archivo Javascript, no se puede simplemente abrir el archivo sino que también hay que mezclarlo con HTML

### Primer modo
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>Holamundo</h1>   
    <script>
    alert('Hola mundo') 
    </script>
</body>
</html>
```
### Segundo modo
De este modo funciona, extrayendo el javascript que hay dentro de la misma carpeta, pero encapsulandolo, a diferencia del método anterior que es directo y no tan recomendado.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
   
    <h1>Holamundo</h1>
    <script src="scripts.js"></script>
     
</body>
</html>
```
### Tercer modo

También se puede extraer datos de un archivo javascript, por ejemplo podemos ver la declaración:
```js
let nombre = 'Jonathan'
```

Mientras que en el archivo HTML para poder mostrar el mensaje de alerta,  se haría de la siguiente forma: 

NOTA: HAY QUE TOMAR EN CUENTA DE QUE EL COMPILADOR LO LEE DE ARRIBA HACIA ABAJO, es decir, primero se lee el script externo:  
```html
<script src="scripts.js"></script>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
   
    <h1>Holamundo</h1>
    <script src="scripts.js"></script>
    <script>
        alert(`Hola ${nombre}`)
    </script>
     
</body>
</html>
```

# Condicionales y Ciclos

El flujo normal de un programa es de arriba hacia abajo. Los condicionales permiten romper ese flujo.

### Con una sola linea

```js
if('a' === 'b') console.log

```
Por otro lado, de este modo como se muestra a continuación el programa va a mostrar que es un error, porque el console.log esta referenciando o llamando a algo que se encuentra dentro de un bloque, por ende no lo va a reconocer el compilador, y tirará un error indicando que no lo encuentra. 

```js
if('a' === 'b')
{
console.log('Me ejecuté')
}

{
let empresa = 'EDteam'
}

console.log(empresa)
```
Por el contrario si la variable se encuentra fuera del bloque y el console.log se encuentra dentro del bloque como se muestra a continuación, viene a ser algo valido. Esto se llama "Scope"
```js
if('a' === 'b')
{
console.log('Me ejecuté')
}
let empresa = 'EDteam'
{
console.log(empresa)
}
```

### ¿Qué es bifurcación?

Es un término utilizado para hacer referencia cuando se utilizan 2 caminos, o al menos cuando en un condicional se pueden tomar varios caminos. Es necesario decir que en el ejemplo a continuación, el compilador va a tomar en cuenta el primero que sea true, es decir, en este caso va a tomar en cuenta el segundo if. Pues se cumple que 3 es mayor que 2.

```js
if (2>3){
  console.log('Pasó la condición')
}else if (3>2 ) {
  console.log('pasó la condición 2')
}else if (10>2) {
  console.log('pasó la condición 3')
}

console.log('siempre me voy a ejecutar')
```
### Ejercicio con condicionales

```js
let age = parseInt(prompt('Dime tu edad'),10)

if(age) {
  if(age >= 18){
    alert('Eres mayor de edad')
  }else{
    alert('Te faltan años')
  }
}else{
  age = parseInt(prompt('Tu edad debe ser un número'),10)
}
```

### 3.4 Valores truthy y falsy
**Falsy:**
Son aquellos valores que devuelven false, tales como:

- 0
- ""
- NaN
- Undefined
- null

**Truthy:**
Son aquellos valores que devuelven verdadero:

- string no vacío
- Número diferente de cero
- arrays
- objetos

### Switch

Se puede hacer un formulario:

```js
let answer = prompt(`La capital de Colombia es:
a. Bogotá
b. Lima
c. Madrid
d. México
e. La Paz

Escribe la letra de tu respuesta`).toUpperCase().trim()

switch (answer) {
case 'A':
  alert('¡Correcto!')
  break
case 'B':
  alert('Te equivocaste. Lima es: ')
  break;
default:
  alert('No has dado una respuesta')
  break;
}
```

### 3.6 Uso de For

Para sacar los números primos de 7.
```js
for (let i = 1; i<=100; i++){
if (i % 7 === 0) console.log(i)
}
```

### 3.7 Break y Continue

Por ejemplo, en el siguiente for se muestra que cada valor de i que llegue a ser multiplo de 7, entonces va a ser ignorado y no será impreso.
```js
for (let i = 1; i<=100; i++){
if (i % 7 === 0) continue
console.log(i)
}
```

```js
let n = 0
for (let i = 0; i <= 100; i++) 
{
  if(i % 7 === 0) {
    console.log(i)
    n++
  }
  if (n )
}
```

# Clase 2.1 y 2.2 

# [Comprender los tipos de dato](https://ed.team/clase/49/466/2208)

JavaScript es un lenguaje dinamicamente tipado, ya que uno no le dice a JavaScript el tipo de dato. Además puede cambiar el tipo de dato que se guarda.


```js
let myVar = 10
typeof myVar
"number"
//Se puede asignar después un sring
myVar = 'Hola mundo'

//lo anterior viene a ser normal en JavaScript
```

TypeCoertion:
```js
'2' * 40

//Va a tirar un resultado de 80, ya que el interprete convierte automaticamente el valor de string a un number.
//Si el 2 no fuese un numero, la operación no se podría hacer, por que tiraría lo siguiente: NaN (not a number)
```

## Asignación por valor o referencia

```js
let numbers1 = [1,2,3,4]

let numbers2 = numbers1

/* si pongo numbers2 en la consola, los valores seguirán siendo [1,2,3,4], ya que ahora apunta a numbers1.
Pero si a numbers2 se le agrega un valor:
numbers2.push(5)
E invocamoos nuevamente a numbers1 en la consola, este tendrá el nuevo valor que le fue agregado a numbers2.

*/
```
Cuando estamos con un tipo de dato primitivo, siempre al igualarlo se hacia por valor. Por eso cuando hacemos lo anterior con otro tipo de dato, siempre los resultados serán distintos, pero en este caso al parecer se hace por referencia, ya que al modificar el segundo también se modifica el primero.

## [Operadores de asignación o comparación](https://ed.team/clase/49/466/2211)

let edad = 38

edad += 1
edad va a ser igual a 39

Lo anterior es lo mismo que decir: edad = edad + 1

Algo sumamente interesante en los operadores de comparación (los cuales devuelven true o false):

5== '5' va a ser true

5 === '5' va a ser false

La doble igualdad compara valores, la triple igualdad compara valores y tipo de datos.

Si fuese el caso de

5!== '5' el resultado va a ser true, porque lo que se evalua es la diferencia.

**Se pueden comparar letras por orden alfabetico** del siguiente modo:

'a' > 'b' sera igual a false
'b' > 'a' sera igual a true

### [Operadores unarios y aritmeticos](https://ed.team/clase/49/466/2212)

Serviría para averiguar si determinado número es par.
13 % 2 === 0
false

number-- (postdecremento: se ejecuta en la siguiente)

En ciclos es importante mmanejarlo. Ya que se hace varias veces una misma orden.

### Operador ternario

```js
let age = prompt('Dime tu edad')

let isAdult = age >= 18 
                ? 'Eres mayot de edad'
                : 'No eres mayor de edad'
                
                /*
                expresionQueDevuelveBoolean
                ? valorSiEsTrue
                : valorSiEsFalse
                */

alert (isAdult)
```

### Operador de cortocircuito

let a
let b=a || 'Juan'

el primer valor viene a ser false ya que es undefined, por lo tanto se muestra el segundo.

let c = null || 25
c 
25

Se salta el null

Evalua, y si el primer valor es false, se queda con ese primer valor, a continuación:

let e = null && a
e

l

En cambio si el primer valor es verdadero, se queda con el siguiente:

let f = 'hola' && 'mundo'

Se queda con el mundo.

### [Numeros](https://ed.team/clase/49/466/2215)

toFixed()
Especifica el número de decimales number.toFixed(n) donde n es la cantidad de decimales. (añade decimales)

También se puede redondear.

### Convertir texto a number

let texto = '20'
let textToNumber = parseInt(texto, 10)

textToNumber
20

Por ejemplo si tenemos un numero con decimales en string y queremos conservar los decimales, entonces tenemos que usar ParseFloat()

Math.floor(20.7) redondea un número hacia abajo = 20

Math.ceil(20.1) hacia arriba redondeo

Math.round(20.1) hacia abajo si es por debajo de 20.5 y hacia arriba si es arriba de 20.5

Math.random() * 10 para obtener numero aleatorio entre 0 y 10.

Math.ceil(Math.random() * 10)  Para obtener un número aleatorio entre 0 y 10.


### Encontrar el indice
let profesor = 'alexys'
profesor.indexOf('s')

### Encontrar el indice de una seguna letra del mismo tipo

'Hola amigos'.indexOf('0',2)

```js
'Hola amigos'.indexOf('o', 'Hola amigos'.indexOf('o') + 1)

```

Hace lo mimo que el método anterior, pero desde el último caracter.

```js
'Hola amigos'.lastIndexOf('o')
```

El siguiente método pregunta si cierta cadena de texto incluye cierto texto:

```js
'https://ed.team/blog'.includes('blog')
true

```
También existen otros métodos para ver si determinado texto comienza con cierto texto:

```js
'https://ed.team/blog'.startsWith('https://ed.team')
// el resultado debe ser true
```
let c = null || 25


### Strings

*Propiedad:* El texto tiene una propiedad. Una propiedad es un valor que tiene un dato, un método es algo que puede hacer una operación.

**.length** devuelve los caracteres de una cadena. en JavaScript se pueden usar literales, por ejemplo : 'alexys'.

### Algunos métodos para stringss.

trim() Quita los espacios en blanco a una cadena.
toUpperCase() Convierte en mayuscula todo.
toLowerCase() Convierte todo en miniscula.


```js
let answer = prompt('¿Cual es la capital del Perú?').toUpperCase().trim()

let message = answer === 'LIMA'
? '¡Correcto!'
: '¡Te equivocaste! La respuesta es Lima'

alert(message)

```

### [Manipular Strings](https://ed.team/clase/49/466/2218)

Remplazar texto:

```js
'Hola mundo'.replace("Hola", 'Holis')

```
O seprar texto:
```js
'Alexys'.split('e')

// O dividir por letras:
'Alexys'.split('')

//Extrae todo el texto desde la posición del carcter seleccionado. 
'Hola mundo'.substring(4)
```
