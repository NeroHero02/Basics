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

## Computer Units :

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
2^0 ---> Lowest Significant Bit(LSB).
2^7 ---> Most Significant Bit (MSB).

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

**Binary To Decimal.**
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

 ## CPU Speed

 * Higher clock speed means a faster CPU (within the same generation).  
 * Clock speed (also "clock rate" or "frequency") is one of the most significant.  
 * A CPU with a clock speed of 3.2 GHz executes 3.2 billion cycles per second.  
 Note : Hertz HZ --> Cycles per second (Colck Cycle).


 ## What is the Different Between32-Bit vs 64-Bit

1. 32-Bit  
   - Less Processing power, older , slower , and less secure.  
   - 2^32 (or 4,294,967,296) bytes.  
   - Can allocate only 4GB of memory (RAM).  
   - Referred to as x86 or x86-32.  
   - Can only run a 32-bit operating system and 32-bit software.  

2. 64-Bit
  
   - More processing power, newer , faster , and more secure.  
   - 2^64 (or 18,446,744,073,709,551,616) Bytes.  
   - Can allocate much more RAM.  
   - Referred to as x64 or x86-64.  
   - Can run both 64-bit 32-bit operating systems and software.  

  Note : if you have installed 32-bit operating system on a 64-bit computer, then it can run 32-bit software only.



## What is Hexadecimal System?
Hexadecimal (Base 16)   
0 1 2 3 4 5 6 7 8 9 A B C D E F  
Provides a human-friendly representation.  
```h
Color Picker ---> Code Hexadecimal.   
Prefix For Hexadecimal : 
Technology/Language         Prefix           Example     
   HTML&CSS                 #Code            #FFFFFF  
  C,C++,Java,...etc         0xCode           0xC2A4  
      XML                   &#Code           &#C2A4  
     Unicode                U+Code           U+C2A4  

Ok , now how can we convert Decimal to Hexadecimal.  

Example :  
* Convert 469 To Hex  
Solution steps:
1- We make a table.
2- We process the coupon every time by 16 and put the correct number and decimals, and the rest of the coupon we represent in Hexadecimal.
3- We write the number in order from bottom to top.


  Number/16          Result          Integer          Fraction          Remainder          Hex
  469/16=            29.3125          29               0.3125           16*0.3125=5         5
  29/16=             1.8125           1                0.08125          16*0.08125=13       D
  1/16=               --              --                --                  1               1

469 in Decimal Equals 1D5 in Hexadecimal.  

Ok, now how can we convert Hexadecimal To Decimal.  

*Convert 1D5 to Decimal.

Solution steps:
1- From right to left, we multiply each number according to its hexadecimal representation by 16.
2- We calculate the result for each digit in the number.
3- We collect the result of each number and this is its representation in Decimal.

    1         D         5
   16^2     16^1      16^0

   16^0 * 5 = 1 * 5 = 5.
   16^1 * 13 = 16 * 13 = 208.
   16^2 = 1 = 256*1 = 256.
  Then 1D5 in Decimal Equals 5+208+256 = 469.  

Ok, now how can convert from Hexa To Binary ? 

We have two steps : 
  1. Convert Hexa to Decimal.  
  2. Convert Decimal to Binary.

OR 
  1- We divide it into several parts, each digit is a part
  2- We convert each digit to Binary
  3- We merge all the binary digit you obtained from each part, from right to left

how can convert from Binary to Hexa?
 
  We have two steps : 
  1. Convert Binary to Decimal.
  2. Convert Decimal to Hexa.
  
OR
 1- We divide it into Nibble from right to left, which is a part
 2- Convert each part to Decimal
 3- We make adjustments according to what each Nibble in Decimal represents in Hexa
 4- We merge them from right to left

```

## Byte Parts

* 1 Byte ---> 8 Bits.
* 2 Bits ---> Crumb.
* 4 Bits ---> Nibble
* Nibble is a group of 4 bits together.
* Nibble is 1/2 Byte.
* First 4 Bits in Byte Called Lower Nibble.
* Last 4 Bits in Byte Called Upper Nibble.


## Octal Systems

**The Octal Numbering System is very similar in principle to the previous hexadecimal numbering system except that in Octal.**  
Note : Each octal digit represents 3 bits, so a 6-bit byte is two octal digits

*Why Octal ?*
- Previously in old computers the byte was only 6 digits not 8 digits.  
- In octal a binary number is divided up into groups of only 3 bits, with each group or set of bits having a distinct value of between 000 and 111.  
- The use of octal numbers has declined now, why?!  
  Because most modern computers (use Nibbles) no longer base their word length on multiples of three bits, (they are based on multiples of four bits, so hexadecimal is more widely used).  
