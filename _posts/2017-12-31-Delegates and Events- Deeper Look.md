---
layout: post
title:  "Delegates"
categories: default
tags: test syntax
---
#### Delegate
We are going to see how delegate works with help of our gradebook class which we created in initial stages. Our objective is to notify 
user whenever there is change of our name of the gradebook.

We are creating class called NameChanged which contains declaration for our delegate. Then we are going to reference this in
our gradebook class and whenever our setter is trying to change the value of our gradebook we will call our delegate which in turns 
call our function to display change of names.

###### Inside file NameChanged.cs

```
public delegate void NameChanged(string oldString, string newString)
```
###### Inside GradeBook.cs
```
public NameChanged nameChanged;
public string Name
{
get 
  {
    return _name
  };
 set
 {
    if(!String.IsNullorEmpty(value))
      {
        if(_name!=value)
        {
          nameChanged(_name,value);
        }
        _name=value;
      }
 }
}
```
Invoking delegate by variable `nameChanged`. This must be calling an function which tells us the old name and new name for the object
of the class.  Now every time this function will be called to notify us of the name change 

```
book.NameChanged= new NameChanged(OnCallName);

...

static void OnCallName(string , string)
{
  console.WriteLine(oldName+newName);
}

```
#### Events

###### TBU
