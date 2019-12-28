# Introducción a CSS


CSS en pocas palabras es un lenguaje que nos ayuda a definir el estilo de como nuestra página HTML va a lucir. 
CSS = Cascading Style Sheets.
Se puede: 
1. Añadir colores a la pàgina
2. Proveer un look atractivo a la página web.
3. Cambia las formas, da bordes a tus elementos.
4. Animar los elementos HTML

**LOS SELECTORES** son simplemente usados para seleccionar el elemento HTML al cual se le quiere dar un estilo. 

**DECLARACIÓN**: Consiste en un set de instrucciones que le dice al navegador como se le va a dar el estilo al elemento HTML seleccionado.

En pocas palabras, los selectores dicen "donde hacer" y las declaraciones dicen el "como o que se va hacer"


### 3 Maneras de agregar CSS al archivo HTML

1. Escribir nuestro CSS dentro de las etiquetas HTML. CSS en línea

!!! hint Dentro de etiqueta
```html
 <p style=”font-size: 24px; color: orange;”>
This is how you write inline CSS.
</p>
```
Esto cambia el color del texto dentro del parrafo y le da un tamaño de 24 px
!!!

!!! caution Anula a los demás por prioridad
Si se incluye un CSS en las 3 maneras teniendo la misma propiedad y selector, entonces esta tendrá la prioridad y sobreescribira los otros CSS.
!!!



2. Escribir este dentro de su archivo HTML, encerrado dentro de < style>< /style> tag... A este se le llama CSS Interno.

!!! hint CSS Interno
```html
 <head>
	<style>
	p{
		color: orange;
		font-size: 24px;
	}
</style>
</head>

```
!!!
3. Escribir este dentro de un archivo externo con extensión .css e incluirlo en el archivo HTML usando el < link> tag - A eso se le llama CSS externo.

!!! hint CSS Externo
```html
 <head>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>
```
**El atributo rel** especifica la relación que vincula el archivo actual con el recurso css.

**El atributo type** especifica el medio y el valor "text/css", el cual transmite que es un CSS.

**href** o hypertext reference es usada para proveer la ruta del archivo que queremos vincular.

En el archivo  **style.css** quedaría:
```css
 p{
	font-size: 24px;
	color: orange
}
```
!!!

!!! caution Usando CSS interno o externo
Si se incluye CSS interno y externo, la precedencia depende del orden en que se especifique dentro de la etiqueta head. En este caso el CSS escrito internamente sobreescribe el css externo y el color cambiará a rojo y su font size a 20px.
```html
 <head>
	<link rel="stylesheet" type="text/css" href="style.css">
	<style>
	p{
		color: red;
		font-size: 20px;
	}
	</style>
</head>
```
!!!

!!! attention NOTA
CSS siempre es leído por los navegadores de arriba a abajo (top to bottom), entonces lo que aparece después anula lo anterior si el selectory la propiedad son iguales.
!!!

### Selección de elementos HTMl

1. Selector de elementos
2. Selector de clase
3. Selector de ID
4. Selector de atributo.

!!! hint Selección de elemento
```html
  <p>Here is some text written inside the paragraph tag.</p>
```
Para simplemnte seleccionar el texto anterior, podemos usar el selector de elementos usando el nombre del elemnto.

Entonces , para seleccionar el texto anterior y modificar su estilo, podemos escribir:
```css
  p{
	/*property value pairs*/ 
}
```
El código anterior va a seleccionar todos los del parrafo presentes en el la página web.

**NOTA:** /**/ es utilizado para encerrar comentarios en CSS. Esto no es leído por el navegador.
!!!

!!! hint Selección de clase
```html
<p class=”select-me”>Here is a paragraph tag which also has a class specified inside it.</p>
```
Si un elemnto HTML tiene una clase asociada con esta, entonces puede ser referenciada usando el selector de clase en CSS.

Escribir un selector de clase implica escribir un . (punto) seguido del nombre de la clase.

```css
 .select-me{
	/*property value pairs*/
}
```
El código de arriba selecciona todos los elmentos contenidos en la clase **select-me**
!!!

### Añadiendo un Background color

La propiedad usada para modificar el fondo es background-color o background, y los valores pueden ser especificados en cualquier formato aprendido.

```css
 body{
	background-color: red;
}
```
o ya sea el siguiente:

```css
 body{
	background-color: #FF0000;
}
```
y por último: 

```css
 body{
	background-color: rgb(255,0,0);
}
```

### Añadiendo un background Image

Se utiliza la propiedad **background** o **background-image** para asignar un fondo con imagen.

```css
background: url(“path to image”);
```

como por ejemplo:
```css
body{
	background: url(“https://www.nasa.gov/sites/default/files/styles/full_width_feature/public/thumbnails/image/pineisland_oli_2017349_lrg.jpg”);
 }
```
Es importante mencionar que también se puede asignar una imagen guardada en la computadora.

