# Introducción a JavaScript y JavaScript Avanzado - Resumen.

JavaScript es un lenguaje de programción utilizado para hacer páginas web interactivas.

JavaScript es como el oxigeno, da vida a las páginas web. Es responsable de todas las animaciones que nos mantiene dentro de una página web entretenidos.

Si has utilizado una cuadro de busqueda o Search box, para buscar tu meme favorito, o vio un video de Mr. Bean o comprobó un puntaje de cricket en vivo , probablemnte JavaScript lo esta ejecutando.

JavaScript es el lenguaje más universal en el mundo, y la belleza de este es que usted puede construir casi cualquier cosa con este.

Se pueden hacer:

- Páginas web interactivas
- Aplicaciones moviles.
- iOS y aplicaciones Android
- También se utiliza para construir aplicaciones de escritorio completas

Es usado por Google, Facebook, Microsoft, Uber y muchas otras compañias.

Las variables son declaradas con la palabra reservada "var", seguidamente del signo "=" y el valor.
```js
 var x = “Programming Hub” ;
document.write(x) ;
```

Hay 3 tipos de Dialog Boxes en JavaScript

- Alert Dialog Box
- Prompt Dialog Box
- Confirm Dialog Box

En JavaScript hay dos tipos de Scope

- Local Scope: Las variables utilizadas dentro de una función solo pueden ser utilizadas en esa función.
- 
- Global Scope

En JavaScript, todas las declaraciones de variable son movidas a la parte superior de su alcance. Esto se conoce como **hoisting**

En JavaScript, una varianle puede ser usada antes de que esta es declarada.

### Accediendo a elementos del DOM

Aprendimos que el documento es la raíz del nodo. Por lo tanto, para acceder a cualquiera de los nodos sigueintes, primero debemos acceder al nodo del documento. Existen tres maneras en las cuales podemos acceder a los nodos. Para ello existen tres identificadores en los cuales estos nodos pueden ser identificados:

1. Tag name - El nombre de la etiqueta o tag.
2. Class - Las clases adjuntas a los nodos/elementos.
3. Id - El id asignado a los nodos/elementos.

Entonces, podemos acceder a los elementos:
1. Por su nombre
2. Por las clases adjuntas a ellos.
3. Por el ID asignado a ellos.

Hay ciertos metodos que pueden ser usados para acceder a los elementos con los identificadores mencionados:
1. **getElementsByTagName()** - Para buscr los elementos usando el tag name.
2. **getElementsByClassName()** - Para buscar los elementos usando la clase asignada al elemento
3. **getElementById()**- Para buscar el elemento usando el id asignado a este.

Entonces, supongamos que queremos acceder a todos los etiquetas de parrafos presentes en la página web. Simplemente tenemos que escribir:

**document.getElementsByTagName("p");**

También, para acceder a los ementos usando la clase presente en el elemento, podemos usar: 

**getElementsByClassName()**

Para acceder a la etiqueta de parrafo con una clase "newClass", podemos escribir:

document.getElementsByClassName('newClass');

Esto, seleccionará todos los elementos contenidos en la clase newClass.

Para acceder a los ementos usando el ID presente en el elemnto, se usa el método **getElementById()**.

Podemos acceder a la etiqueta < p> con el id que le fue asignado, el cual es "newId".

```html
<p id="newID"> Are you trying to access me using the id</p>
```

### Accediendo a los elementos HTML con selectores CSS

Los selectores de CSS son usados para seleccionar los elementos a los que usted quiere darle un estilo, los cuales pueden ser id, nombres de clase, tipos, atributos, valores de atributos y etc.

Tenemos dos métodos que pueden ser usadoa para acceder a los elementos HTMl basado en selectores especificos de CSS.

1. **querySelector()** este método retorna solo el primer elemento que coincide con selector especificado
2. **querySelctorAll()** mientras que este método retorna todos los elementos que coinciden.

