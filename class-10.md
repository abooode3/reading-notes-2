# Error Handilink & Debugging:

Execution context : every statment lives in one of these 
- global context 
      - global scope : the variable declared outside any thing, and can used anywhere becuse it has golbe scope
- function context : 
      - the varible id declare within a function, just can use it inside the function, can't call it out side in globel scope
- eval context 
 
firs thing when a function or statments nedd to call some other code, new task will go to the top of the pile (stacks) of things to do , and when finished to excute the calling will back to the task in hand. 

there is two phases when script enters a new excution : 
1. prepare
     - create new scope
     - crate function variables and arguments
2. excute
     - assign values to variables
     - reference  function and run code
     - excute statment 

* Errors:
if there is error is not handled the script will just stop processing.
and the error object help to ind where is the mistakes are 
type of built-in error object: 
- error 
- syntaxEroor
- ReferanceError 
- TypeError
- RangeError
- URIError 
- EvalError

massege error contain : name / message / fileNumber / lineNumber 

* Browser dev tools :
javascript console tell you when there is a problem, also in console can type code into it and will show the result

* brakpoints:
> can  puse the excution of script on any line, then check the values stored in variables at that poit in time
