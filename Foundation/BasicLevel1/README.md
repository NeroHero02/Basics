# Started
In this section, I will summarize the basics that programmers need to know.

## Data vs Information 
When I tell you that I have Temperature data for the past 100 years, and these data are facts, but currently, I don't benefit from them. But when I tell you that the temperature increases by 5% each year, this has become information. Therefore, the information is derived from the data I have; thus, information is represented as:
```
Data : Temerature in the past 100 Years.
Process : 
- Structure it. 
- Organize it. 
- Analyze it. 
- Give it a meaning.
Information : Global Temperature is raising.
Data + Meaning = Information
```
The difference between data and information.
1. Data : 
 - Raw facts
 - Unstructured/Unorganized
 - Unanalyzed
 - Unprocessed
 - Has no meaning

2. Information
 - Driven from data
 - Structured/Organized
 - Analyzed
 - Processed
 - Has meaning

 ## Knowledge vs Wisdom

Data&rarr;<sup>Input</sup> Processing &rarr;<sup>Output</sup> Information &rarr;<sup>With Time</sup> Knowledge &rarr;<sup>Applied</sup> Wisdom

Data is the foundation, and when processed are performed on it, it transforms into information. Over time, this information evolves into knowledge, and when applied, it becomes expertise. Therefore, having knowledge doesn't necessarily mean you are an expert; applying that knowledge is crucial to becoming an expert.

Example : 
Data : 10,000 newborn every day
Information : Newborn are dubling every year 
Knowledge : It is happening in my country!
Wisdom : I better be ready for the future and build a good infrastructure

## What is Computer
It is an electronic device that receives data and processes it according to rules, laws, and commands. After processing, it transforms the data into information.

## Functionalities of Computer

1. **Input Data.**  
Takes Data as Input.
2. **Stores Data**  
Stores the data/instructions in its memory and use them when required.
3. **Process Data**  
Processes data and convert it to useful information
4. **Output Info**  
Generates Information as output.
5. **Control**  
Controls all previous steps

**Computer is :**  
  * Electronic Device.  
  * Operating under the control of instructions.
  * Accepts Data(Input).
  * Processes Data according to certain rules.
  * Produces Information (Output).
  * Stores Information for future use.

## Computer Components:

  1. **Software**  
  Computer Programs, instructions and Data. (Intangible)  
  * System Software : Operating Systems  
     Windows, Linux, Mac , ... etc.  
  * Application Software :  
     MsOffice, Photoshop , ... etc.

  2. **Hardware**  
  Collection of physical elements. (Tangible)
  * Computer case
  * Moniter
  * CPU
  * RAM
  * Motherboard
  * Keybaord

## Computer Units :*

1. **Input:**  
  Any device that provides data or signal to computer.
  Examples : Keybaord, Mouse , Camera , Mic.
2. **Output:**  
  Any device used to communicate results.
  Examples : Printer, Moniter , Speaker.
3. **Primary Memory:**  
    * Random Access Memory (RAM)  
       Temporary.  
    * Read Only Memory (ROM)  
      Permanent.  
      Examples : It stores the instructions for the computer to start up.
4. **Secondary Storage:**  
    * Stores data parentally (Hard Drive, CD, Memory Card, Flash Memory).
5. **Central Processing:**  
    * It is responsible for all functions and processes. (CPU)  
    Know as microprocessor or processor And it is divided into 3 parts :  
     1. ALU (Arithmetic Logic Unit). 
        Responsible for arithmetic and logical operations.   
     2. Control Unit.  
        Controls the inputs and outputs.  
     3. Cache & Registers.  


## Graphics Processing Unit
GPU stands for Graphics Processing Unit.  
you'll also see GPUs commonly referred to as graphics cards or video cards and it's only one part from graphic card. 


 ## In terms of speed in accessing data.
 Secondary Storage &rarr; Slow Access to Data.  
 Primary Storage &rarr; Makes Access to data much faster.  
 Cashe Memory &rarr; Simi Instantly available data.  
 Registers &rarr; Instantly Avalible data.  

## How Computers Works?
* Computer is an electronic device.  
* It deals with electricity On/Off.  
* It only understands 0's (Off) and 1's (On).  
* Everything you see, hear and read on the screen reaches you as the result of "on" or "off" billions of times.
* Computer uses Binary System to represent numbers, letters, commands, images and sounds.

## Decimal vs Binary

1. Decimal  
  9 8 7 6 5 4 3 2 1 0  

2. Binary  
  0 1

Bit : It is a cell that stores either zero or one.  
Zero : No Electronic.  
One : Electronic.  

