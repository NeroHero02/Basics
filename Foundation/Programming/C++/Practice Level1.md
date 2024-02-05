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
**Write a program to ask the user to enter his/her:**  
**1- Age**  
**2- Driver license**  
**Then Print "Hired" if his/her age is grater than 21 and s/he has a driver license, otherwise Print "Rejected"**  

```cpp
#include <iostream>
#include <string>

using namespace std;

struct stInfo {
	int Age;
	bool HasDriveLicense;
};

stInfo ReadInfo()
{
	stInfo Info;
	cout << "Please Enter You'r Age : \n";
	cin >> Info.Age;
	
	cout << "Do you have driver License?" << endl;
	cin >> Info.HasDriveLicense;

	return Info;
}

bool isAccepted(stInfo Info)
{
	return (Info.Age > 21 && Info.HasDriveLicense);
}

void PrintResult(stInfo Info)
{
	if (isAccepted(Info))
		cout << "\nHired\n";
	else
		cout << "\nRejected\n";
}

int main()
{
	PrintResult(ReadInfo());
}
```

## Problem 5
**Write a program to ask the user to enter his/her:**  
**1- Age**  
**2- Driver license**  
**3- Has Recommendation!**  
**Then Print "Hired" if his/her age is grater than 21 and s/he has a driver license, otherwise Print "Rejected" Or Hire him/her without condition.**  

```cpp
#include <iostream>
#include <string>

using namespace std;

struct stInfo {
	int Age;
	bool HasDriveLicense;
	bool HasRecommendation;
};

stInfo ReadInfo()
{
	stInfo Info;
	cout << "Please Enter You'r Age : \n";
	cin >> Info.Age;
	
	cout << "Do you have driver License?" << endl;
	cin >> Info.HasDriveLicense;

	cout << "Do you have Recommendation?" << endl;
	cin >> Info.HasRecommendation;
	return Info;
}

bool isAccepted(stInfo Info)
{
	if (Info.HasRecommendation)
	{
		return true;
	}
		
	return (Info.Age > 21 && Info.HasDriveLicense);
}

void PrintResult(stInfo Info)
{
	if (isAccepted(Info))
		cout << "\nHired\n";
	else
		cout << "\nRejected\n";
}

int main()
{
	PrintResult(ReadInfo());
}
```

## Problem 6
**Write a program to ask the user to enter :**  
**- First Name**  
**- Last Name**  
**Then Print Full Name on screen.**  

```cpp
#include <iostream>
#include <string>

using namespace std;

struct stInfo
{
	string _FirstName;
	string _LastName;
};

string GetFullName(stInfo Info)
{
	return Info._FirstName + " " + Info._LastName;
}
stInfo ReadName()
{
	stInfo FullName;
	cout << "Please Enter First Name : " << endl;
	cin >> FullName._FirstName;

	cout << "Please Enter Last Name : " << endl;
	cin >> FullName._LastName;

	return FullName;

}

void PrintName(string FullName)
{
	cout << "You'r Name is : " << FullName;
}

int main()
{
	PrintName(GetFullName(ReadName()));
}
```

## Problem 7
**Write a program to ask the user to enter:**  
**-Number**  
**Then Print the "Half of the <Number> is <???>".**  

```cpp
#include <iostream>
#include <string>

using namespace std;

int ReadNumber()
{
	int Num;

	cout << "Please Enter The Number : " << endl;
	cin >> Num;

	return Num;
}

float CalculateHalfNumber(int Num) 
{
	return (float) Num / 2;
}

void PrintResult(int Num)
{
	string Result = "Half of " + to_string(Num) + " is " + to_string(CalculateHalfNumber(Num));
	cout << endl << Result;
}
int main()
{
	PrintResult(CalculateHalfNumber(ReadNumber()));
}
```
## Problem 8
**Write a program to ask the user to enter:**  
**-Mark**  
**Then Print the "PASS" if mark >=50 , otherwise print "Fail"**  


*The first method*
```cpp
#include <iostream>
#include <string>

using namespace std;

int ReadMark()
{
	int _Mark;

	cout << "Please Enter You'r Mark : \n";
	cin >> _Mark;

	return _Mark;
}

string CheckMark(int _Mark)
{
	if (_Mark >= 50)
		return "PASS";
	return "Fail";
}

void PrintResults(string Mark)
{
	cout << "You'r Finall Mark is : " << Mark << endl;
}
int main()
{
	PrintResults(CheckMark(ReadMark()));
}
```

