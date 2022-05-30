# Guía de estilos

Lo importante al escribir una hoja de estilo es seguir siempre los mismos criterios, para que sea más fácil detectar errores o poder reutilizarla en otros proyectos. En la mayoría de los casos, esto no supone ningún problema mientras una persona trabaje sola en un proyecto. Sin embargo, en el caso de proyectos web de mayor envergadura, son varios equipos los que se encargan de la edición, desarrollo y mantenimiento de la página web. La solución en dichos entornos de trabajo se plantea en forma de guía de estilo que permite escribir código más limpio.

## ¿Qué es?

Las guías de estilo hacen referencia, en el ámbito del desarrollo web, a los manuales para la elaboración de un diseño uniforme en cada aplicación. Las guías de estilo CSS resultan necesarias para presentar el trabajo realizado por los distintos equipos de desarrollo como una única unidad. Este tipo de manuales ofrecen directrices acerca de cómo se tiene codificar para poder ofrecer un desarrollo mantenible.

## Principios

-	Mantener un **código limpio** y poder reusarlo lo máximo posible
-	Implementar un código que luzca como si lo hubiera escrito una **única persona**
-	Codificar para mayor **escalabilidad y visibilidad**

## Arquitectura

La arquitectura usada para organizar las carpetas del código fuente de los estilos CSS será **La regla del 7+1**. Esta arquitectura también es conocida como patrón 7–1. Consiste en tener todas las hojas de estilo organizadas en 7 carpetas y un único archivo en la raíz para importarlas. A continuación se muestra la estructura jerárquica:

```
scss/				
|- style.scss			
|
|- base/			
|  |- _global.scss 
|  |- _reset.scss 
|  |- _tipografia.scss 
|  
|- components/			
|  |- _buttons.scss 
|  |- _texts.scss 
|  
|- layouts/			
|  |- _footer.scss 
|  |- _header.scss 
|  
|- themes/			
|  |- _admin.scss 
|  |- _theme.scss 
|  
|- utils/			
|  |- _extends.scss 
|  |- _funciones.scss 
|  |- _mixins.scss 
|  |- _variables.scss 
|  
|- views/			
|  |- _home.scss 
|  
|- vendors/ 
 
```

-	`scss`  Este directorio contiene el código fuente de todos los estilos de aplicación agrupados en *partials* (pequeños archivos que dividen la hoja de estilos), para que posteriormente sean mapeados y procesados a una única hoja de estilo interpretada por los navegadores.
-	`base`  Contiene el código base del proyecto como las reglas de tipografía o los resets necesarios para sobrescribir las reglas por defecto de los navegadores.
-	`components`  Contiene los estilos de los distintos componentes que emplearemos dentro de nuestra aplicación como pueden ser botones,  sliders, carruseles… 
Separar cada componente en su propio archivo nos permitirá reutilizarlos en otros proyectos.
-	`layouts`  En esta carpeta aparecen los estilos relacionados con la estructura de la aplicación, como los estilos de la cabecera o el pie de página.
-	`themes`  Almacena los estilos referidos a diferentes themes que pueda adoptar nuestro proyecto en función, por ejemplo, del tipo de usuario o la sección que esté visualizándose. 
-	`utils`  En esta carpeta se encuentran las funciones, variables y mixins empleados en el resto de ficheros. Estos archivos no generan ninguna regla CSS al ser compilados sino que añaden funcionalidad extra para ser empleada por los otros partials.
-	`views`  Contiene los estilos específicos para determinadas vistas (páginas) de la aplicación como puede ser la página de inicio o la de login.
-	`vendors`  Contiene librerías de terceros.

Cabe destacar que el archivo `style.scss` situado en la raíz de la carpeta de desarrollo, importará todos los estilos (*partials*) alojados en dicha carpeta.

## Metodología

La metodología usada para la codificación de las hojas de estilo de la aplicación se llama **BEM**. Esta metodología divide la interfaz de usuario en bloques independientes para crear componentes escalables y reutilizables. Con BEM modularizamos lo máximo posible cada uno de los bloques de código dispuesto. Se centra en tres parámetros o variables posibles: 

-	Bloques
```html
<section>
	<article class="noticia"> 
		<!-- Bloque contenedor -->
	</article>
</section>
```
-	Elementos
```html
<section>
	<article class="noticia"> 
		<h1 class="noticia__titulo">Título de la noticia</h1>
	</article>
</section>
```
-	Modificadores
```html
<section>
	<article class="noticia"> 
		<h1 class="noticia__titulo--mayuscula">Título de la noticia</h1>
	</article>
</section>
```

## Reglas generales

-	Los nombres de las hojas de estilo que vayan dentro de las carpetas `components`, `layouts` y `utils` irán en plural y siempre deben comenzar con un guión bajo. El resto de hojas de estilo se nombrarán en singular (*Ejemplo: _botones.scss*).
-	Las imágenes se nombran en referencia a su bloque y están separadas por un guión (*Ejemplo: background-header.png*).
-	Las clases deben ir en singular y minúsculas (*Ejemplo: .galeria__boton*).
-	El estilo de escritura es **Kebab Case** (*Ejemplo: .main-header*).

## Sintaxis

-	Uso siempre de palabras en minúscula.
-	Uso de comillas dobles preferiblemente en lugar de comillas simples.
-	El selector y la llave de apertura deben ir en la misma línea, sin sangrar.
-	1 espacio en blanco entre el selector y la llave.
-	Cada propiedad debe ir en una línea, completando la línea con un punto y coma.
-	1 tabulación para identación.
-	0 espacios antes de los dos puntos que separan la propiedad y su valor. 
-	1 espacio después de los dos puntos que definen de la propiedad.
-	0 espacios en blanco antes del punto y coma final de cada línea de propiedad.
-	La llave de cierre debe ir en una línea, sin sangrar. En esa línea sólo estará la llave de cierre.
-	Bloques de CSS separados por una línea en blanco (2 saltos de línea).
-	Selectores dentro del mismo bloque separados por 1 salto de línea.
-	Última propiedad termina siempre con punto y coma.
-	Evitar abuso de anidaciones. Límite 1 nivel.
-	Evitar el uso de identificadores `id/#` salvo en especificaciones muy concretas como el uso de anclas.
-	Siempre que se pueda usar clases `class/.`.
-	Uso de mixins para tamaño, estilos y media queries.
-	Uso de funciones para cálculos. *Ejemplo: Valores numéricos o el tamaño de fuente*.
-	1 espacio entre parámetros en mixins y funciones.
-	1 espacio antes de los paréntesis, que contienen los parámetros, en mixins y funciones.
-	Uso de propiedades cortas cuando sea posible. *Ejemplo border: 1px solid #000*
-	Se deben omitir los 0 cuando sea posible. *Ejemplo Escribir .8 en lugar de 0.8*
-	Uso de 3 caracteres haxadecimales cuando sea posible en lugar de 6. *Ejemplo #000*





