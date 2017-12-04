---
layout: post
title:  "Methods"
categories: Introduction
tags: Methods, Feilds 
---

Methods
- Defines behaviour
- Default access modifiyer is private, return type is void and can contain zero or more parameters
- Method Signature consists of method name, number of parameters, type of that parameters.
- _Return Type_ is not a part of the method signature.
- _params_ is an object array of any type which can be used to pass the number of parameters when the exact number is not known.

[To Know more about method signature](https://stackoverflow.com/questions/8808703/method-signature-in-c-sharp)

```
public static void WriteResult(float number, params float[] result)
{
 foreach (float f in result)
  {
    Console.WriteLine("Number: "+f);
  }
}

WriteResult(12.2f, 1.3f, 1.43f);
WriteResult(1.3f, 1.1f, 1.2f, 1.4f);

```
Both of the above methods will call `WriteResult`. 

#### Feilds

- Feilds define the variables of the class
- It also defines the state or data that is held by the part of the object

```
private readonly string _name;

public Animal(string name)
{ _name=name;}

```

This means name can only used by the object of the class. `readonly` denotes that it can be initialized only inside the constuctor
and not in any part of the object.

#### Properties

- It is similar to the feild as it controls the state and data of the objects. But the difference is that is has properties that allows
to control when some writes/reads are performed on the data.

```
public string Name
{
 get{ return _name};
 
 set
 {
  if(! String.IsNullorEmpty(value))
  { 
    _name=value;
  }
 }

}
```

The above property will not allow name to be set to null or empty. Properties are more useful for serlization, XML, JSON where data
binding is used.

#### Events

Events helps us in keeping tracking of the components which might do intersting things at unpreditable times. Events allow object to
announce that some thing has happened. It will announce these events to whomever subscribes for that events. More on that in forth 
coming topics.


#### Delegates

In order to understand more about events and its subscribers we need delegates. Delegates are used to refernce a method-variable which
references the method.

Variable that encapsulates executable code that will invoke code with optional arguments which ias again jsut like a method.

A delegate is a type that references a method. It is dedicated to refernece method.

```
public delegate void write(string message);

public Class Logger
{
public void WriteMessage(string message)
 {
   Console.WriteLine(message);
 }
 
}

...

Logger log = new Logger();

Write writer= new Write(log.WriteMessage); // This is making writer as an executable variable

writer('Sucess'); // This will invoke the delegate
```

Here writer delegate can only be used by method which returns void and takes string as a parameter.