*The Second method*
```cpp
#include <iostream>
#include <string>

using namespace std;

enum enPassFail {Pass = 1 , Fail = 2};
int ReadMark()
{
	int _Mark;

	cout << "Please Enter you'r Mark? : \n";
	cin >> _Mark;

	return _Mark;
}

enPassFail CheckMark(int Mark)
{
	if (Mark >= 50)
		return enPassFail::Pass;
	return enPassFail::Fail;
}

void PrintResult(enPassFail Mark)
{
	if (CheckMark(Mark) == enPassFail::Pass)
		cout << "\nPass\n";
	else
		cout << "\nFail\n";
}
int main()
{
	PrintResult(CheckMark(ReadMark()));
}
```

## Problem 9
**Write a program to ask the user to enter:**  
**- Number1, Number2, Number3**  
**Then Print the Sum of entered numbers**  


```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(int &Num1, int &Num2, int &Num3)
{
	cout << "Please Enter First Number :\n";
	cin >> Num1;

	cout << "Please Enter Second Number :\n";
	cin >> Num2;

	cout << "Please Enter Third Number :\n";
	cin >> Num3;

}

int Sumof3Numbers(int Num1, int Num2, int Num3)
{ 
	return Num1 + Num2 + Num3;
}

void PrintResults(int Total)
{
	cout << "Summation Three Number is : " << Total << endl;
}
int main()
{
	int Num1, Num2, Num3;
	ReadNumbers(Num1, Num2, Num3);
	PrintResults(Sumof3Numbers(Num1,Num2,Num3));
}
```

## Problem 10
**Write a program to ask the user to enter:**  
**-Mark1, Mark2, Mark3**  
**Then Print the Average of entered Marks**  

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(int &Mark1, int &Mark2, int &Mark3)
{
	cout << "Please Enter First Number :\n";
	cin >> Mark1;

	cout << "Please Enter Second Number :\n";
	cin >> Mark2;

	cout << "Please Enter Third Number :\n";
	cin >> Mark3;

}

int Sumof3Numbers(int Mark1, int Mark2, int Mark3)
{ 
	return Mark1 + Mark2 + Mark3;
}

float CalculateAverage(int Mark1, int Mark2, int Mark3)
{
	return (float)Sumof3Numbers(Mark1, Mark2, Mark3) / 3;
}

void PrintResults(float Average)
{
	cout << "The Average is : " << Average << endl;
}
int main()
{
	int Mark1,	Mark2, Mark3;
	ReadNumbers(Mark1, Mark2, Mark3);
	PrintResults(CalculateAverage(Mark1,Mark2,Mark3));
}
```

## Problem 11
**Write a program to ask the user to enter:**  
**- Mark1,Mark2,Mark3**
**Then Print the Average of entered Marks, and print "Pass" if average>=50, otherwise print "FAIL"**
```cpp
#include <iostream>
#include <string>

using namespace std;

enum enPassFail {Pass = 1 , Fail = 2};
void ReadNumbers(int &Mark1, int &Mark2, int &Mark3)
{
	cout << "Please Enter First Number :\n";
	cin >> Mark1;

	cout << "Please Enter Second Number :\n";
	cin >> Mark2;

	cout << "Please Enter Third Number :\n";
	cin >> Mark3;

}

int Sumof3Numbers(int Mark1, int Mark2, int Mark3)
{ 
	return Mark1 + Mark2 + Mark3;
}

float CalculateAverage(int Mark1, int Mark2, int Mark3)
{
	return (float)Sumof3Numbers(Mark1, Mark2, Mark3) / 3;
}

enPassFail CheckAverage(float Average)
{
	if (Average >= 50)
		return enPassFail::Pass;
	return enPassFail::Fail;
}

void PrintResults(float Average)
{
	cout << "The Average is : " << Average << endl;
	if (CheckAverage(Average) == enPassFail::Pass)
		cout << "\n You Passed";
	else
		cout << "\n You Failed";
}
int main()
{
	int Mark1,	Mark2, Mark3;
	ReadNumbers(Mark1, Mark2, Mark3);
	PrintResults(CalculateAverage(Mark1,Mark2,Mark3));
}
```

## Problem 12
**Write a program to ask the user to enter:**  
**- Number1, Number2**
**Then Print the Max Number**

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(int& Number1, int& Number2)
{
	cout << "\nPlease Enter First Number :\n";
	cin >> Number1;

	cout << "\nPlease Enter Second Number :\n";
	cin >> Number2;

}

int MaxOf2Number(int Number1, int Number2)
{
	if (Number1 > Number2)
		return Number1;
	return Number2;
}

void PrintResults(int Max)
{
	cout << "\n The Maximum Number is : " << Max << endl;
}
int main()
{
	int Number1, Number2;
	ReadNumbers(Number1, Number2);
	PrintResults(MaxOf2Number(Number1, Number2));
}
```

## Problem 13
**Write a program to ask the user to enter 3 Numbers:**  
**- A, B, C**
**Then Print the Max Number**

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(int& Number1, int& Number2, int &Number3)
{
	cout << "\nPlease Enter First Number :\n";
	cin >> Number1;

	cout << "\nPlease Enter Second Number :\n";
	cin >> Number2;

	cout << "\nPlease Enter Third Number :\n";
	cin >> Number3;

}