Usar querySelector es un enfoque moderno para acceder a elementos DOM. Este método toma un selector como parámetro y devuelve los elementos respectivos.

 document.querySelector(“.className”);	//to access using class
 document.querySelector(“#idName”);	//to access using id
 document.querySelector(“tagName”);	//to access using tag name

### Escribiendo contenido HTMl

JavaScript provee una propiedad llamada innerHTML, la cual puede ser usada para asignar contenidos de HTML. Obviamente lo primero que necesitamos es acceder al elemento, una vez hecho esto podemos hacer uso de la propiedad. Como se muestra a continuación:
```js
document.getElementById("lone-p").innerHTML = "Here is some text for you!";
```
Qué pasa si ya tiene texto presente en el elemento p? Entonces escribe:

```js
 document.getElementById(“not-alone”).innerHTML = “Replaced you!”;
```
Lo anterior sobrescribirá el texto presente y lo reemplazará con el nuevo valor.

También podemos añadir etiquetas HTML escribiendo las etiquetas dentro de los valores de la propiedad innerHTMl. Por ejemplo, tenemos el siguiente elemento:
```html
 <-- This will declare a paragraph with id name -->
<p id= “bold-me”></p>
```
Queremos escribir un texto en negrita dentro del mencionado elemento p. Entonces lo podemos hacer de la siguiente forma:
```js
 <-- This will access the paragraph and store the content with bold text -->
document.getElementById(“bold-me”).innerHTML = “<b>Just like this</b>”;
```

### Creando elementos HTML 

Para crear elementos usamos el método **document.createElement("p");**

#### Elementos anexos

Considere que tiene que insertar un elemento p dentro de un div existente.

Sabemos como crear un nuevo elemento, pero también necesitamos insertarlo dentro del DOM. 

```js
 <-- Esto crea un nuevo elemnto y lo guarda en una variable -->
var newEl = document.createElement("p");
<-- Esto crea un texto para el elemnto nuevo y lo guarda en una variable -->
var someText = document.createTextNode("Some Text Here!");
<-- Esto inserta el texto dentro del elemento p recien creado y lo guarda en una variable -->
var insertThis = newEl.appendChild(someText);
<-- Esto insertará el elemento guardado anteriormente, en el div -->
document.getElementById("meDiv").appendChild(insertThis);
```
#### Remover un elemento

Consideremos el siguiente trozo de código HTML:

```html
 <-- This will create a division with Id name -->
<div id=”thisDiv”>
	<-- This will create a paragraph with Id name and print the text -->
	<p id=”thisP”>
		Hehe! I am going to die.
	</p>
</div>
```
Deseamos remover el elemento p presente dentro del div

Entonces tenmeos que hacer uso de **removeChild()**, para ello tenemos que obtener tanto el div como el elemento p, para poder hacer uso del método. Tal como se muestra a continuación:

```js
  <-- This will access the division with specific ID name-->
var divEl = document.getElementById(“thisDiv”);
<-- This will access the paragraph element -->
var pEl = document.getElementById(“thisP”);
<-- This will remove paragraph element from division -->
divEl.removeChild(pEl);
```

### Asignando un atributo

Además, también podemos asignar un atributo a un elemento con su respectivo valor, esto se puede lograr usando el método setAttribute().

Este método ocupa dos parametros: nombre del atributo y su valor:

```js
 setAttribute(“attribute”,”value”);
```
Podemos ver el ejemplo de la implementación completa en el siguiente trozo de código:

```js
 <-- This will create a link with given text -->
<a>Google</a>
 <-- This will access the anchor element -->
var aEl = document.querySelector("a");
<-- This will set a href attribute in the <a> tag -->
aEl.setAttribute("href","http://google.com");
```
Del mismo modo, podemos también remover atributos, en este caso se hace con el método **removeAttribute()**

Por ejemplo tenemos lo siguiente:

```html
<a href=”http://google.com”>Google</a>
```
Si queremos eliminar el atributo href, hacemos lo siguiente que es similar a pasos anteriores:

```js
 document.querySelector(“a”).removeAttribute(“href”);
```

## Manipulando CSS con JavaScript

Podemos añadir CSS styles o cambiar cualquier elemento existente. Para hacerlo usamos la propiedad de style del elemento.

La sintaxis es la siguiente:

```js
 el.style.CSSProperty = value;
```

Donde **el** es el elemento, **style** es la propiedad del elemento, **CSSProperty** es la propiedad para ser manipulada, y el **value** es el valor de la propiedad.

Pero para cambiar las propiedades del elemento, primero debemos de acceder a él.

```html
<p>Here I come, again.</p>
```
Entonces, veamos como podemos cambiar el **font-size** del texto en la etiqueta p.

```js
<-- This will access the paragraph element -->
var el = document.querySelector(“p”);
<-- This will make paragraph font-  size 25px -->
el.style.fontSize = “25px”;
```
De igual modo, si tuviesemos que cambiar el color del texto:

```js
 el.style.color = “green”;
```
También podemos hacer el texto invisible haciendolo oculto modificando la propiedad:
```js
 el.style.display = “none”;
```
Además podemos cambiar el background color de un texto:
```js
el.style.background = “red”;
```
Con lineas similares, también vamos a poder cambiar el margin, padding, border, change alignment, etc.

### Eventos en JavaScript

Los eventos se pueden escribir de dos formas
Supongamos que existe un evento al que le queremos asignar un evento onClick:

```html
 <button onclick="alert('Oh! Clicked.')">Click me</button>
```

Aquí, nostoros definimos la acción que se necesita realizar dentro del atributo OnClick del boton en si. Por lo tanto, una alerta aparecerá cuando el botón es presionado.

La otra manera es llamr una función que se define en otra parte del programa cuando se hace click en el botón. Este enfoque se utiliza cuando las funciones son complejas y también estructura el código HTML y el código JavaScript por separado.

```js
  function clicked(){
	alert('Oh! Clicked.'); 
}
```

También existe otra manera que permite añadir eventos a los elementos HTML en vez de escribirlos directamente dentro del elemento.Esto, a través de la función **addEventListener()**, podemos añadir eventos a los elementos HTMl.
En html:
```html
 <button>Click Me</button>
```
En JavaScript:
```js
 <-- This will access the button element -->
var myBtn = document.querySelector(“button”);
<-- This will add an event using proper method -->
myBtn.addEventListener(‘click’,function(){
	alert(“Oh! Clicked.”);
});
```

También se utiliza un método para eliminar el evento llamado: **removeEventListenr()**:--- also takes two arguments, the event to remove and the function to perform when the event is removed.

```js
 <-- This will access the button element -->
var myBtn = document.querySelector(“button”);
<-- This will remove an event   using proper method -->
myBtn.removeEventListener(‘click’);
```

### BOM - Browser Object Model

Este le permite a JavaScript inteactuar con el navegador.Consiste en un objeto conocido como ventan

El **Window object** guarda la información sobre el tamaño de la ventana del navegador del usuario. Podemos averiguar la altura y el ancho de la ventana del navegador. 

Para hacer lo anterior, utilizamos las propiedades innerHeight e innerWidth del objeto de la ventana.

**window.innerHeight** retorna el **innerHeight** de la ventana del navegador.

**window.innerWidth** retorna el **innerWidth**  de la ventan del navegador.
Estos valores se devuelven en pixeles- Esto incluye la barra de herramientas y la barra de desplazamiento durante el cálculo. Solo se considera la parte de visualización del navegador. 

**El screen object** contiene la información sobre la pantalla del usuario. Para acceder al screen object podemos escribir:

```js
window.screen
```
Podemos obtener el height, width, color depth, pixel depth y muchas cosas más usando el screen object.

Para encontrar la altura y el ancho de la pantalla, podemos simplemente usar:
- **screen.height y screen.width** respectivamente.
- 

#### El objeto de historia (The History Object)

Este objeto nos da acceso al historial del navegador, el cual viene a ser interesante a la hora de manipularlo.

Podemos navegar de un lado a otro utilizando el history object. Este objeto provee 2 métodos:
**back() y forward()**... También **history.back()** es lo mismo que presionar el botón volver en el navegador. Todo lo contrario lo hace **history.forward()**, pues nos dirige hacia adelante. 

Tenemos otro objeto bastante útil, el cual se llama **location object**, podemos obtener detalles sobre el URL, hostname, protocolo.

- **window.location.href** retorna la URL de la página actual
- **window.location.hostname** retorna el dominio del sitio web.
- **window.location.protocol** retorna el protocolo del sitio web.

El objeto navegador, es usado para detectar la información del navegador, tal como appName, appVersion etc.

1. appName - retorna el nombre
2. appVersion - retorna la versión
3. cookieEnabled - retorna true si los cookies estan activados, de lo contrario retorna falso.
4. online - retorna verdadero si el navegador esta en linea, de lo contrario retorna falso.

#### Cookies en JavaScript

Nos permite guardar datos en el navegador de usuario. El Cookie es un dato que se almacena en el navegador del usuario.
Pero.. Por qué necesitamos guardar datos en el navegador?
Es bastante útil cuando queremos recordar información sobre el usaurio, pero qué tipo de información?
Por ejemplo, recordar tu nombre de usuario en un sitio web particular, entonces cunado visites el mismo sitio web de nuevo, no necesitarás escribirlo de nuevo.
O almacenar variables de sesión, las cuales son usadas para mantenr el login de sesión entre diferentes páginas. **JavaScript puede leer, crear, modificar y eliminar cookies**, veamos como:

#### Creando un cookie

Un cookie puede ser creado usando la propiedad de cookies de nuestro propio document object. Para crear un cookie, la sintaxis es la siguiente:

```js
 document.cookie = “key=value;”;
```
Donde key es el nombre del cookie y value el valor del cookie. Para crear multiples cookie, simplemente utilizamos el comando anterior de forma repetida.

```js
 document.cookie = “key1=value1”;
document.cookie = “key2=value2”;
```
Los cookies tiene una fecha de expiración, no son permanentes.

Por default, el cookie es eliminado cuando el navegador se cierra, pero también podemos especificar el tiempo manualmente. Esto se hace usando un campo adicional cuando se crean los cookies:

```js
 document.cookie = “key:value;
expires:Date”;
```
El expires toma una fecha como valor.

#### Leyendo los cookies que estan activos

```js
var myCook = document.cookie;
```
Lo de arriba guardara un string conteniendo toda la información de los cookies en la variable myCook que estará en el mismo formato key-value. 

Además, podemos cambiar el valor de un cookie del mismo modo que lo creamos:

```js
document.cookie = "username=Rahul Saxena; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";
```

El cookie viejo es remplazado con el nuevo. 

También podemos eliminar cookies existentes, del siguiente modo:

```js
 document.cookie = “key=;
expires= Past_date;”;
```
Cuando key es el nombre del cookie que se va a eliminar. No hay necesidad de especificar el valor cuando se va a eliminar un cookie.

## ES6 

Antes de ES6, las variables eran declaradas usando var. Las variables usando var tienen un alcance de función.

En ES6, podemos declarar variables usando **let** y **const**.

let es lo mismo que var, excepto que tiene un alcance de bloque, a diferencia de var.


Cuando aprendimos sobre el alcance de las variables, vimos que una variable declarada dentro de una función usando **var** no esta disponible afuera de la función. Pero una variable dentro de un "block scope" usando **var** aún permanece dispinible afuera del bloque.

Por ejemplo:

```js
 for(var count=0; count<5; count++) 
 {//some action }
 console.log(count);
```
Vemos que la varible va a estar disponible afuera del block scope, y su valor será 5.

Es aquí donde entra el **let**, pues aveces no necesitamos que el valor se encuentre accesible después del bloque. Por ejemplo, si escribimos:

```js
 for( let count=0; count<5; count++) 
 {//some action } console.log(count);
```
Nos dará reference error, pues no se tiene acceso.

#### Uso del const

Funciona exactamente como let, pero el valor de la variable declarada usando const sigue siendo el mismo en todo el programa.

Se recomienda evitar el uso de var y usar bloques de ámbito let y const.

#### Arrow functions

Recuerda como se escribian las funciones en JavaScript?
```js
 <-- This defines a function -->
function nameOfFunction(){
	<-- This is function body -->
}
```

En ES6 se introdujo una forma abreviada y eficiente de hacer lo mismo, lo que se conoce como función flecha o arrow en inglés.


```js
 <-- This defines an Arrow function using Fat arrow-->(parameters) => {
	<-- This is function body -->
}
```

También podemos ignorar el uso de llaves si el cuerpo de la función se limita a una declaración:

```js
(parameters) => statement; 
}
```
Además, podemos asignar la función a una variable, por lo que la referencia de la función se almacenará en esa variable:

```js
 let varName = (parameters) => {
	<-- This is function body -->
};
```
Se debe comenzar a reemplazar por este nuevo método. 

### Template Strings

Es una tarea tediosa romper cadenas utilizando el operador "+" para concatenar variables. ES6 brinda la solución en la forma de **Template Strings**. Para escribir template strings, se usa los backticks (` ` ) en vez de comillas simple o dobles.

```js
 let str = `Hey! String me.`;
```
Podemos ver un ejemplo donde se aplica:

```js
 <-- Declares a variable and assign an integer value -->
let a = 5;
<-- Declares another variable and assign a template   string value -->
let str1 = `I am ${a} years old.`;
```

Por ende, podemos ver que la salida de str1 será: **I am 5 years old**, sin la necesidad de concatenar con +

### Clases en JavaScript

En ES6 se introducieron las clases a JavaScript. La sintaxis de clase recienetemente introdcida es solo una sintaxis actualizada del JavaScript existente basado únicamente en objetos.
Como JavaScript no tenía clases explíctias, se logró lo mismo usando los objetos.

Las clases en JavaScript son tipos de funciones màs o menos especiales. Las clases son variables y métodos agrupados. Los métodos no son más que las funciones declaradas dentro de una clase. Los miemboros en una clase pueden ser accesados creando una instancia de la clase. Estas instancias de la clase no más y nada menos que los objetos.

#### Escribiendo una clase

```js
 class className{
	<-- This is class body -->
}
```
Otra manera es: 
```js
 <-- Declare a class without name and store in a variable -->
var varName = class{
	<-- This is class body -->
};
```
Las pueden ser nombras o no:

```js
 <-- Declare a class with a name and store in a variable -->
var varName = class className{
	<-- This is class body -->  
};
```
El método constructor es un metodo especial en una clase, pues es usado para crear e inicializar los objetos creados dentro de su clase, y puede existir solo un método constructor en una clase. Por ejemplo:

```js
 <-- This defines a class -->
class Student{
	<-- This defines a constructor for the class -->
	constructor(name,   roll_no){
		<-- This initialises the variables -->
		this.name = name;
		this.roll_no = roll_no;
			}

	<--   This defines a method of the class -->
	showName(){	
			<-- This is a method to return name -->
			return   name;
	}
	<-- This defines another method of the class -->
	showRoll(){
		<-- This is a method to return roll_no   -->
		return roll_no;
	}
}
```
La clase anterior simplemente toma el nombre y el roll number del estudiante y los retorna.

### Accediendo a miembros de la clase:

Los miembros de una clase pueden ser accesados creando la instancia de una clase.
Los objetos son usados para acceder y asignar valores a las variables.


```js
 let objName = new ClassName(); 
```

Veamos una instancia de clase estudiante:


```js
 <-- This defines a class -->
class Student{
	<-- This defines a constructor for the class -->
	constructor(name,   roll_no){
		<-- This initialises the variables -->
		this.name = name;
		this.roll_no = roll_no;
			}

	<--   This defines a method of the class -->
	showName(){	
			<-- This is a method to return name -->
			return   name;
	}
	<-- This defines another method of the class -->
	showRoll(){
		<-- This is a method to return roll_no   -->
		return roll_no;
	}
}

<-- This creates an instance of defined class with parameters -->
let student1 = new   Student(“Rahul”,45);
```

Eso es todo, de este mod opodemos llamar la función showName() y showRoll() desde una instancia:

```js
 <-- This calls 1st method using instance variable -->
student1.showName();
<-- This calls 2nd method using instance variable -->
student1.showRoll();
```