Además también podemos modificar el tamaño o medida del background con la propiedad **background-size**, puede contener valores height y width.

La propiedad **contain** se encarga de asegurar que el height y el width del backgroudn image concuerda con el height y el width del content. 

La propiedad **cover** se encarga de asegurar que el height y el width de la imagen abarque todo el width y el height del área disponible. 

Una forma de asignar el background-size se muestra a continuación:

```css
background-size: 100%; 
background-size: cover; 
background-size: contain;
```
### Cambiando el color a un texto:

Para cambiar el color a un texto en CSS, la propiedad de color es usada como se muestra a continuación:

```css
 <p>Hey! Make me blue</p>
//style.css 
p{
	color: blue;
}
```

También podemos cambiar la alineación, los valores pueden ser: center, left, right y justify:

```css
 <p>Hey! I am here.</p>
//style.css 
p{
	text-align: center;
}
```

Para cambiar la fuente, se puede utilizar la propiedad **font-size**. El valor de font-size puede ser asignado con pixels (px), o em.

1em = 16 px

```css
 <p>Hey! Please increase my font-size.</p> 
//style.css
p{
	font-size: 32px;  /*can be specified using em as 2em*/ 
}
```
También tenemos el **font-weight**, la cual es usada para modificar el nivel de negrita de una fuente, o bien el peso (boldness). Los valores van de 100 a 900, de lo más claro a lo más acentuado.

```css
 <p>Hey! Please change my font-weight.</p>
//style.css
p{
	font-weight: 400;  /*can be anything from above values*/
}
```
Cambiar la fuente puede ser posible gracias a la propiedad **font-family**. Por ejemplo, a continuación se cambiara la fuente a 'Roboto', y si esa fuente no es encontrada, se utilizará la sans-serif, porque utiliza un sistema de reserva.

```css
 <p>Hey! Please change my font-family.</p>
//style.css
p{
	font-family:'Roboto', sans-serif;
}
```
### Sobre Height, width, margin y más.

El Height y el width pueden tomar valores en pixeles (px) y porcentaje. Veamos como se hace: 

En pixeles:
```css
 <img src=”img.png” class=”panda”>Wow</div>
//style.css
.panda{
	height: 400px;
	width: 400px;
} 
```
En porcentaje, se cambia al 50% del espacio disponible para la aultura y al 100% del espacio disponible para el ancho.

```css
  .panda{
	height: 50%;
	width: 100%; 
}
} 
```

#### Para añadir bordes...
Se utiliza **border-width**, **border-style** provee variaciones como **dashed**, **solid**, **dotted** y border-color puede tomar cualquier un valor de color valido.
```css
 <div class=”rocket”>The box has margin around it.</div>
//style.css
.rocket{
	border-width: 2px;
	border-style: solid;
	border-color: black;
}
```


!!! hint MÉTODO ABREVIADO

También existe una propiedad abreviada para aplicar el borde:

```css
 .rocket{
	border: 2px solid black; 
}
```
2px es = a border-width, solid es el border-style, y el border-color es negro. 

Si se necesitan bordes curvos, entonces se puede usar la propiedad border-radius.

```css
 .rocket{
	 border: 2px solid black;
	border-radius: 20px; 
}
```
Si se marca su valor en 50%, esto se transformará en un circulo.
!!!

#### Margenes

Creamos los margenes para separar el contenido principal del borde la página.
Para una página wbe, el margen es usado para crear espacio alrededor deleementos fuera del borde.

```css
 <div class=”starlord”>Starlord, who?</div>
.starlord{
	margin-top: 20px;
	margin-right: 30px;
	margin-bottom: 20px;
	margin-left: 30px;
}
```

Hay algún comando corto para los comandos? Si, se muestra a continuación.

```css
 .starlord{
	margin: 20px 30px 20px 30px; /*In order top, right, bottom, left*/ 
}
```
También podemos escribir: 


```css
  .starlord{
	margin: 20px 30px;
}
```

También tenemos la otra opción a continuación que nos permitira´crear un margen de 20 pixeles alreddor de todos los lados. Se muestra a continuación.

```css
  .starlord{
	margin: 20px;
}
```

### Padding

Es usado para crear espacio al rededor de los elemntos, dentro del borde.

```css
 <div class=”starlord”>Starlord, who?</div>
.starlord{
	padding-top: 20px;
	padding-right: 30px;
	padding-bottom: 20px;
	padding-left: 30px;
}
```
El método corto de asignar el padding es: 

```css
 .starlord{
	padding: 20px 30px 20px 30px; /*In order top, right, bottom, left*/ 
}
}
```

### Posiciones

