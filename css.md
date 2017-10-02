# CSS

## Notes to share
1. [Priority](https://github.com/ssomac/cheatsheet/blob/master/css.md#cascade-priority)
1. [inheritance](https://github.com/ssomac/cheatsheet/blob/master/css.md#inheritance)
1. [Box Model](https://github.com/ssomac/cheatsheet/blob/master/css.md#box-model)
1. [Type of Boxes](https://github.com/ssomac/cheatsheet/blob/master/css.md#type-of-boxes---display-property)
1. [Flexbox](https://github.com/ssomac/cheatsheet/blob/master/css.md#flexbox)

## Shorthand

* font
* background

```css
background: red url(bg-graphic.png) 10px 10px repeat-x fixed;
/* color image position repeat scroll */
```

* padding

```css
padding: 10px 15px 15px 5px; /*top right bottom left */
```

* border
* margin

## @-rules

* @media : works like if statement

```css
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
```

## Simple selector

* .name : class name
* #name : id name
* Combinators
  * selector, selector : multiple
  * selector selector : child
  * selector > selector : immediate child
  * selector + selector : immeidate sibling
  * selector ~ selector : sibling

## Attribute selector

* [attr] : attribute
* [attr=val] : attribute with value
* [attr~=val] : attribute with one of values

```css
[data-vegetable] {
  color: green;
}

[data-vegetable="liquid"] {
  background-color: goldenrod;
}

[data-vegetable~="spicy"] {
  color: red;
}
```

* [attr|=val] : value start with val or val-
* [attr\^=val] : start with val (REGEXP)
* [attr$=val] : end with val (REGEXP)
* [attr*=val] : contains val

## Pseudo selector ( pseudo-class / pseudo-element )

* pseudo-class : preceded by a colon ( : ) to specify certain state.

```css
a:visited
a:hover
a:focus
```

* pseudo-element : preceded by two colon ( :: ) to specify certain part of an element

```css
::after
::before
::first-letter
::first-line
::selection
::backdrop
```

## Values and Units

* numeric
* Percentage : relative to a parent container
* colors : color names, hex values, rgb(x,x,x), hsl(x,x,x), rgba, hsla
* coordinate positions : relative to the top left of the screen
* Functions

### Units

* em : font-size of the current element ( width of a capital letter M)
* rem: root em. font-size of the root element. much easier than em but older version of IE doesn't support.
* vw, vh : 1/100th of the viewport.

### Unitless

* margin: 0;
* line-height: relative to current font size.(units can also be used)

## Cascade (Priority)

1. Importance : !important
1. Specificity : how many it could match. inline > ID > class, attribute, pseudo > element
1. Source Order : later source wins ( overwrite )

### Specificity Score Table

selector | Thousands | Hundreds | Tens | Ones | Total specificity
---------|-----------|----------|------|------|-----------
h1       | 0         |0         |0     | 1    |0001
\#important|0        |1         |0     |0     |0100
h1 + p::first-letter|0|0        |0     |3     |0003

### Inheritance

* inherit : font-family, color
* No inheritance : margin, padding, border, background-image

#### Controlling inheritance

* inherit : inherit parent element
* initial : browswer default, if no browswer default inherit parent
* unset : naturally inherit, otherwise initial

## Box Model

![Box Model](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)

* Box height don't observe percentage length and always adopts box content, unless absolute height is set(eg. px or em)
* total width = width + padding-right/left + border-right/left
* box-sizing : border-box => makes width/height property used for border

![box-sizing : border-box](https://mdn.mozillademos.org/files/13649/box-model-alt-small.png)

### content

* width, height : sets the content box. related) min-width, max-width, min-height, max-height

### Padding

* padding : shorthand
* padding-top, padding-right, padding-bottom, padding-left

### Border

* ignores percentage width setting
* Property
  * border : shorthand
  * border-top, border-right, border-bottom, border-left
  * border-width, border-style, border-color
  * border-top-width, border-top-style, border-top-color

### Margin

* most outer of the box.
* margin collapsing : when two boxes touch each other, larger one remains, not sum of two.
* properties
  * margin : shorthand
  * margin-top, margin-right, margin-bottom, margin-left


### Overflow ( contents area )

* auto : scroll bar
* hidden : hide
* visible : overflow. default

### Outline

* looks like a border, but not part of the box model. It's drawn on top of the box without changing the size of the box

### Type of Boxes - display property

* block : default. stacked upon other boxes. can have width/height setting.
* inline : it flows with the document's text. ie on the same line. and break with the flow of the text. width/height setting has no effect on this type of box. padding, margin and borders will update position of surrounding text, but not on surrounding block boxes
* inline-block : flows with surrounding text, can be sized using width/height but won't be broken across paragraph lines like inline and acts like block box.
* table : emulate table without table html
* flex : flexbox
* grid : grid

## Font and Text Layout

[Properties - Click here for Detail](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)


## Layout

* float

```css
div:nth-of-type(1) {
  width: 48%;
  float: left;
}

div:nth-of-type(2) {
  width: 48%;
  float: right;
}
```

* position
  * absolute : absolute to html element
  * relative : relative to normal text flow
  * z-index : default is auto and value is 0
  * fixed : relative to browswer viewport
  * sticky : experimental. doesn't move until certain scroll.

### Flexbox

* Vertically centering a block of content inside its parent.
* Making all the children of a container take up an equal amount of the available width/height, regardless of how much width/height is available.
* Making all columns in a multiple column layout adopt the same height even if they contain a different amount of content.

![flexbox](https://developer.mozilla.org/files/3739/flex_terms.png)

* main axis : items laid this direction.
* cross axis : perpendicular to the main axis
* align-item : related to cross axis
* justify-content : related to main axis
