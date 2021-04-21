# TREANSFORMS
 ways to position and alter elements.

Transforma have two type :
1. two dimensional (2D) : work on x and y axes
2. three dimensional (3D) : work on x , y axes and z (depth)

--- 
 Two Dimensional :
1.  Rotate Value : ability to rotate an element from 0 to 360 degrees

- positive value will rotate an element clockwise.
ex :  transform: rotate(20deg);

- negative value will rotate the element counterclockwise.
ex :  transform: rotate(-55deg);

2. Scale Value: to change the appeared size of an element
 -  1 : Default
 - ( . 99 - . 01) : smaller        transform: scale(.75);
 - (1.01 >=  ) : larger            transform: scale(1.25);
 
* To scale only the height /or width :
- scaleX: width    transform: scaleX(.5);  horizontal
- scaleY: height     transform: scaleY(1.15); vertical
-  width & height   transform: scale(.5, 1.15);

- Positive values will push an element down and to the right 
- Negative values will pull an element up and to the left 

3. Skew Value:  distort elements on the horizontal axis, vertical axis, or both.

- skewX:  distorts an element on the horizontal axis
  transform: skewX(5deg);
- skewY:  distorts an element on the vertical axis
  transform: skewY(-20deg);

To add multi values togather:
-   transform: rotate(25deg)    scale(.75);
-   transform: skew(10deg, 20deg)   translateX(20px);


* Transform Origin : default 50% 50%
- first is used for  horizontal axis and the second is used for the vertical axis

# Perspective 

two different ways:
-  perspective value within the transform property on individual elements
-  perspective property on the parent element residing over child elements being transformed.

can added to the single element , for group element  apply the perspective property to their parent element..

*****
# 3D Transform
- using Y axis , X axis and Z axis
 
1. 3D Rotate: 
- rotateX :  rotate an element around the x axis,  bent in half horizontally. 
- rotateY:  rotate an element around the y axis, bent in half vertically. 
- rotateZ:  value allows an element to be rotated around the z axis. 

2. 3D Scale : elements scaled on the z axis. 

3. 3D Translate :
  - negative value : push an element further away on the z     axis, (smaller element). 
  - positive value : will pull an element closer on the z axis,( a larger element.)

4. 3D Skew :  cannot be transformed on a three-dimensional scale

 

> To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.

>backface-visibility property to hidden, and you will hide the element whenever it is facing away from the screen.

***** 

# Transition & Animation 

* Transitions 
 Use to  alter the appearance and behavior of an element whenever a state change occurs

pseudo-classes.:
1. :hover
2. :focus
3. :active
4. :target 

Properties:
1. transition-property :  ex-> background , border radius , border-color, font-size , margin , top... etc
2. transition-duration :  ex-> 1s , 5ms
3. transition-timing-function:  ex->
 - linear: constant speed 
 - ease-in: starts slowly and speeds up 
 - ease-out :starts quickly and slows down
 - ease-in-out: starts slowly, speeds up in the middle, then slows down again
4. transition-delay:determines how long a transition should be stalled before executing


# Animations
use to set multiple points at which an element should undergo a transition

# Use @keyframes rule
- includes: animation name/  animation breakpoints/ and the properties intended to be animated.

- different keyframe breakpoints are set using percentages, starting at 0% and working to 100% with an intermediate breakpoint at 50%. 

* animations can only apply a transition within a single property
top: 0; to top: 100%;.

add with Animation:
- animation-name: slide
- animation-duration
-  animation-timing-function
-  animation-delay
-  animation-iteration-count

animation-direction property: 
- normal : intended from beginning to end.
- reverse : starting at 100% and working backwards to 0%
- alternate :  forward from 0% to 100% and then backwards from 100% to 0%
- alternate-reverse : starts at 100% running to 0% and then back to 100% again.

animation-fill-mode :  
- how an element should be styled either before, after, or before and after an animation is run.
- none ,forwards ,backwards, both

*****

- fade in : set  1. initial state 2. change 
- change color
-  grow & shrink
- rotate elements
-  square to circle
- 3D shadow
- swing
- inset border
