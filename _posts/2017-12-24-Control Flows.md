---
layout: post
title:  "Control Flows"
categories: Introduction
tags: loops
---

Control Flows are branching and looping statement which helps us in deciding the flow of our program. As like other languages syntax of 
all control statments are similar. One other added feature in C# is the `for each` loops which helps us in Enumerating through an given collection.

Below are list of Control Flows in C#. We will take look at throwing, catching errors and handling them as well.

###### Branching

- If..Else/ Nested If..Else

###### Switching

- Switch Cases

###### Iteration

- For..Each
- For loop
- Do..While
- While

###### Jumping

- Break    - Statements after this won't be executed and it exits out of the loop.
- Continue - Statements after this won't be executed and it jumps to next iteration.
- Goto     - Jumps to the label provided and skips any code in between. 
- Return   - Returns values to a variable. Can also be used with Void but it can't return anything.
- Throw     

###### [Throwing](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/exception-handling)

- Used to raise an exception.

- Used when the program can't forward after a particular point.

- Every exception in C# is of known tyoe and hence it can help complier in working with the exception.

```
if(age==21)
{
    throw new ArgumentException("21 isn't a legal value");
}

// This an generic exception(ArgumentException) which tell us there is something wrong with the arguments.
```

- We can also track exceptions by using stack trace. It is not but an data structure that is build while executing the
    program.

- It helps us to know where the error got generated and it LineNumber etc.,

###### Handling

Handling exceptions helps us to exit from the program more gracefully then abrupt exit from the program. It is very advisible to using try..catch block
for handling any unexpected exits from the program. While throwning an exception will help us in narrowing down to issue it will not be an
fruiful experince for the user. 

When an exception is either thrown by the program or triggered by an unexpected input from the user complier will search for catch block and if it finds
then will catch the error which caused the exception and display it to the user. Else it has to break out the program and exit abruptly.

```
try
{
    ComputeStat();
}
catch(DivideByZeroException ex)
{
    Console.WriteLine(ex.Message);     // Default error messages from the exception
    Console.WritlLine(ex.StackTrace); // Not an user friendly message but helps in debugging
}
```
Catch block will invoked only when there is divide by zero exception

```

try
{
    Console.WriteLine("Enter a book name: ");
    book.Name = Console.ReadLine();
}

catch(ArgumentException ex)
{
    Console.WriteLine(ex);
}

```
We can also chain mutiple catch blocks which can be useful where we aren't possible to catch every exception. If that's the case then the most specific
ones must placed in first.  Catching `System.Exception` will handle all the cases expect for few cases. 

##### Finally

Finally code executes even when there isn't exception and it will always execute once the block completes. Its most common purpose is to clean up resources at the end. 
The only resource which is managed by .NET Runtime is memory. Many classes will have unmanaged resources which needs to be explicitily managed. It can be done with 
help of `IDisposable`. 