**Posición estatica:** Para una página web, un elemento el cual es posicionado de forma estatica, es posicionado de acuerdo al flujo normal de la página.

Por default la posición de todos los elementos HTML es asignada a estatica.

En el documento HTML:
```html
<div class=”static-me”>I am not special.</div>
```
En el documento CSS:
```css

.static-me{
	position: static;
}
```

**Posición relativa**: Nos permite posicionar el elemento en relación a sí mismo. Es decir, el elemnto cambiará de posición en relación con su posición predeterminada.

Documento HTML:

```html
<div class=”relative-me”>What does this even mean? Look up.</div> 
```
En el documento CSS:
```css
.relative-me{
	position: relative;
	top: 10px;
}
```
El top moverá el div 10 px hacia la parte inferior de donde hubiera estado por defecto.

!!! attention NOTA
Top, left, right, bottom son usados con la posición para especiicar la distancia desde los ejes respectivos.
!!!

**Posición fija:** (Fixed Position) Nos permite posicionar el elemento en relación con la pantalla. Si al elemento le es dada una posición fija, esta va ocupar esa posición en la pantalla.

```html
 <div class=”fixed-me”>I get attached soon.</div>
```
En el documento CSS:
```css
.fixed-me{
	position: fixed;
	top: 50px;
	left: 50px;
}
```
Esta se movera 50px hacia el bottom y 50 px hacia el right desde su posición original y permanecerá fijo ahí.

Los elementos fijados permaneceran en el mismo lugar de la pantalla incluso si el usuario scrollea.

**Posición Absoluta:**  Permite posicionar el elemento exactamenre donde nosotros queremos. Podemos usar top, right, bottom, left para colocar el elemento donde queramos. 

Documento HTML:

```html
 <div class=”absolute-me”>I am the best thing you have in store.</div> 
```
En el documento CSS:
```css
.absolute-me{
	position: absolute;
	top: 50px;
	left: 50px;
}
```

### Manipulación de propiedades de visualización

La propiedad de visualización en CSS se utiliza para controlar el comportamiento de representación predeterminado de un elemento. 

Los elemntos tienn un comportamiento de representación predeterminado diferente, por ejemplo:

< p> y < div> son elementos de bloque, mientras que < a> y < span> son elementos en linea.

**Display block**: Un elemnto que tiene la propiedad de visualización establecida bloqueda, se muestra en una nueva línea y se extiende por todo el ancho.


Documento HTML:

```html
<span class=”block-me”>I need space.</span>
```
En el documento style.css:
```css
 .block-me{
		display:block;
 } 
```

El fragmento de código anterior cambiará el comportamiento de visualización de  < span> para bloquear.
**NOTA:** < span> es un elemnto en línea por defecto.

#### **inline-block**:
Establecer este tipo de comportamiento de visualización nos permite establecer la altura y el ancho del elemento, además permite ocupar varios elementos en una fila.

Documento HTML:

```html
 <div class=”inline-me”>Hey, I wish we were together.</div>
<div class=”inline-you”>What’s stopping you?</div>
```
En el documento style.css:
```css
.inline-me, inline-you{
	display: inline-block;
	height: 20px; 
	width: 50%;
}
```
El fragmento anterior hará que los divs estén en línea, donde cada uno tomará el 50% del ancho del contenedor y la salida será similar a la que se muestra en la imagen de arriba. 

**NOTA:** div ES  un elemnto de bloque por default.

*La diferencia entre inline-block y block display es que en inline-block se pueden añadir multiples elemntos en una fila, además se puede añadir ancho y altura a la clase.*

#### None 
El valor de visualización onne es usado para eliminar el elemento.

Documento HTML:

```html
<div class=”not-me”>I didn’t do anything.</div>
```
En el documento style.css:
```css
 .not-me{
	display: none; 
}
```

### Propiedad de desbordamiento (Overflow)

Esta propiedad de desbordamiento en CSS, se usa para especificar qué sucede si el contenido va más allá del contexto o área de contenido.

Existen 2 opciones: **Recortar el contenido desbordado**

- Para recortar el contenido desbordado, el valor oculto se pasa a la propiedad de desbordamiento. Esto hará que el contenido desbordado sea invisible.

Documento HTML:

```html
<div class=”trimmed”>I know I am going to get slashed from bottom but it’s fine. Someone will save me. Hopes intact.</div>
```
En el documento style.css:
```css
 .trimmed{
	height: 20px;
	width: 400px;
	overflow: hidden;
} 
```
El fragmento anteriro de código tendrá la siguiente salida:

_I know I am going to get slashed from bottom but it’s fine_

La altura y el ancho del div es asignado para ser de 20px y 400 px respectivamente, entonces el contenido se desbordado, se le asigna un valor oculto, entonces se recorta. 

### Añadir Scrollbars

