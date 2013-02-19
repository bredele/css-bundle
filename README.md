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

Thankfully, new specifications describe a flexible box model optimized (i.e. less css, more maintainable) for user interface design. You can use it with the property display : flex.

```css
  display:-webkit-flex;
  display:flex;
```

In this model, the children of a flex container can be laid out in any direction and can flex their sizes, fill unused space, etc. See http://www.w3.org/TR/css3-flexbox/ for more information.

I tried in this repository to gather useful layout using flexbox. The first one (website.html) is a responsive layout for your website with header, section, aside and footer.

## Inset text-shadow

https://github.com/bredele/css-bundle/tree/master/inset-text-shadow

At the opposite of box-shadow, text-shadow doesn't have an inset property. However, it is possible to get the same effect : 

```css
body { 
  background: white;
}


.inset {
  color:rgba(0,0,0,.6);
  text-shadow: 1px 4px 6px white, 0 0 0 #000;
}
```

The background color of the parent element (here the body) has to be the same than one of the text-shadow (here the first one). The fake inset shadow is visible under slightly transparent text.

**Note**: With webkit you can play with -webkit-mask-image to apply gradient color to your text. 

## Icon fonts

https://github.com/bredele/css-bundle/tree/master/icon-fonts

I absolutely love icon fonts. If you need simple icons for your application such as home, delete, clear, etc ... icon fonts are the best for the following reasons:
  - it is scalable (icons fonts are vector which is great for hight ppi displays)
  - it is 100% accessible
  - it is optimized and lightweight
  - you can apply any CSS effect that is appliable to text

For most of your needs icon-fonts are largely suffisent (see http://css-tricks.com/flat-icons-icon-fonts/).

## CSS3 transform

https://github.com/bredele/css-bundle/tree/master/css-transform

An example of facebook-like navigation using CSS3 translate3d.

```css
  -webkit-transform:translate3d(180px,0,0);
  -moz-transform:translate3d(180px,0,0);
  -ms-transform:translate3d(180px,0,0);
  -o-transform:translate3d(180px,0,0);
  transform:translate3d(180px,0,0);
```
I used hardware accelerated css for optimal quality on both desktop and mobile interfaces. The translate3d property is the only sure way to trigger hardware acceleration. See http://bredele.tumblr.com/post/43477636846/html5-dom-and-css3-high-performance.
