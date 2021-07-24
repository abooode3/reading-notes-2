# Java Basics

### Variables
- Type Of Variables:
1. Instance Variables (Non-Static Fields): the values are uniqe to each instance of a class
2. Class Variables (Static Fields):use (static) modifier, 
> one copy of this variable in existence, regardless of how many times the class has been instantiated
3. Local Variables: only visible to the methods in which they are declared and not accessible from the rest of the class.
4. Parameters: always classified as "variables" not "fields"

The rules for naming variables:
1. Variable names are case-sensitive : start with letter, $ , _ 
2. if the name consists of only one word, spell that word in all lowercase letters. If it consists of more than one word, capitalize the first letter of each subsequent word.


### Operators

| Operators             | Precedence                      |
| -----------           | -------------------------       |
| postfix               | expr++ expr--                   |
| unary                 |  ++expr --expr +expr -expr ~ !  |
| multiplicative        | * / %                           |
| additive              | + -                             |
| shift                 | << >> >>>                       | 
| relational            | < > <= >= instanceof            | 
| equality              | == !=                           |
| bitwise               | AND	&                         |
| bitwise exclusive OR  | ^                               |
| bitwise inclusive OR  | |                               |
| logical AND           | &&                              |
| logical OR            | ||                              |
| ternary               | 	? :                           |
| assignment            |= += -= *= /= %= &= ^= |= <<= >>= >>>=  |


### Expressions, Statements, and Blocks
> An expression is a construct made up of variables, operators, and method invocations

#### Statment 
 
1. expression statements:
- // assignment statement
aValue = 8933.234;
- // increment statement
aValue++;
- // method invocation statement
System.out.println("Hello World!");
- // object creation statement
Bicycle myBike = new Bicycle();


2. declaration statements 
// declaration statement
double aValue = 8933.234; 

3. control flow statements.
- decision-making statements (if-then, if-then-else, switch)
- the looping statements (for, while, do-while)
- the branching statements (break, continue, return)

#### Blocks 
> A block is a group of zero or more statements between balanced braces and can be used anywhere

## Compiling
- Compiling is the process of transforming a high level language into a low level langauge. A low level language is closer to what the computer understands.

