# Semantics specifications in Maude
In this project I am using Maude to specify the semantics of several programming languages. Maude is a functional language where the programmer can define the syntax of any language by means of functional modules and equations. Also, the semantics of the languages can be specified thanks to rewrite rules.

### **GREP**
GREP is a command line tool like grep (UNIX). The user has to give it a regular expression which will specify a language (a certain set of accepted strings). Then, the user can ask if certain word belongs to the language specified by the regular expresion with a syntax that looks like this:

```is <string> in <regular expression>```

### **ENS**
ENS is a simple assembly language for a specific machine. This machine operates on eight registers and only supports integer numbers. The RAM memory for ENS is a list of address-value pairs. Each value in memory is accessed by means of its address. The flow of the language consists on executing a set of instructions, one after the other, altering the state of the bank of registers and the memory.

* It supports basic arithmetic instructions that allow the machine to sum, subtract or multiply numbers stored in registers.
* It supports information exchange instructions, which allow the machine to exchange values between the bank of registers and the memory.
* It supports jump instructions. If certain conditions are met, the predefined flow of the execution can be altered.

### **IMP**
IMP is a simple, high level, imperative language. 

* Variables and integer numbers are the basic elements of the language.
* The programmer can create complex arithmetic expressions using numbers, variables, and the +, - and * operators.
* It supports _true_ and _false_ truth values, as well as the operations and, or, not, greater than, equal to, etc.
* It supports instructions like if-else or while.
* The most important feature are the functions: implement a function and call it inside the program or inside other functions.

### **ObjectiveIMP**
This language is based off the functionality of IMP and includes the ability to code in an object oriented way. It supports objects, which are variables that contain their own variables and functions (called methods).
