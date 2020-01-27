Assignment 1 - The Art of Clean Code

Roll Number : 2018201016

Name: Danish Mukhtar

**Disclaimer :**

This code has been originally forked from the Args program described in: [http://butunclebob.com/ArticleS.UncleBob.CleanCodeArgs](http://butunclebob.com/ArticleS.UncleBob.CleanCodeArgs)

**New Feature Added:**

- Support for new Class **&quot;Date&quot;**
- Unit Test for Date Input

**Final Schema Support:**

- Char                        Boolean Argument
- Char\*                        String Argument
- Char#                        Integer Argument
- Char##                Double Argument
- Char$                        Date Argument
- Char&amp;                        Map Argument
- Char[\*]                        String Array Argument

**Example for use:**

**        Schema: (**z, y#, x\*, p$)

  **Command Line:** java classFile -z -y 3 -x &quot;danish mukhtar&quot; -p 21/11/2000

**Changes Made For Cleaning Code:**

1. **I.**** Testing:**

1. There were multiple asserts per test so changed to one assert per Test.
2. Added new test cases

1. testSimpleDatePresent
2. testMissingDate



**    II. Source Code:**

1. Separated Interface and Classes in different  folders
2. Removed IntegerArgumentMarshaler , StringArgumentMarshaler , BooleanArgumentMarshaler , DoubleArgumentMarshaler and create single java file  using Generics which handles all the above classes.
3. Put Marshaller Classes in one folder
4. Changed Names of few variables to convey the semantic meaning and importance of the data to be stored
5. Tried to have code in a method as small as possible ,so for few functions

having many code of lines present breaked into multiple functions.

1. Methods having at max of 2 parameters
2. Function declaration and Function calls were having parameters in the same line , so changed this format to function return type and function name in one line and every parameter in different lines.
3. Implemented new feature **Date** with schema as $



**       **