int MaxOf2Number(int Number1, int Number2)
{
	if (Number1 > Number2)
		return Number1;
	return Number2;
}
int MaxOf3Number(int Number1, int Number2 , int Number3)
{
	if (Number1 > Number2 && Number1 > Number3)
		return Number1;

	else if (Number2>Number1 && Number2 > Number3)
	    return Number2;

	return Number3;

}


void PrintResults(int Max)
{
	cout << "\n The Maximum Number is : " << Max << endl;
}
int main()
{
	int Number1, Number2, Number3;
	ReadNumbers(Number1, Number2, Number3);
	PrintResults(MaxOf3Number(Number1, Number2, Number3));
}
```

## Problem 14
**Write a program to ask the user to enter:**  
**- Number1, Number2**
**Then Print the two numbers , then Swap the two numbers and print them**

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(int& Number1, int& Number2)
{
	cout << "\nPlease Enter First Number :\n";
	cin >> Number1;

	cout << "\nPlease Enter Second Number :\n";
	cin >> Number2;

}

void Swap(int& Number1, int& Number2)
{
	int Temp = Number1;
	Number1 = Number2;
	Number2 = Temp;
}

void PrintNumbers (int Number1 , int Number2)
{
	cout << "Number1 = " << Number1 << endl;
	cout << "Number2 = " << Number2 << endl;
}
int main()
{
	int Number1, Number2, Number3;

	ReadNumbers(Number1, Number2);
	PrintNumbers(Number1,Number2);

	Swap(Number1, Number2);
	PrintNumbers(Number1, Number2);
}
```

## Problem 15
**Write a program to calculate rectangle area and print it on the screen**

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(float& Length, float& Width)
{
	cout << "\nPlease Enter Length of Area :\n";
	cin >> Length;

	cout << "\nPlease Enter Width of Area :\n";
	cin >> Width;

}

float CalculateRectangleArea(float Length, float Width)
{
	return Length * Width;
}

void PrintResults(float Area)
{
	cout << "The Area of Rectangle is : " << Area << endl;
}

int main()
{
	float Length, Width;
	ReadNumbers(Length, Width);
	PrintResults(CalculateRectangleArea(Length, Width));
}
```

## Problem 16
**Write a program to calculate rectangle area through diagonal and side are of rectangle and print it on the screen**  
- Area = A * $\sqrt{D^2-A^2}$  

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(float& A, float& D)
{
	cout << "\nPlease Enter A of Area :\n";
	cin >> A;

	cout << "\nPlease Enter D of Area :\n";
	cin >> D;

}

float CalculateRectangleAreabySideAndDiagonal(float A, float D)
{
	float Area = A * sqrt(pow(D, 2) - pow(A, 2));
	return Area;
}

void PrintResults(float Area)
{
	cout << "The Area of Rectangle by  Side and Diagonal is : " << Area << endl;
}

int main()
{
	float A, D;
	ReadNumbers(A, D);
	PrintResults(CalculateRectangleAreabySideAndDiagonal(A, D));
}
```

## Problem 17
**Write a program to calculate triangle area then print it on the screen**  
<sup>1</sup>&frasl;<sub>2</sub> A * H;

```cpp
#include <iostream>
#include <string>

using namespace std;

void ReadNumbers(float& A, float& H)
{
	cout << "\nPlease Enter A of Area :\n";
	cin >> A;

	cout << "\nPlease Enter H of Area :\n";
	cin >> H;

}

float CalculateTriangleArea(float A, float H)
{
	float Area = 0.5 * A * H;
	return Area;
}

void PrintResults(float Area)
{
	cout << "The Area of Triangle is : " << Area << endl;
}

int main()
{
	float A, H;
	ReadNumbers(A, H);
	PrintResults(CalculateTriangleArea(A, H));
}
```

## Problem 18

**Write a program to calculate circle area then print it on the screen**
- Area = &#960; * $R^2$

```cpp
#include <iostream>
#include <string>
using namespace std;

float ReadRadious()
{
	float R;
	cout << "\nPlease Enter Radious :\n";
	cin >> R;

	return R;
}

float CalculateCricleArea(float R)
{
	const float _PI = 3.141592653589793238;

	float Area = _PI * pow(R,2);

	return Area;
}

void PrintResults(float Area)
{
	cout << "The Area of Circle is : " << Area << endl;
}

int main()
{
	PrintResults(CalculateCricleArea(ReadRadious()));
}
```
## Problem 19

**Write a program to calculate circle area through diameter, then print it on the screen.**
- Area = &#960; * $D^2$ &frasl; <sub>4</sub>