# magik-zoom
==========

Mimics native browser zooming of images. The image is zoomed the same way as if
it were loaded directly into the browser window.

## The magik
=========

The magik is created by a few lines of CSS. Most notably the max-height and
max-width properties. Initially the image is given a `100%` value for both. When
zoomed in, the value is set to `initial`

This little line of JavaScript, put in the onclick attribute of the image,
takes care of adding and removing the `.zoom` CSS class. Of course you can move
this code to a seperate JS file. It's done this way in the lights of
KIT [Keep It Tiny ;)]

    onclick="this.className=this.className.match(/zoom/)?'':'zoom'"

IE does not support the zoom-in value for the property cursor. Chrome, Safari
(Webkit) and Firefox only support the vendor prefix version: `-moz-zoom-in;` and
`-webkit-zoom-in;`. That is why there is also a zoom cursor file included. See
below.

## Creating the `*.cur` files
========================

Go to http://cursor.cc and upload the saved png files there to create a `*.cur`
file. You can set the hotspot at the 6x6 pixel point, although I've also done
that in the CSS:

    cursor: url(zoom-in.cur) 6 6, zoom-in;