# React Docs - Forms

1. What is a ‘Controlled Component’?

- A Controlled Component is one that takes its current value through props and notifies changes through callbacks like onChange .


2. Should we wait to store the users responses from the form into state when they
submit the form OR should we update the state with their responses as soon as they enter them? Why.

- Use the ternary operator to simplify your if-else statements that are used to assign values to variables. The ternary operator is commonly used when assigning post data or validating forms.



3. How do we target what the user is entering if we have an event handler on an input field?

-  When you need to handle multiple controlled input elements, you can add a name attribute to each element and let the handler function choose what to do based on the value of event.target.name.
----------------------------------------------------------------

# The Conditional (Ternary) Operator Explained

1. Why would we use a ternary operator?

- Using a conditional, like an if statement, allows us to specify that a certain block of code should be executed if a certain condition is met.


2. Rewrite the following statement using a ternary statement?

if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
===
let equity = {
x:0,
y:0,
equityTest:x=y
};
= persoequity.equityTest x===y ? console.log(true) : console.log(false);