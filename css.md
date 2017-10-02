# CSS

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

