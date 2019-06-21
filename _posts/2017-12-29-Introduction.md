---
layout: post
title:  "Introduction to C#"
categories: Introduction
tags: Introduction
---

C# is an object oriented language which runs on top .Net Framework. The framework provides language with basic class libraries and interfaces that can be used in handling basic chores.

### Compilation 

Compiling any language supported that is supported by the framework can be broken down to two basic steps. First is to convert the code MSIL which will be common code for any language that is supported by the Framework. Second is to use .NET Framework to convert the code to native machine language with the help of JIT and CLR

C# program will complied with help of the compiler to MSIL(Microsoft Intermediate Languange) or simply IL. Intermediate Language will simply create an exe/dll file which contains information about the assembly and its version,features and security requirements.

This converted IL code will be loaded with help of CLR and Just In Time(JIT) compilations will happent to convert this code to machine language.

Source code that is written in C# or any other language that is supported by .Net Framework follows the same flow of converting from Higher Language to Machine readable code.

Below are few highlighted functions of Common Language Runtime

### Common Language Runtime
- It is responsible for bringing the app to life and managing the resources while exectuing the app.
- It is also responsible for the tearing down the application or when it hits an unrecoverable state.
- It tracks the memory that is being used and cleans up once it is finished exectuing. 
- It performs virtulization of the apps by converting to -64 or 32 bit and such.
- Supports different languages like F# and many more. Also takes into account of various platforms (Linux/Mac)

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
_This is an cs file which is not exectuable(exe/dll) version. In order to do that we can use cmd prompt to generate [exe file 
which will be gives us the desired output](https://stackoverflow.com/questions/21476588/where-is-developer-command-prompt-for-vs2013)_

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

The syntax and program structure is very similar to any Object oriented language avaliable out there.  C# also wraps many day-to-day functionality with classes and interfaces which prevents writing any additional code that isn't necessary. For instance Arrays were provided with various methods including sort,ordering and even bubble sorts. 

##### Breakpoints and Debugging
Visual Studio provides us with wide array of tools to debug and examine our application. We can set breakpoints debug the current state of variables at given point of time. This helps us in understanding flow of our logic and state of variables and how they respond to changes by the user.
![Debug](https://user-images.githubusercontent.com/8538409/29741918-9d52856a-8a93-11e7-8007-8351c3d64bdc.PNG)
We also added feature of conditional breakpoints which you might of guessed will break the flow only if it satisifiyes given condition. We can also step-in,step-out and step-over while traversing through our application.

[For more about debugging](https://docs.microsoft.com/en-us/dotnet/core/tutorials/debugging-with-visual-studio?tabs=csharp)