- Octal System is base 8.  
Octal Prefix:  
```bash
0oCode ---> 0o725
```

```
Convert Decimal to Octal
The same method of converting from Hexadecimal to Decimal But we divide by 8, not 16.  
Convert Octal to Binary
The same method of converting from Hexadecimal to Binary But we convert to 3 digit every part not 4 digit.
Convert Binary to Octal
We take every 3 bits together from right to left and convert them to octal
```


## What is Network?
**Network : is a group of connected computer and devices.**  
Example: The Computer , Phones , and other Devices.  

## Network Types

1. Local Area Network (LAN).  

**LAN : Local Area Network that has a group of connected devices.**  
LAN is a type of network made up of nearby computers.  
- A LAN can have anywhere from a few devices (like a home network) to hundreds of devices (like a school or hospital).  
- Large organizations like colleges can have multiple LANs - maybe one per building.  

**Communicating on LAN**
```h
1.  Wired
Using wires or cables With Ethernet.  
2. Wireless
Without wires using Wi-Fi.

Ethernet : Rules that computers follow for communicating on a wired network.  
Wireless : Rules that computers follow for communicating through a radio signals.  

Wireless Fidelity (Wi-Fi)  : is a popular way to connect wirelessly to a network.  

Protocol : is a standard set of rules for how devices communicate through wires or wireless.  
```
2. Wide Area Network (WAN).  
WAN : is made of connected LANs that are far from each other (like in different parts of the country or world).  
WANs connect thousands or even millions of devices.  

![WAN Network](https://github.com/NeroHero02/Basics/blob/main/Foundation/BasicLevel1/Images/WAN%20network.png)  

Note : This part is sufficient to understand what networks are. As for the details, I will address them in the networking section.  

## What is Programming Language?

**Programming Language : is only a tool to help you write instructions to computer to perform certain operation/task.**  

- Instructions are called code.  
- Machine Language : Computer programming language consisting of binary or hexadecimal instructions which a computer can respond to directly.
- Assembly Language :  is a type of low-level programming language that is intended to communicate directly with a computer's hardware.  
- Low Level Language : Like Machine Language and Assembly Language.  

Example For Machine Language and Assembly Language

```h
Print "Osama, Sbeih" 
if i will do this line in Machine Language i need to write : 
0x50 0x72 0x69 0x6e 0x74 0x20 0x22 0x4f 0x73 0x61 0x6d 0x61 0x2c 0x20 0x53 0x62 0x65 0x69 0x68 0x22
if i will do this line in Assembly Language i need to write : 
section .data
    output_msg db "Osama, Sbeih", 0

section .text
    global _start

_start:
    ; write the string to stdout
    mov eax, 4          ; syscall: write
    mov ebx, 1          ; file descriptor: stdout
    mov ecx, output_msg ; pointer to the message
    mov edx, 13         ; length of the message
    int 0x80            ; make the system call

    ; exit the program
    mov eax, 1          ; syscall: exit
    xor ebx, ebx        ; exit code 0
    int 0x80            ; make the system call
```
- Middle Level Language : Like C,C++.  
- High Level Language : Like Java,C# ,...etc.    
- Translator Software : Its function is to convert from high-level languages to low-level languages so that the computer can understand Like Interpreter or Compiler.   
- High Level Language Code Called Code or Source Code.  
- Low Level Language Code Called Object Code.   
- Scripting/Interpreted Languages : Python , JavaScript.  
- Assembler : is the program that translate the assembly code to Machine code.  

Note : In terms of speed, the higher the language, the slower it is, but the easier it is to deal with, and the lower it is, the faster it is, but the more difficult it is to deal with.  

## What is the different between Compiled and Interpreted

1. Compiled 

- Reads the Entier Code at once.  
- Execute the process is much faster.  
- Machine Code is stored in HDD.  
- Generates exe file.  
- C,C++.  

2. Interpreted

- Reads one instruction at a time.  
- Execute the process is much slower.   
- Does not store any machine code on HDD.   
- No exe file generated  
- Ruby, Python, Javascript.  

## Computers Operators  

1. Mathematical  

```h
Addition + (3.0+4.2=7.2).  

Subtraction - (8.5-4.0=4.5).  

Multiplication * (5*5=25).  

Integer Division / (10/5=2).  

Modulo Division Mod (9 Mod 4 = 1).

Power ^ (3^2=9).  
```

2. Relational  
```h
Equal to = (5=7 False)

Less than < (5>7 True)

Grater than > (5>7 False)

Less than or equal to <= (5<=7 True)

Grater than or equal to >= (5>=7 False)

Not equal to <> (5<>7 True)
```

3. Logical   
```h
And AND (True AND True = True)

Or OR  (True OR False = True)

Not NOT (NOT True = False)
```