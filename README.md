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

