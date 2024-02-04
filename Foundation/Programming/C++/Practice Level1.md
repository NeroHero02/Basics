# Started 
**In this section, we will solved 100 problem using C++.**  

## Problem 1
**Write a program to print your name on screen**

```cpp
#include <iostream>
using namespace std;

void PrintName(string Name)
{
	cout << "\nYour Name is : " << Name << endl;
}
int main()
{
	PrintName("OsamaSbeih");
}
```

## Problem 2
**Write a program to ask the user to enter his/her name and print it on screen**    
*The first method*
```cpp
#include <iostream>
using namespace std;

void PrintName(string Name)
{
	cout << "\nYour Name is : " << Name << endl;
}
int main()
{
	string Name;
	cout << "Please Enter You'r Name : \n";
	cin >> Name;
	PrintName(Name);
}
```
*The second method*
```cpp
#include <iostream>
#include <string>

using namespace std;

void PrintName(string Name)
{
	cout << "\nYour Name is : " << Name << endl;
}

string ReadName()
{
	string Name;

	cout << "Please Enter You'r Name : \n";
	getline(cin, Name);

	return Name;
}
int main()
{
	PrintName(ReadName());
}
```

## Problem 3
**Write a program to ask the user to enter a number , then Print "ODD" if its odd, Or "Even" if its even**   
*The first method*
```cpp
#include <iostream>
#include <string>

using namespace std;

string CheckOddEven(int Number)
{
	if (Number % 2 == 0)
		return "Even";

	return "Odd";
}
int main()
{
	int Number;
	cout << "Please Enter Number : " << endl;
	cin >> Number;
	cout << "\nYour Number is : " << CheckOddEven(Number);

    return 0;
}
```
*The Second method*
```cpp
#include <iostream>
#include <string>

using namespace std;

enum enNumberCheck{Odd = 1 , Even = 0};

int ReadNumber() {
	int Num;
	cout << "Please Enter Number : " << endl;
	cin >> Num;
	
	return Num;
}

enNumberCheck CheckNumberType(int Num) {
	int Result = Num % 2;
	if (Result == 0)
		return enNumberCheck::Even;
	return enNumberCheck::Odd;
}

void PrintNumberType(enNumberCheck NumberType) 
{
	if (enNumberCheck::Even == NumberType)
		cout << "\nNumber is Even\n";
	else
		cout << "\nNumber is Odd\n";
}
int main()
{
	PrintNumberType(CheckNumberType(ReadNumber()));
}
```

## Problem 4
**Write a program to ask the user to enter his/her:
1- Age
2- Driver license
Then Print "Hired" if his/her age is grater than 21 and s/he has a driver license, otherwise Print "Rejected"
**
```cpp

```

