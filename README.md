# nexsTools.css

NexsTools.css is a set of basic tools written in SCSS, designed to help beginners and developers in creating 
web projects. 

They're made to be easily implementable in your project and can be used alongside any CSS framework.


**Table of content**

1. [Instalation](#install)
2. [Adding the stylesheet](#addCss)
3. [Using the css classes](#use)
4. [Flex Layout](#flexLayout)
5. [Media Query](#mediaQuery)
6. [Z-index](#zindex)

## Instalation. <a name='install'></a>

To install nexsTools.css in your project, simply include the SCSS file in your project and compile it along with the
rest of your styles. You can also import only the necessary parts of the file to reduce the final size of the CSS file.

# Adding the stylesheet. <a name='addCss'></a>

You can import the SCSS files directly into your main SCSS file and compile them along 
with the rest of your styles. This allows you to easily customize the variables and use the tools as they are designed.

`// Importing the SCSS files
@import 'path/to/scss/nexstools.scss';`

Remember that if you decide to import the SCSS files, you must have a SCSS to CSS compiler configured in your project 
to be able to use it.

## Using the classes <a name='use'></a>

Once installed, you can start using the nexsTools.css tools in your project. Here are some examples of how you can 
use some included tools:

## Flex Layout <a name='flexLayout'></a>

**_flex-layout.scss**  includes a set of commonly used CSS Flex classes that make it easy to distribute and center 
elements in a container. The `flex` class must be included.

[Flex Row usage example and guide on Codepen](https://codepen.io/ggd14/pen/poZeYNw)

**The included flex classes are:**

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

## Fill (child)

-`fill`

## Align Self (child)
-`align-self-start`
-`align-self-center`
-`align-self-end`
-`align-self-stretch`


# Media Query <a name='mediaQuery'></a>

**_media-query.scss** The media query toolset includes a set of tools that will help you create styles adapted to 
different resolutions and devices.

## Breakpoints

The breakpoint tool allows you to specify specific styles for different resolutions. You can use the predefined 
breakpoint variables for small, medium, large and extra large resolutions, or create your own variables for custom 
resolutions.

These variables are:

```
- mobile         : 370px
- tablet         : 768px
- desktop        : 1280px
- large-desktop  : 1536px
```
### Usage

```
    // Utilizing predefined breakpoint variables  
    @include media-query('tablet', 'min/max') {  
    // Styles for medium devices
    }
```

## Media Device Type

The media-type tool allows you to specify specific styles for mobile or desktop devices.

### Usage

```
    @include media-type('mobile') { ... } 
    @include media-type('desktop') { ... }
```

**Note:** Both the previous examples (breakpoints and device type) are compiled in the final CSS when the function is 
called in the stylesheet in SCSS.

## show-at - hide-at'

The show-at - hide-at tool allows you to show or hide elements based on the resolution. You can use predefined 
breakpoint variables for mobile, small, medium and large resolutions, or create your own variables for 
custom resolutions.

### Usage

These classes are included in the CSS version and are applied directly to the container.

```
    <div class="hide-at-tablet">
    <div class="show-at-desktop">
```


# Z-index <a name='zindex'></a>

**_zindex.scss** Allows you to assign z-indices to your elements in an orderly and maintainable way. It uses a 
variable $z-indexes to store a list of index names and a z() function to obtain the corresponding numerical value 
for each name.

The variable $z-indexes is defined as a list of index names, in this case "modal", "overlay" and "low" but with the 
freedom to change the names or add as many indices as you need.

The z() function takes as a parameter an index name and returns its corresponding numerical value. The numerical 
value is calculated by subtracting the position of the name in the index list from the length of the list and 
adding 100.

The z-index mixin takes as a parameter the name of an index and applies its numerical value to the 
element's z-index style.

```
// Assigning a z-index to an element
.element {
    @include z-index(modal);
}
```

This way you can assign z-indices to your elements in an orderly and maintainable way, avoiding problems of overlapping 
and ensuring that the elements behave properly.
