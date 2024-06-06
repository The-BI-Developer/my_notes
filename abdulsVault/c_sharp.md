#CREATE A PROJECT FIRST
dotnet new console -o <directory_name> //note -o is output and new console is application type e.g. can be replaced by a web app

1. navigate to app directory and then code . to set app as workspace
2. edit the program.cs (rename if you like) to whatever is desired

For beginner:
1. stick to one .cs file
2. don't worry about other created folders by .net

#NET ANALOGY
.net is the theatre and c# is the script

#namespace
is like a science section within a big library

#static = opposite is instance - understand this

MyClass myObject = new MyClass();
myObject.MyInstanceMethod();

MyClass.MyStaticMethod(); //never needed to instantiate it

#MAIN
Main is entry point because that is the first method excuted when application is started

#CONSOLE
type of application that is interacted through text-only interface like cmd or bash

#void
doesn't return anything to be used elsewhere within the program

#method signatures
set of params that id's a method e.g.

public int add(int a, int b) //where int a, int b are set of params identifying method "add"
	{
		int c= a + b;
		return c
	}

#Data types: bid cars = bool int double char string
Note char stores single characters e.g. "a", "b" whereas string stores 'text' such as "Hello World

char = ascii character | string = set of ascii characters //good for memory efficiency. string is more versatile :|

#declaring of same type
int x = 5, y = 6, z = 50;

#keywords vs identifiers
variables: one is reserved and other is created 

#INTEGER TYPES
long myNum = 15000000000L; 64bits
int myNum = 5000; 32bits

#FLOAT POINT TYPES
//uses XeY syntax for exponents e.g. 5E10
//Float is an "implementation" of single (^double) floating point data type i.e. it is half of double floating point (double in c#) as it occupies 32 bits
//5.0EF where E is exponent symbol as in excel

WHY FLOATING THOUGH? the decimal point moves or floats by magnitude of the number. The position of dp is indicated by E. e..g
30.00E2, 3.0E1, 0.3E-1

float myNum = 5.5F //7 dp 32 bit = 4bytes
double myNum = 19.9D //15 digits of precision 64bit = 8bytes

#bit = smallest unit of data containing either 0 or 1 (boolean)
in 1byte = 8bits 

#sbsui ulu = sbyte, byte, short, ushort, int, uint, long, ulong : 1, 1, 2, 2, 4, 4, 8, 8 (bytes not bit)

#implicit cast versus explicit cast

//implicit or automatic casting
int x = 5
double myDouble = x

//explicit
int x = 5

//signed version of every int type except byte which has sbyte. By signed meaning the domain is from negative to positive range



double myDouble = (double) 5

//built in conversion methods

Convert.ToInt32()
Convert.ToDouble()
Convert.ToString()

#.NET FRAMEWORK IS BACKWARD COMPATIBLE WITH C# VERSIONS - OPPOSITE IS __ 


#MEMORY INEFFICIENT DATA CASTING //don't leave unused space. it won't be allocated for other variables otherwise...
Yes, if you store a value that can be represented in a smaller data type, then the remaining bits in the larger data type will be unused. For example, if you store the value 1000 in a long, then the remaining 63 bits will be unused.

#FINDING INCOMPATIBLE C# AND .NET VERSION
dotnet --info #.net sdk & host are .net version and c# version respectively. generally, both c# and .net have same version (7 in this case).

.NET SDK:
 Version:   7.0.302
 Commit:    990cf98a27

Runtime Environment:
 OS Name:     ubuntu
 OS Version:  22.04
 OS Platform: Linux
 RID:         ubuntu.22.04-x64
 Base Path:   /home/abdul/.dotnet/sdk/7.0.302/

Host:
  Version:      7.0.5
  Architecture: x64
  Commit:       8042d61b17


#LOGICAL OPERATORS
|| logical or
&& logical and
! logical not

#STRING INTERPOLATION
string firstName = "John";
string lastName = "Doe";
string name = $"My full name is: {firstName} {lastName}"; //note the use of $ at start to introduce string interpolation

#TERNARY OPERATOR - A SHORTHAND FOR IF-ELSE
string result = (time < 18) ? "Good day." : "Good evening.";
var = (condition) ? expressionTrue : expressionFalse;


#SWITCH-CASE
switch(expression) 
{
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
    break;
}
