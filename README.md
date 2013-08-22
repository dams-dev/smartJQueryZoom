#Zoom and pan jQuery plugin

This plugin manage smooth zoom and pan on a given dom element. The plugin works on mobile and pc and use CSS3 transitions on compatible web browsers. (javascript is used for old web browsers)

Zoom is enabled via mouse events (scroll and click) on pc and with touch events on mobile devices.

For live examples and more explanations visit : [http://e-smartdev.com/#!jsPluginList/panAndZoomJQuery](http://e-smartdev.com/#!jsPluginList/panAndZoomJQuery)

##Initialization

```js
  $(document).ready(function() {
    $("#elementToZoomOn").smartZoom(); // start plugin behaviour
  });
```

##Options
You can customize smartZoom plugin behaviour with an option object.
```js
options = {'top' : '0', // zoom target container top position in pixel
           'left' : '0', // zoom target container left position in pixel
           'width' : '100%', // zoom target container width in pixel or in percent
           'height' : '100%', // zoom target container height in pixel or in percent 
           'easing' : 'smartZoomEasing', // jquery easing function used when the browser doesn't support css transitions
           'maxScale' : 3, // the max scale that will be applied on the zoom target
           'dblClickMaxScale' : 1.8, // the max scale that will be applied on the zoom target on double click
           'mouseEnabled' : true, // enable plugin mouse interaction 
           'scrollEnabled' : true, // enable plugin mouse wheel behviour
           'dblClickEnabled' : true, // enable plugin mouse doubleClick behviour
           'mouseMoveEnabled' : true, // enable plugin target drag behviour
           'moveCursorEnabled' : true, // show moveCursor for drag
           'touchEnabled' : true, // enable plugin touch interaction 
           'dblTapEnabled' : true, // enable plugin double tap behaviour 
           'pinchEnabled' : true, // enable zoom when user pinch on target
           'touchMoveEnabled' : true, // enable target move via touch
           'containerBackground' : '#FFFFFF', // zoom target container background color (if containerClass is not set)
           'containerClass' : ''// class to apply to zoom target container if you whant to change background or borders (don't change size or position via css)
          } 
```		  
This sample code set the maximum scale to 4 and apply a red background to the zoom container:
```js
  $(document).ready(function() {
    $("#elementToZoomOn").smartZoom({'maxScale':4, 'containerBackground':'#FF0000'}); // start plugin behaviour
  });
```
##Methods

###`smartZoom("zoom", scaleToAdd, globalRequestedPosition, duration)`
Zoom on a given position.
```js
	jQuery(document).ready(function(){
	     $('#domElementToZoom').smartZoom("zoom", 0.5);
	});
```
This call add 0.5 to the target current scale.

__Arguments__

  1. `scaleToAdd` _{Number}_: Scale to add to the target.
  2. `globalRequestedPosition` _{Object}_: Position to zoom on. (Default target center)
  3. `duration` _{Number}_: Effect duration in millisecondes. (Default 700)

###`smartZoom("pan", pixelsToMoveOnX, pixelsToMoveOnY, duration)`
Move the target on the given position.
```js
	jQuery(document).ready(function(){
     $('#domElementToZoom').smartZoom("pan", 5, 0);
  });
```
This call move the target 5 pixels to the right.

__Arguments__

  1. `pixelsToMoveOnX` _{Number}_: Pixels to add on horizontal axis
  2. `pixelsToMoveOnY` _{Object}_: Pixels to add on vertical axis.
  3. `duration` _{Number}_: Effect duration in millisecondes. (Default 700)

###`smartZoom("destroy")`
Remove and clean the plugin.
```js
	jQuery(document).ready(function(){
      $('#domElementToZoom').smartZoom("destroy");
  });
```
Remove the plugin behaviour.

###`smartZoom("isPluginActive"):Boolean`
Check if the plugin is active or not.
```js
	jQuery(document).ready(function(){
     if($('#zoomImage').smartZoom('isPluginActive'))
          $('#zoomImage').smartZoom('destroy'); 
     else
          $('#zoomImage').smartZoom();
  });
```
If the plugin is activate, remove it else launch it.

  

