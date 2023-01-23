# nexsTools.css

NexsTools.css es un conjunto de herramientas básicas escritas en SCSS, diseñadas para ayudar a principiantes y 
desarrolladores en la creación de proyectos web.

Están diseñadas para ser fácilmente implementables en el proyecto y pueden utilizarse junto con cualquier framework CSS.

**Índice**

1. [Instalación](#install)
2. [Añadiendo la hoja de estilo](#addcss)
3. [Uso de las clases](#use)
4. [Flex Layout](#flexlayout)
5. [Media Query](#mediaquery)
6. [Z-index](#zindex)


## Instalación. <a name='install'></a>

Para instalar NexsTools.css en su proyecto, simplemente incluya el archivo SCSS el proyecto y compilalo junto con el 
resto de sus estilos. También puede importar solo las partes necesarias del archivo para reducir el tamaño final del 
archivo CSS.

# Añadiendo la hoja de estilo. <a name='addcss'></a>

Puedes importar los archivos SCSS directamente en tu archivo SCSS principal y 
compilarlos junto con el resto de tus estilos. Esto te permite personalizar fácilmente las variables y utilizar 
las herramientas tal y como están diseñadas.

`// Importando los archivos SCSS
@import 'path/to/scss/nexstools.scss';`

Recuerda que si decides importar los archivos scss debes tener configurado un compilador de scss a css en tu 
proyecto para poder utilizarlo.

## Uso de las clases <a name='use'></a>

Una vez instalado, puede comenzar a utilizar las herramientas de NexsTools.css en su proyecto. Aquí hay algunos 
ejemplos de cómo puede utilizar algunas de las herramientas incluidas:

## Flex Layout <a name='flexlayout'></a>

**_flex-layout.scss** incluye un conjunto de clases más utilizadas de CSS Flex que facilitan la distribución y 
centramiento de elementos en un contenedor. Se debe incluir la clase `flex`.

[Ejemplo y guía de uso de Flex Row Codepen](https://codepen.io/ggd14/pen/poZeYNw)

**Las clases de flex incluidas son:**

## Flex Direction

- `flex row`
- `flex column`
- `flex row-reverse`
- `flex column-reverse`

## Justify Content

- `flex justify-start`
- `flex justify-center`
- `flex justify-end`
- `flex justify-around`
- `flex justify-between`
- `flex justify-evenly`

## Align Items

- `flex items-start`
- `flex items-center`
- `flex items-end`
- `flex items-stretch`

## Wrap

- `flex flex-wrap`
- `flex flex-wrap-reverse`

## Gap
 
- `gap-5`
- `gap-10`
- `gap-15`

## Fill (hijo)

-`fill`

## Align Self (hijo)
-`align-self-start`
-`align-self-center`
-`align-self-end`
-`align-self-stretch`


# Media Query <a name='mediaquery'></a>

**_media-query.scss** incluye un conjunto de herramientas de media queries que te ayudarán a crear estilos 
adaptados a diferentes resoluciones y dispositivos.

## Breakpoints

La herramienta de breakpoints te permite especificar estilos específicos para diferentes resoluciones. 
Puedes utilizar las variables de breakpoints predefinidas para las resoluciones pequeña, mediana, grande y extra grande, 
o crear tus propias variables para resoluciones personalizadas.

Estas variable son:

```
- mobile         : 370px
- tablet         : 768px
- desktop        : 1280px
- large-desktop  : 1536px
```
  
### Uso
```
    // Utilizando las variables de breakpoints predefinidas  
    @include media-query('tablet', 'min/max') {  
    // Estilos para dispositivos medianos 
    }
```

## Media Device Type

La herramienta media-type te permite especificar estilos específicos para dispositivos móviles o de escritorio.

### Uso
    
```
    @include media-type('mobile') { ... } 
    @include media-type('desktop') { ... }
```


*Nota:* Los dos anteriores ejemplos (breakpoints y device type) se compilan en el css final al ser llamada la funcion 
en la hoja de estilos en scss.


## show-at - hide-at'

La herramienta show-at - hide-at te permite mostrar o ocultar elementos según la resolución. Puedes utilizar 
las variables de breakpoints predefinidas para las resoluciones móvil, pequeña, mediana y grande, o crear tus propias 
variables para resoluciones personalizadas.

### Uso

Estas clases estan incluidas en la version css y se aplica directamente al contenedor

```
    <div class="hide-at-tablet">
    <div class="show-at-desktop">
```


# Z-index <a name='zindex'></a>

**_zindex.scss** Permite asignar índices z a tus elementos de manera ordenada y mantenible. Utiliza una variable 
$z-indexes para almacenar una lista de nombres de índices y una función z() para obtener el valor numérico 
correspondiente a cada nombre.

La variable $z-indexes se define como una lista de nombres de índices, en este caso "modal", "overlay" y "low" pero con
la libertad de de cambiar los nombres o añadir tantos índices como necesites.

La función z() recibe como parámetro un nombre de índice y devuelve su valor numérico correspondiente. El valor 
numérico se calcula restando la posición del nombre en la lista de índices a la longitud de la lista y sumándole 100.

El mixin z-index recibe como parámetro el nombre de un índice y aplica su valor numérico al estilo z-index del elemento.

```
// Asignando un índice z a un elemento
.element {
    @include z-index(modal);
}
```
De esta manera puedes asignar índices z a tus elementos de manera ordenada y mantenible, evitando problemas de 
superposición y asegurando que los elementos se comporten.


