---
layout: post
title:  "Assembely"
categories: Introduction
tags: Assembely
---

A .net assembely contains our complied code which can run under the supervision of CLR.  Assemblies are either exe files
in case of windows or dll files. exe file can be executed directly but the same can't be done with dll file. A dll file is a
dynamic link library which contains the code that be re-used multiple times for building different applications.  It contains meta data
about the type present init.

[Global assembely cache](https://docs.microsoft.com/en-us/dotnet/framework/app-domains/gac) contains the basic dll which can be used by all application. It is central location to store assemblies for a machine.  `MsCorLib` is avaliable under GAC which has functions like _console.writeLine(), dateTime_ etc,.

![](https://user-images.githubusercontent.com/8538409/30003035-7ba42d4a-90d5-11e7-8135-0a03d0f8e3ae.png)

Usually when our program is complied it gives output file in .exe.  We can change that by setting the output type to dll which is avaliable
under `Properties`.   Visual Studio also has option of viewing our metadata by pressing F12 key on the function. Here is an example which 
shows us functions avaliable under console

![](https://user-images.githubusercontent.com/8538409/30003183-22a00212-90d7-11e7-88ca-cd659446ce14.png)

#### Loading Assemblies

We can refernece the assembely that we are going to use by `using` statement. We also need to load the refernece files that are required
for the assembely.   At first `Speech` will not avaliable in `System` so we have add it our `References`.

```
using System.Speech.Synthesis;
. . .
. . .
  SpeechSynthesizer synth = new SpeechSynthesizer();
  synth.speak("Hello");
  } 
}
```
#### Unit Testing

In Visual Studio there is option for performing Unit testing which can determine if particular method passes or fails. This can be 
determined based on the conditions we provide inside the tests. The conditions can be implemented with built-in functions which are 
avaliable in .net framework.   Methods which has to tested should be avaliable under `[TestMethod]`  which is in a `[TestClass]`.  
```
Assert.areEqual(3,4) \\ Fail

Assert.areEqual(3,4) \\ Pass

```
These unit testing tools are avaliable under `Microsoft.SystemTools.TestTools.UnitTesting` namespace. We can use the access modifiyers
private,public and protected which are similar to one which we use in normal classes. 

We can use this feature to see if our grades are being calcuated correctly.  We have add this as separate project to our solution and we can add classes to it.

```
using Grades;
using Microsoft.VisualStudio.TestTools.UnitTesting;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Grades.Tests
{
    [TestClass]
    public class GradeBookTests
    {
        [TestMethod]
        public void ComputesHighestGrade()
        {
            GradeBook book = new GradeBook();
            book.AddGrade(10);
            book.AddGrade(90);

            GradeStatistics result = book.ComputeStatistics();
            Assert.AreEqual(90, result.HighestGrade);
        }

        [TestMethod]
        public void ComputesLowestGrade()
        {
            GradeBook book = new GradeBook();
            book.AddGrade(10);
            book.AddGrade(90);

            GradeStatistics result = book.ComputeStatistics();
            Assert.AreEqual(10, result.LowestGrade);
        }

        [TestMethod]
        public void ComputesAverageGrade()
        {
            GradeBook book = new GradeBook();
            book.AddGrade(91);
            book.AddGrade(89.5f);
            book.AddGrade(75);

            GradeStatistics result = book.ComputeStatistics();
            Assert.AreEqual(85.16, result.AverageGrade, 0.01);
        }
    }
}
```
There are few thing to notice here. We could see that we are using the same methods that were present in `GradeBook.cs` class. This is 
possible because we are using the entire solution as refernece here. Just like we did with `Speech` namespace we are referencing this solution.  

Next is each test function is above a `[TestMethod]` which helps visual studio to identify the test methods and 
builds it automatically whenever there is a change with solution.
```
[TestMethod]
        public void ComputesAverageGrade()
        { ..
          ..
 ```

In this case we have passed a number third parameter which allows us to specify the minumum variance that will accepted. 


`Assert.AreEqual(85.16, result.AverageGrade, 0.01);`

