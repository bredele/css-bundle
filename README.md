css-bundle
==========

This is a bundle of CSS tips that have been very helpful in my projects. 

## Vertical and Horizontal centering 

https://github.com/bredele/css-bundle/tree/master/vertical-centering

Trying to center elements vertically and horizontally is a real puzzle and the internet is not realy 
helpful in this task. 

A solutions exists since the development of CSS2 thanks to display:table (and it works with IE8...magical!).


```css

html {
	display: table;
	table-layout: fixed;
	width: 100%; height: 100%;
}

body {	
	display: table-cell;	
	width: 100%; height: 100%;
	vertical-align: middle;
	margin:0;
}

/* the element to center */
.vertical {
	width: 50%;
	margin: auto;
}

```
This tip comes from a talented web designer named Raphaël Goetter: http://lab.goetter.fr/post/37906297786/centrer-un-site-verticalement-et-horizontalement.

Here an other vertical centering demo with a flexible box layout:

```css

html, body {
  height:100%;
}
body{
  display:-webkit-flex;
  display:flex;

  -webkit-align-items: center;
  align-items: center;
}

.vertical {
  margin:0 auto;
}

```

## CSS positions

https://github.com/bredele/css-bundle/tree/master/css-positions

The position's base : a must know!

## Sticky footer

https://github.com/bredele/css-bundle/tree/master/sticky-footer

A cross-browser solution (works since IE8) based on display:table. No extra markup, no clearfix, a flexible content height and just a couple of lines.

```css

html, body {
  margin: 0; 
  padding: 0;
  height: 100%;
}

.wrapper {
  display : table;
  height: 100%;
  width:100%;
  behavior: url(display-table.min.htc);
}

header, footer{
  display : table-row;
  height: 100px;
}

.content {
  display : table-row;
}

```

This css use the behavior attribute to load a polyfill library intended to emulate CSS properties of display: table* family in Internet Explorer 6 and 7.

## Text wrapping

https://github.com/bredele/css-bundle/tree/master/text-overflow

There is a simple way to determine what should happen when the text overflows the containing element : the text-overflow property.


This property allows to display an ellipsis, a clip or a string...and you don't need JavaScript.

```css

.ellipsis {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

```
Things become difficult when you try to overflow a block of multi-lines. 

## Flexible box layout

https://github.com/bredele/css-bundle/tree/master/flexbox

You will find lots of dynamic or flexible layout for your website. 
Most of them are just like a plate of spaghetti. I really like meat balls but not in my code! Float positionning with relative margin, clearfix, extra markups...berk!

Thanksfully, new specifications describe a flexible box model optimized (i.e. less css, more maintainable) for user interface design. You can use it with the property display : flex.

```css
  display:-webkit-flex;
  display:flex;
```

In this model, the children of a flex container can be laid out in any direction and can flex their sizes, fill unused space, etc. See http://www.w3.org/TR/css3-flexbox/ for more information.

I tried in this repository to gather useful layout using flexbox. The first one (website.html) is a responsive layout for your website with header, section, aside and footer.


