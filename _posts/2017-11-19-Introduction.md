---
layout: post
title:  "Introduction"
categories: default
tags: test syntax
---
# C Sharp
Each Module has multiple chapters with coding examples with it.

## Introduction to C#

C# runs on top .Net Framework. It provides the languages with basic syntax and interfaces that can be used for communication with other apps.

There are two distinct features of .Net Framework
1. CLR [Comman Language RunTime](https://docs.microsoft.com/en-us/dotnet/standard/clr)
2. FCL [Framework Class Library](https://docs.microsoft.com/en-us/dotnet/standard/framework-libraries)

### CLR
- It is responsible for bringing the app to life and managing the resources while exectuing the app.
- It is also responsible for the tearing down the application or when it hits an unrecoverable state.
- It tracks the memory that is being used and cleans up once it is finished exectuing. 
- It performs virtulization of the apps by converting to -64 or 32 bit and such.
- Supports different languages like F# etc.,
- Takes care of differnet platforms (Linux/Mac)

### FCL
- Contains BCL[Base Class Library](https://docs.microsoft.com/en-us/dotnet/standard/framework-libraries)

##### Hello World!
```
Using System;

public Class Program
{
  static void Main()
  {
    console.writeLine("Hello World!"); // cw and press tab twice
  }
}
```
_This is an cs file which is not exectuable(exe/dll) version. In order to do that we can use cmd prompt to generate exe file 
which will be gives us the desired output. Below links have step by step procedure to do so_

[SO](https://stackoverflow.com/questions/21476588/where-is-developer-command-prompt-for-vs2013)

[VS Docs](https://docs.microsoft.com/en-us/dotnet/framework/tools/developer-command-prompt-for-vs)

##### Args
```
Using System;

public Class Program
{
  static void Main(string[] args)
  {
    console.writeLine("Hello" +args[]+"!"); // Hello there! 
  }
}
```

Just like C and C++ we can supply with argruments which can be used by the program.

##### Breakpoints and Debugging

Possibly one of best features of the vs studio is debugging. We can have breakpoints and we can hover over the variables changes which helps us in better understanding of the code.

![Debug](https://user-images.githubusercontent.com/8538409/29741918-9d52856a-8a93-11e7-8007-8351c3d64bdc.PNG)

##### Complier

When the program is executed `.cs` file is converted into `.exe`/`.dll`  which then with the help of [CLR](https://en.wikipedia.org/wiki/Common_Language_Runtime) is converted into machine code. 

Without CLR `.exe`/`dll` file can't be executed which reads and converts the instruction that are written in [MSIL](https://en.wikipedia.org/wiki/Common_Intermediate_Language). But MSIL is comman for all languages that are supported by .NET Framework
