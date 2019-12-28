# Resumen del curso básico de HTML

## Sobre los tags
### El < img/>
Podemos hacer las páginas web más interactivas, añadiendo <img/> como tag. 

Se ubica dentro del body tag.
```html
<img src= "image's path"/> 
```
src es un atributo para incluir la ruta de la imagen, la cual también puede contener un URL.
Un atributo provee información adicional sobre tu tag html.
```html
 <body>
	<img src="www.google.com/images/KungFuPanda.png"/>
</body> 
```
Pero, para mayor simplicidad, también podemos guardar las imagenes en la misma carpeta, y lo podemos intentar de este modo:
```html
 <body>
	<img src="GrumpyPanda.png"/>
	<p>I ain't angry :/ </p>
</body>
```
### El < div> Tag

Este se ubica dentro del body tag. Y permite dividir la página en secciones.

```html
 <body>
	Can I meet my other half? Please. 
	<div>
	<p>Don't worry, I'll meet you soon</p>
	</div>
</body>
```
### El < title> < /title> tag

Se ubica dentro del head tag. Además no se visibiliza en la página principal, pero permite dar instrucciones especiales al navegador.

```html
 <head>
<title>Can you see me?</title>
</head>
```
Viene a ser bien útil para los motores de busqueda.

### Etiqueta de anclaje < a> < /a>

Del mismo modo, para insertar enlaces de otras páginas web, se utiliza una etiqueta de anclaje. Se ubica en el body tag. Es un vínculo entre páginas web.

```html
 <body>
	<a href=”https://programminghub.io>
  I think you should try clicking this</a>
</body>
```
**href** es otro atributo utilizado para definir el link. Además sirve tanto para referenciar páginas web, como documentos.

**El atributo src** permite proveer la ruta de la imagen en una página web. Instruye al navegador donde buscar por la imagen.

## Atributos

Un atributo solo brinda información extra sobre el elemento HTML al navegador. Puede ser una propiedad relacionada con el **width**, **height o el color de un objeto.**

El atributo se compone de 2 partes:
1. Nombre del atributo.
2. Valor del atributo.
2.1 attribute=”value”

Se puede definir el width, height etc. para una imagen usando estos atributos:

alt: Define el texto o nombre de una imagen. Solo en caso de que este no pueda ser desplegado.

**width:** Es un atributo opcional para asignar el ancho de la imagen. 
**height:** Es un atributo opcional para asignar la altura de una imagen. 

```html
<img src="image.png" width="200" height="400"/>
```

En caso de que la imagen no pueda ser desplegada.
```html
 <img width="200" height="400" alt="Hey People, Good Day"/>
```

### Atributos de estilo

El atributo de style hace el retoque final de los elementos HTML. Permite cambiar o agregarle diferentes estilos. Puede ser en forma de color de fondo, tamaño, etc.

**style="property:value"**
La propiedad implica color básico, o incluso el font-size brinda la propiedad a un elemento.

```html
 <h4 style="color:green">Can we change this to red please?</h4>
<p style="font-size:200%">No Green looks better</p>
```
PS: Es un atributo genrico que puede ser usado con cualquier etiqueta HTML. 

#### Cambiar el background-color cambia el fondo de un texto

```html
<h1 style=”background-color:orange”>Try typing your name here</h1>
```

## HTML5

Las nuevas actualizaciones generalmente conducen a un mejor y mejor funcionamiento de una aplicación

Fue diseñado para brindar un soporte multimedia rico y mejorado. Además permite desarrollar aplicaciones web complejas.

Fueron agregados nuevos elementos y las etiquetas son más interactivas.

La estructura básica sigue siendo la misma con algunos cambios minimos.

Cross platform signica desarrollo de aplicaciones para multiples dispositivos.

Algunas de las etiquetas especiales añadidas, fueron para permitir agregar audio y video en la página web.

### Diferencias entre HTML y HTML5

La primera diferencia que podemos notar es la declaración Doctype.

denotada como: < !DOCTYPE html>... Esta declaración le dice al navegador en cual version de HTML la página fue codificada. No es una etiqueta y siempre va en la primera linea del documento HTML.

A diferencia de HTML, HTML5 tiene contiene elementos specificos como < header>, < footer>, < section> etc. 

En HTML5 fue agregada la GeoLocation, es decir, podemos averiguar la localización del visitante a nuestra página. Se una API de geolocalización.

**Localización para todo:** ubicado dentro del < body>

**El < header> & < /header>** contiene la parte introductoria de la página. Además se pueden añadir imagenes, logo y etiquetas  < h1>..< h6> 

**El < footer> & < /footer>** se pueden añadir los detalles como informacion de Copyright , contacto y entre otras cosas.

**El < nav> & < /nav>** van ubicados cosas como links, profile, mi cuenta entre otros.

** El< article> & < /article>** tiene un lugar dedicado para si mismo en la pagina web. Puede ser utilizado para un blog o caja de comentario. etc Viene a ser como un reemplazo del div.
