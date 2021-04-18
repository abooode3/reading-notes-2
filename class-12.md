## Charts

use it to display data dawnload charst.js,, import secript , drawing a pie chart 
1. canvas element 
2. Next, we need to get the context and to instantiate the chart:
3. to create the data.

 - < canvas > element has only two attributes, width and height
  defult value be 300 pixels wide and 150 pixels high
 -  can add to < canvas >  (margin, border, background…). 
 -  < canvas> element requires the closing tag (</ canvas>


* drawing paths
A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color.
functions:

- beginPath()
- Path methods
- closePath()
- stroke()
- fill()


* appying styles and color :
-  to apply colors to a shape, use there properties : fillStyle and strokeStyle


* Line styles
 to style lines use :

- lineWidth = value
- lineCap = type
- lineJoin = type
- miterLimit = value
- getLineDash()
- setLineDash(segments)
- lineDashOffset = value


* The canvas rendering context provides two methods to render text:

- fillText(text, x, y [, maxWidth]) : Fills a given text at the given (x,y) position. 
- strokeText(text, x, y [, maxWidth]) : Strokes a given text at the given (x,y) position. 


* Styling text 
There are some more properties which let you adjust the way the text gets displayed on the canvas:

- font = value
- textAlign = value
- textBaseline = value
- direction = value

