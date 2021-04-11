object -->

is a set of variables and function to creat a model of something. 
object is a standalone entity with properties and type 
variables --> properties (to define the caractaristics) , the value of property can be string,number,boolean,array.
function-->method (represent tasks), always the value is a function.


**properties and method have 1)name 2)value than known as key

**in method used keyword this to indicate that is used the property of this object.

to access a property/method of an object :using dot notation
objectName.name of properity/method.
(.) period(member operator)

Document Object Model-->
- set of rules it is implemented by all browser makers to make a model of the HTML pages and accessing and changing the HTML page.

DOM tree-> creates a model of web pages when the browser load the pages, and storees in the browser memory. Scripts access and update thi DOM tree not source html file .consists of four main types of nodes : 
1)Document Node (Top of the tree)
2)Element Nodese
3)Attribute Nodee
4)Text Nodes

To accessing and updating the DOM tree:
1)Locate the node (Access The Element)
      -select an individual element node-> getElementById() / querySelector()
      -select multiple elements getElementByClassName() / getElementByTagName () / querySelector()
      - traversing betweer element node :(parentNode) / (previousSibl ing / nextSibl ing) / firstChild / lastChild ()

2)Work with those element 
     -Access/Updante text node : nodeVakue
     -Work with html content : innerHTML / textContent / creatElement() - createTextNode() / appendChild() - removeChild()
     - Access or update attribute values : className/ id - hasAttribute() - getAttribute() -setAttri bute() -removeAttribute() 

    ** if the script needs to use the same elements more than once, should store the location of the element in a variable. it store the reference to where that node is in the DOM tree

 * Method select individual elements ->> getElementById () / querySelector()
syntex--> 
document.getElementById('attribute')

 *Method return more than one element->>getElementsByTagName( )/ getElementsByClassName( )/querySe l ectorA 11 ( ) 

** selecting an element from a nodelist  :
 1) item() ->> return an individual node from the Node list.
 2) array syntax ->>it is faster , check nodes then select.
 
  ** Using  loop so you can loop through each node in the collection and apply the same statments to each
 
 
  ** Adding or removing html content ->>innerHTML / DOM manipulation 

Attribute nodes:  to access and change its attributes
1)select the element node that carries the attribute  2)using method
