# Table 

In HTML there is a tags used to create a table, mainly we use the table to represent in formation in grid format.

Basicly table start < table > </ table > tags to create a tables , the table written out row by row 
 and the < tr >  tag indicate the start of each row, and also the table cell represente using < td > and < th > tag.

there is an element used in table to make it easy like : 
                  - < thead >  
                  - < tbody >
                  - < tfoot >   



## Certing an object

There is a different ways to create an object : 1. literal notation 
                                                                          2.object construstor notation

**to create a new object ** 
> var  objectName = new object();   Blank object
* use dot notation 
- to add properties and methods.
- update a property value

using literal notation to create an empty object 
> var objectName ={ }

To delete a property using (delete keyword)
> delete objectName.property

To clear the value of property using ( ' ' )
> objectName.property = ' ' ; 

mainly in methods using ( THIS ) it's a keyword refer to the object that the method declare in to. 
and the scope of (THIS ) is just inside the function or/method

- creating many objects 
several objects can represent similar things, so object constructor use functio as a templet
> var object = new objectName( ' ' , ' ' , ' ' );
          - need two different object name  
          -  new  keyword 
          - values of  object

*********
Variables Vs Arrays 

Variables : 
           - one key (var = one value)
           - separated variables name by equal (=)
           - use name to retrieve the value

Arrays:
            - store multiple pieces of information
            - separated the values using comma 
             - use index number to retrieve an item 

***** 

* Arrays Are Objects 
arrays work like object, they hold many values but in array using index number and thats the (key). and sure can combine arrays an objectrs togather.

Array store -> series of object
objects hold -> arrays 


There is a  groups of built-in objects used in javascript
 1.  browser object model 
    (create a model of the browser tab or window ) 
          consist of : 
                    - window object : represent current browser window
                     - child object : represent other browser features

2. document object model 
  (create a model of the current web page)
        consist of:
                     - document object : represent the page as a whole 
                      - shild object : represent other items on the page

3. globel javascript object 
      (group of individual objects that relate to gifferent parts of the javascript)
            - objects represent basic data types ( STRING / NUMBER / BOOLEAN)
            - object help deal with real world (DATE / MATH / REGEX )


**Creating An Instance Of The Date Object **
if need work with date can create an instance of Date Object, allow to specify any time and date
 
> var variableNAme = new Date();