Para mostrar el contenido desbordado podemos configurar la propiedad de visualización para desplazarse.

```html
<div class=”scroll”>I knew you would save me. Let’s show the world what we are made of.</div>
```
En el documento style.css:
```css
.scroll{
	height: 50px;
	width: 200px;
	overflow: scroll; 
} 
```
**La salida es la siguiente:** Aparecen barras de desplazamiento al rededor del div y el  contenido se puede ver al desplazarse.


### Desbordamiento auto

Detecta automáticamente si el contenido se recorta y agrega barra desplazamiento si es necesario, y solo a lo largo del eje donde se requiere.

```html
<div class=”auto-me”>I knew you would save me. Let’s show the world what we are made of</div>
```
En el documento style.css:
```css
.auto-me{
	height: 40px;
	width: 200px;
	overflow: auto; 
}
```
**La salida:**

La barra de desplazamiento aparece desde que el contenido se está recortando, tambiñen solo aparece la barra de desplazamiento vertical.

### Desbordamiento visible

Esto no se recomienda, pero básicamente si se configura el desbordamiento visible, hará que el contenido se procese incluso si sale del contenedor. Por lo cual hay que tener cuidado , porque este es el comportamiento por default.

```html
<div class=”visible-me”>I knew you would save me. Let’s show the world what we are made of</div>
```
En el documento style.css:
```css
.visible-me{
	height: 40px;
	width: 200px;
	overflow: visible;
	border: 1px solid #000;
 }
```

### Pseudo clases 

Un elemento puede tener multiples estados, estos estados pueden ser cualquiera como, hovered, focused, visited.
Para cambiar las propiedades de los elementos en estos estados podemos tener pseudo classes.

Las pseudo clases son escritas de la siguiente manera:

```css
 selector:pseudo-class{
	  property: value; 
}
```
#### Cambiar las propiedades del elemento al pasar el mouse sobre

Has notado alguna vez que el texto se enfoca cuando pasa el mouse sobre él. 
Con el mismo propósito, utilizamos el desplazamiento de pseudoclase **hover **para seleccionar elmentos cuando cuando el mouse esta encima de ellos.

```html
 <input class=”hover-me” type=”button” value=”Hover” />
```
En el documento style.css:
```css
 .hover-me:hover{
	background-color: green; 
}
```
Cualquier propiedad yvalor que se otorgue a la pseudo clase jover, se aplicará solo cuando el elemento este "hovered" (o cuando el mouse este encima del elemento)

```html
 <input class=”hover-me” type=”button” value=”Hover” />
```
En el documento style.css:
```css
 .hover-me:hover{
	background-color: green; 
}
```
En la siguiente imagen se mostrará la salida:


#### Cambiando propiedades de un elemento activo

Para cambiar las propiedades de un link activo, la active pseudo class es usad. Un link esta en estado activo cuando es clickeado.

```html
 <a href=”www.anywebsiteyoulike.com”>Click me</a>
```
En el documento style.css:
```css
 a:active{
	color: red; 
}
```
Podemos ver en la imagen la salida de lo anterior:



#### Cambiando las propiedades de un link no visitado.

Para cambiar las propiedades de los links que todavía no han sido visitados, **link** pseudo class es utilizado.

```html
 <a href=”www.anywebsiteyoulike.com”>Don’t click me</a>
```
En el documento style.css:
```css
 a:link{
	color: red; 
}
```
El trozo de código anterior resulta en:


una vez el link es visitado, esta pierde las propiedades aplicadas usando :link class. 

### Escribiendo CSS para móviles.

Es una necesidad asegurarnos que el desarrollo de aplicaciones sea compatible entre todos los dispositivos. Para ello, son importantes los **Media queries**. Al usar media queries, podemos escribir estilos basados en tamaños de pentalla, especificamente para tablets, celulares y escritorio.

Para escribir los **media** queries @media property es usada.

Es escrita a continuación:
```css
@media screen and (condition) {
	//Whatever CSS you want to write 
}
```
Aquí la condición consiste en condiciones que involucran altura y ancho de la pantalla.Dentro de este block, podemos escribir cualquier CSS especifico para alguna pantalla.

Para escribir CSS para los tamñaos de pentalla más anchos o iguales a 720 px, podemos escribir:

```css
@media screen and (min-width: 720px){
	p{
		font-size: 16px;
	}
}
```
El CSS anterior cambiará el font-size de cada parrafo para 16 px en dispositovos con pantala de 720 px o màs que 720 px.
Similarmente, **max-width** puede ser usado para especificar propiedades especificamente para tamaños de pantalla iguales o menores que la especificada. En el mismo ambito, también se pueden usar max-height y min-height. 

Dar una condición de ancho máximo asegurará que el CSS se aplique a los dispositvos que tienen un ancho de pentalla igual o menor al especificado.








