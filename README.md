* Assignment 1 - The Art of Clean Code
** Submission by
Amar Banerjee
Roll No. 2018801016
** Course
Software Engineering - Spring 2019

** Disclaimer

This code has been orginally forked from the Args program described in: http://butunclebob.com/ArticleS.UncleBob.CleanCodeArgs. I have further tried
to implement a clean coding practice on this source code written in Java.

* Usage
To use the code please implement the main class in the following way.

#+BEGIN_SRC java
public class ArgsMain {

public static void main(String[] args) {
try {
Args arg = new Args("l,p#,d*", args);

boolean logging = arg.getBoolean('l');

int port = arg.getInt('p');

String directory = arg.getString('d');

executeApplication(logging, port, directory);

} catch (ArgsException e) {
System.out.printf("Argument error: %s\n", e.errorMessage());
}
}

private static void executeApplication(boolean logging, int port, String directory) {

System.out.printf("logging is %s, port:%d, directory:%s\n",logging, port, directory);

}
}
#+END_SRC

For the ease of coding, I have used Eclipse IDE as the development environment.

* Schema:
- char - Boolean arg.
- char* - String arg.
- char# - Integer arg.
- char## - double arg.
- char[*] - one element of a string array.

Example schema: (f,s*,n#,a##,p[*])
Coresponding command line: "-f -s Bob -n 1 -a 3.2 -p e1 -p e2 -p e3

* Clean Code Practices

The source code makes use of the following clean coding prcatices:-

** Clean Code Practices in Source Code

* Package
+ The package names are named to convey the semantic categorisation for the classes inside the package.
+ Classes addressing different aspects have been seperated by packages( The classes defining exceptions,marshallers and arguments
are kept in a seperate packages), to enable modularity and seperation of concerns.

* Imports
+ The imports inside the classes have been seperated into groups in the order.
- java libraries import
- java libraries static import
- local libraries
- local libraries static imports

+ The imports are again ordered alphabetically to enable ease of reading and uderstanding the dependencies of the classes.

* Class / Interface Name
+ The class interfaces names have been named to convey the semantic meaning of the operations / functions defined in the class.
+ The interface names start with an /"I"/ to denote that the file contains the definition of an interface.

* Variables
+ The variables declared in the classes are arranged alphabetically, so enable reviewer go through each variable in sequence.
+ The variables are named to convey the semantic meaning and importance of the data to be stored.
+ Numbering is used in variables to enable quick and easy reading of the variables and understand their meanings.
+ Every variable declaration has been spaced from other variable declaration to avoid cluttering of text for the ease of reading.

* Methods

+ Functions have been named to convey the operation they execute.
+ The return types for the methods have been modified to convey the semantic meaning of the values the methods return.
+ An attempt has been made to keep the meaning of the returned value, the parameters and the function names to match the operations happening
in the function.
+ Every statement for variable declaration, data assignment, function call has been spaced to enable the reader to easily identify the order of
execution.
+ All logical, loop and switch constructs have been seperated from the single line operational code, to create a direct seperation of concerns.
+ All methods are sorted in the following order of precedence
- The order in which the functions are invoked. For e.g., if A invokes B and B invokes C, then the order of the functions in the class will be
A - B - C
- If there is no explicit order of the function within the class (As in the cases of POJO Bean classes having only getter and setter), then
the methods are ordered alphabetically to enable ease of reading and understanding the function.
+ The methods are defined with not more than 2 parameters, hence reducing data inflow and cross cutting complexity.
+ For the methods which return a value, the returned variable name is kept consistent with the method objective to enable
intutive realisation of the returned value and its meaning
+ Multiple / nested if-else constructs, have been replaced by switch statements, to enable better understading of multiple consitional blocks.