Byte : Every 8 bits equal 1 byte.
* Decimal To Binary.  
```h
 0      1     0     0     0     0     0     1  
2^7    2^6   2^5   2^4   2^3   2^2   2^1   2^0  
128    64    32    16    8     4     2      1 

Base2  
2^0 ---> LSB  
2^7 ---> MSB  

Examples : 
1- Represent this in Binary : 
* 3
0      0     0     0     0     0     1     1  
2^7   2^6   2^5   2^4   2^3   2^2   2^1   2^0  
128    64    32    16    8     4     2     1 
Solution steps:
1- We make the table.  
2- We put 1 in the bits whose sum equals the number we want to convert.  
2+1 = 3  
Then 3 in binary equal 00000011.  
*8  
00001000.  
*5  
00000101 (4+1).  
*20  
00010100 (16+4).  
*21  
00010101 (16+4+1).  

Note : Only one way to represent data.  

```

*Binary To Decimal.
```h

Solution steps:
1- We make the table.  
2- We sum all the numbers that have the digit 1.

Represent this in Decimal :  
* 00000101  
* 3
0      0     0     0     0     1     0     1   
2^7   2^6   2^5   2^4   2^3   2^2   2^1   2^0   
128    64    32    16    8     4     2     1  

4+1 = 5.  

* 00010100
16+4 = 20.

* 00010101
16+4+1 = 21.

Larges number in a byte  
1      1     1     1     1     1     1     1   
2^7   2^6   2^5   2^4   2^3   2^2   2^1   2^0   
128    64    32    16    8     4     2     1  

128+64+32+16+8+4+2+1 = 255  

If the largest number representable in 1 byte is 255, how can the number 257 be represented?  
Here, we add another byte  

 0        0         0          0         0          0         0        1        0      0     0     0     0     0     0     1   
2^15     2^14      2^13       2^12      2^11       2^10      2^9      2^8      2^7    2^6   2^5   2^4   2^3   2^2   2^1   2^0   
32,768  16,384     8,192      4,096     2,048      1,024     512      256      128     64    32    16    8     4     2     1  

From 1 To 128 This First Byte.  
From 256 To 32,768 This Second Byte.  
Then 257 Equals in Binary --->100000001 (256+1).  
What is the Largest Number in 2 Byte ? 
1111111111111111 (32768+16384+8192+4096+2048+1024+512+256+128+64+32+16+8+4+2+1 = 65,535).  
```
We've learned how to convert numbers, like converting from decimal to binary and vice versa. Now, how is the conversion of characters done?  
```
ASCII Code : American Standard Code for Information Interchange
A ---> 01000001 --->65.  
B ---> 01000010 --->66.  
..........etc.........  
a --->01100001 --->97.  
b --->01100010 --->98.  
This Website will help you ---> https://www.ascii-code.com/
How to represents My Name ?  
Solution steps:  
We convert letter by letter to binary.   
Osama Sbeih  
01001111 01110011 01100001 01101101 01100001 00100000 01010011 01100010 01100101 01101001 01101000  

```

Now, we can convert numbers and English letters to decimal and binary systems. But what about Arabic or other languages? How can computers handle them?  

```h
Unicode : a Universal character encoding standard that assigns a code to every character and symbol in every language in the world.
```

## Differences Between ASCII and UNICODE  

1. ASCII  
  - American Standard Code for Information Interchange.  
  - Supports specific characters (less space).  
  - Has 2 standards:  
    - 7-bit ASCII - 128 characters.  
    - 8-bit ASCII - 256 characters.  
  - Only one language.  
2. UNICODE  
  - Universal Coding System.  
  - Large number of characters (large space).  
  - It has 3 standards:  
    - UTF 8 - 256 characters.  
    - UTF 16 - 65,535 characters.  
    - UTF 32 - 4,294,967,296 characters.  
  - Any combination of languages.  

  ## Memory Units  

 ```h
 
 8 bits ---> 1 Byte.  (Text Document)  
 1024 Kilobyte (KB) --->1 Byte * 1024.  (Image, Song)  
 1,048,576 Megabyte (MB) ---> 1024 Kilobyte * 1024.  (Movie, Flash Memory)  
 1,073,741,824 Gigabyte (GB) ---> 1,048,576 Megabyte * 1024.  (Large Storge HDD)  
 1,099,511,627,776 Terabyte (TB) ---> 1,073,741,824 Gigabyte * 1024.  (HardDisk)  
There are more :
Petabyte (PB) 10 ^ 15 (Facebook Servers 10+ PBs).  
Exabyte (EB) 10^18 (Amount of data transfer over the internet).  
Zettabyte (ZB) 10^21 (whole data in the world just a few ZB).  
Yottabyte (YB) 10^24 (Huge, No practical use).  

 ```
