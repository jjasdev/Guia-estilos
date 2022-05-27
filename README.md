# Guía de estilos

Lo importante al escribir una hoja de estilo es seguir siempre los mismos criterios, para que sea más fácil detectar errores o poder reutilizarla en otros proyectos. En la mayoría de los casos, esto no supone ningún problema mientras una persona trabaje sola en un proyecto. Sin embargo, en el caso de proyectos web de mayor envergadura, son varios equipos los que se encargan de la edición, desarrollo y mantenimiento de la página web. La solución en dichos entornos de trabajo se plantea en forma de guía de estilo que permite escribir código más limpio.

## ¿Qué es?

Las guías de estilo hacen referencia, en el ámbito del desarrollo web, a los manuales para la elaboración de un diseño uniforme en cada aplicación. Las guías de estilo en maquetación resultan necesarias para presentar el trabajo realizado por los distintos equipos de desarrollo como una única unidad. Este tipo de manuales ofrecen directrices acerca de cómo se tiene codificar para poder ofrecer un desarrollo mantenible.

## Principios

–	Mantener un **código limpio** y poder reusarlo lo máximo posible
–	Implementar un código que luzca como si lo hubiera escrito una **única persona**
–	Codificar para mayor **escalabilidad y visibilidad**

## Arquitectura

La arquitectura de los proyectos usarán la estructura de carpetas estándar que la comunidad de JavaScript sigue por convención. Además, la arquitectura que se usará para organizar las carpetas del código fuente de los estilos será **La regla del 7+1**. Esta arquitectura también es conocida como patrón 7–1. Consiste en tener todas las hojas de estilo organizadas en 7 carpetas y un único archivo en la raíz para importarlas. A continuación se muestra la estructura jerárquica:

```
guia-estilos
|
|- dist/				
|  |- index.html   
|  |      
|  |- assets/				
|     |- css/				
|     |  |- style.min.css			
|     |
|     |- images/			
|     |  |- background-header.webp	
|     |
|     |- js/				
|        |- main.min.js
|
|- src/ 				
|  |- assets/				
|     |- css/				
|     |  |- style.css
|     |  |- style.css.map
|     |
|     |- images/			
|     |  |- background-header.jpg
|     |
|     |- js/				
|     |  |- main.js
|     |  |- imagemin.js
|     |  
|     |- scss/				
|        |- style.scss			
|        |
|        |- base/			
|        |  |- _global.scss 
|        |  |- _reset.scss 
|        |  |- _tipografia.scss 
|        |  
|        |- components/		
|        |  |- _buttons.scss 
|        |  |- _texts.scss 
|        |  
|        |- layouts/			
|        |  |- _footer.scss 
|        |  |- _header.scss 
|        |  
|        |- themes/			
|        |  |- _admin.scss 
|        |  |- _theme.scss 
|        |  
|        |- utils/			
|        |  |- _extends.scss 
|        |  |- _funciones.scss 
|        |  |- _mixins.scss 
|        |  |- _variables.scss 
|        |  
|        |- views/			
|        |  |- _home.scss 
|        |  
|        |- vendors/ 
```

-	`dist` Este directorio contiene la versión minificada del código fuente. Los documentos alojados en ella se usan en la aplicación en el modo de producción. 
-	`assets`  Los assets web son las hojas de estilo CSS, los archivos JavaScript y las imágenes que se utilizan en la interfaz de la aplicación.
-	`css`  Contiene las hojas de estilo usadas para dar formato al contenido y presentar la aplicación con un diseño personalizado.
-	`images`  En este directorio se alojarán todas las imágenes usadas en el proyecto.
-	`js`  Contiene los scripts implementados para agregar funcionalidad interactiva a la aplicación.
-	`src`  Este directorio contiene el código fuente en bruto. Los documentos alojados en ella son las fuentes puras usadas en el modo de desarrollo.
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

