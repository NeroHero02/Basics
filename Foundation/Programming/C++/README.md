# Started 
**In this section, we will begin to learn and explain the details of the basics of the language C++.**  

## C++ Code Structure  

```cpp
#include <iostream>

int main()

{

std::cout << "Osama Sbeih";

return 0;
}
```
**Output:**
```
Osama Sbeih
```
- `#include` : include the library for me. 

- `#include <iostream>` :include the iostream library for me.  

- `std::cout << "Osama Sbeih";` : The command cout is within the std (standard) namespace, and this command is used to print what we write. It is an abbreviation for "Console out".  

- `int main()` : is a requirement for any C++ program, as it must contain a function named main. It serves as the entry point of the program, and it is the first thing executed when the program is run. Everything between the curly braces {} following main gets executed.  

- `return 0;` : Every function needs a return value, and we will discuss it later.  


## Output (Print)  

**The cout object, together with the << operator, is used to output values/print test**
- `std::cout` : Monitor (Destination).  
- `<<` : Write (Verb).  
- `"Message To Be Shown."` : Message (Object).  
- `;` : End (Terminator).  

Example 1 :

```cpp
#include <iostream>

int main()
{
std::cout << "Osama Sbeih";
return 0;
}
```
**Output:**  
```
Osama Sbeih
```
Example 2 : 

```cpp
#include <iostream>

int main()
{
std::cout << "My Name is : Osama Sbeih";
std::cout << " My Age is : 21";
return 0;
}
```
**Output:**  
```
My Name is : Osama Sbeih My Age is : 21
```
Note : To insert a new line, you can use the `\n` character.  

Example 3 :  
```cpp
#include <iostream>

int main()
{
std::cout << "My Name is : Osama Sbeih\n";
std::cout << "My Age is : 21\n";
return 0;
}
```  
**Output:**  
```
My Name is : Osama Sbeih 
My Age is : 21

```

Another way to insert a new line, is with the `std::endl` manipulator.  

Example 4 :
```cpp
#include <iostream>

int main()
{
std::cout << "My Name is : Osama Sbeih" << std::endl;
std::cout << "My Age is : 21" << std::endl;
return 0;
}
```  
**Output:**  
```
My Name is : Osama Sbeih 
My Age is : 21

```

Print Multiple Messages in One Line.  

Example 5 : 
```cpp
#include <iostream>

int main()
{
std::cout << "My Name is : " << "Osama Sbeih" << std::endl;
std::cout << "My Age is : " << "21" << std::endl;
return 0;
}
```  
**Output:**  
```
My Name is : Osama Sbeih 
My Age is : 21

```

## Omitting Namespace

**Using `std::` every time when `cout` and `endl` is annoying, so there is a way to get rid of that and not write it every time.**

```cpp
#include <iostream>
using namespace std;

int main()
{
cout << "My Name is : Osama Sbeih" <<endl;
cout << "My Age is : 21" << endl;
return 0;
}
```  
**Output:**  
```
My Name is : Osama Sbeih 
My Age is : 21

```
`using namespace std;` : allows you to access elements from the C++ standard library without specifying the namespace each time.  


## Which is better \n or endl ?

`\n` :

- It is a simple newline character.
- More lightweight compared to std::endl.
- Doesn't flush the output buffer.


`std::endl` :

- It represents a newline character and also flushes the output buffer. Flushing means forcing the system to immediately write the output to the console or file.
- Useful when you want to ensure that the output is immediately visible, for example, in situations where you need real-time feedback.

**Therefore, each of them has a place to use. If I have a large program that I divide, I use `endl` with some statemnts and other statements `\n`.**

## C++ Comments

- Comments can be used to explain C++ code, and to make it more readable.  
- Comemnts can be single-lined or multi-lined.  

1. Single-lined  
   - Start with two forward slashes (//).   
   - Example 1 :   
 ```cpp
// This is Comments
cout<< "OsamaSbeih" << endl;
```
  - Example 2 :  
```cpp
cout << "OsamaSbeih" << endl; // This is Comments
```
2. Multi-Line Comments  
   - Multi-line comments start with /* and ends with */.  
   - Any test between /* and */ will be ignored by the compiler.  
   - Example :
```cpp
/*This
is
Comments
*/
cout << "Osama Sbeih" << endl;
```

## Literals and Escape Sequences

**Literals : Literals are data used for representing fixed values. They can be used directly in the code.**  

  - Example : `5`, `3.5`, `b` , `"OsamaSbeih"`, ...etc.  
  - You cannot assign different values to these terms.  

Literals Types:  

1. Integer Literals : 
  - `Decimal (base 10)`.  
  - `Octal (Base 8)`.  
  - `Hexadecimal (Base 16)`.  

Note : In C++ programming , `Octal` starts with a `0` , and `Hexadecimal` starts with a `0x`.  

2. Floating-Point Literals: 
  - `13.5`.  
  - `1.99`.  
  - `-8.07`.  

3. Characters Literals: 
  - `A`.  
  - `b`.  
  - `z`.  
  - `$`.  
  - `#`.  
  
4. Escape Sequences Literals:
  - `\n`.  


**Escape Sequences:**

- `\\` (Blackslash)
- `\t` (Tab)
- `\n` (Newline)
- `\"` (Double quote)
- `\'` (Single quote)
- `\a` (Audio bell)


## Variables

**Data Types in C++**
Different types of varaibles (defined with different keywords).  

1. Fundamentals
  - Integral Type 
    - `int`  (Whole Numer : `712`).
    - `char` (Single Character : `A`).
  - Floating Type
    - `float` (Floating Point : `14.5`).
    - `double` (Floating Point : `14.5`).
  - Bolean Type 
    - `bool` (`True` or `False`).
  - String Type
    - `string` (Text:`"Osama"`).
  - Void Type
    - `void` (`Empty`).
  - Wide Character 
    - `wchar_t` (`Unicode`).

2. Derived
  - `Function`.
  - `Array`.
  - `Pointer`.
  - `Refrence`.
3. User-Defined
  - `Class`.
  - `Structure`.
  - `Union`.
  - `Enum`.
  - `Type Def`.
