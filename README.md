jQuery classList extension
==================================================

Re-implementation of jQuery class manipulation methods that utilizes the classList interface.

Compatible with jQuery 1.9.x-2.0.x.

Rationale
--------------------------------------

HTML5 defines the `classList` interface, allowing for adding/removing/toggling classes or checking if an element
contains a specified class using built-in methods as opposed to manually parsing the `className` field where
classes are separated by spaces.

This native interface is much faster that the previous way, two test suites that confirm it are:

1. http://jsperf.com/classlist-v-old-way/8 - large number of classes
2. http://jsperf.com/classlist-v-old-way/10 - small number of classes

Unfortunately, jQuery currently doesn't utilize this interface by default, one of the reasons being it's
not supported by Internet Explorer 9. However, if your site/web app doesn't need to support this browser
or if you accept having to polyfill the interface (with the cost of having to download an additional JS file
for IE9, probably with conditional comments) it might be a good choice to use this extension performance-wise.

Browser support
--------------------------------------

1. Google Chrome 25+
2. Firefox 19+
3. Opera 12.10+
4. Safari 5.1+
2. Internet Explorer 6+

In fact the code will work in many older versions, too, but they were not tested.

In browsers that don't support the `classList` intefrace (e.g. IE < 10) this code fallbacks to the built-in
jQuery implementation so it doesn't break them.
