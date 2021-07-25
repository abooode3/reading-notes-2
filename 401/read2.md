## Packages and Import

packages: all java classes grouped togather inside it (directory)

- should start with packge decleration: 
    - package statment 
    - imports 
    - class

### import Option
1. import javax.swing.*;  // Make all classes visible altho only one is used.
2. import javax.swing.JOptionPane;  // Make a single class visible.
3. Alternately we can the fully qualified class name without an import.
  -    javax.swing.JOptionPane.showMessageDialog(null, "Hi");


#### NOTES :
- import only tells the compiler where to look for symbols.
- The search for names is very efficient so there is no effective difference.
- The wildcard "*" only makes the classes in this package visible, not any of the subpackages.
- All classes in the java.lang package are visible without an import.


## Different types of loops in Java

> looping is a feature which facilitates the execution of a set of instructions until the controlling Boolean-expression evaluates to false.

* types of loops:
- Simple for loop : 
control structure that allows us to repeat certain operations by incrementing and evaluating a loop counter.


- While loop:
repeats a statement or a block of statements while its controlling Boolean-expression is true.:

- Do-While loop:
 first condition evaluation happens after the first iteration of the loop.