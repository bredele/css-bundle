css-bundle
==========

This is a bundle of CSS tips that have been very helpful in my projects.

## Vertical and Horizontal centering 

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

