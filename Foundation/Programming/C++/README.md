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

**Therefore, each of them has a place to use. If I have a large program that I divide, I use `endl` with some statemnts and with other statements `\n`.**

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

