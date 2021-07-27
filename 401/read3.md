## Primitives vs. Objects

* object contains a single value of the corresponding primitive type.

primitive type variables have the following impact on the memory:
- boolean – 1 bit
- byte – 8 bits
- short, char – 16 bits
- int, float – 32 bits
- long, double – 64 bits

referance types like:
- Boolean – 128 bits
- Byte – 128 bits
- Short, Character – 128 bits
- Integer, Float – 128 bits
- Long, Double – 192 bits

* Exceptions:
>An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.

* Assertion :
> An assertion is a sanity-check that you can turn on or turn off when you are done with your testing of the program.

##### We have three exceptions: checked exception, error exception, runtime exception. Note: Code that fails to honor the Catch or Specify Requirement will not compile.

* Scanning
Its used get data from user
• must import this packge import java.util.Scanner; • public class ScanXan { • public static void main(String[] args) throws IOException { • • Scanner s = null; • • try { • s = new Scanner(new BufferedReader(new FileReader(“xanadu.txt”))); • • while (s.hasNext()) { • System.out.println(s.next()); • } • } finally { • if (s != null) { • s.close(); • } • } • } • }
