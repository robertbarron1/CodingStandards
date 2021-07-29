# C# Coding Standards

My personal C# coding standards developed over time at various jobs and with my personal projects.

## Classes

**Do use PascalCasing for class and method names.**

``` c#
public class Customer
{
    public void Create()
    {
    }
}
```

**Do use the prefix I for interfaces.**

``` c#
public class IDisposable
{
}
```

**Do use camelCasing for method arguments and local variables.**

``` c#
public class Customer
{
    private int id;

    public void Create(string name)
    {
    }
}
```

## Using Clauses

**Do order using clauses at the top of files in alphabetic order.**

``` c#
// Correct
using System;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using System.Xml.Serialization;

// Incorrect
using System;
using System.Xml.Serialization;
using System.IO;
using System.Text.RegularExpressions;
using System.Text;
```

**Do break up using clauses in three distinct groups (system, third party and internal), separated by a blank line**

``` c#
// Correct
using System;
using System.Text;

using NLog;

using MyInternalLibrary;

// Incorrect
using MyInternalLibrary;
using System;
using System.Text;
using NLog;
```

## Variables and Type names

**Do use predefined type names instead of system type names.**

``` c#
// Correct
string Name;
bool isOpen;
int NumberOfRecords;

// Incorrect
String Name;
Boolean isOpen;
Int32 NumberOfRecords;
```

**Do arrange large lists of variable declarations in alphabetical order.**

``` c#
public class Customer
{
    string Address;
    int Age;
    string City;
    string ID;
    string Name;
    string State;
    string ZipCode;
}
```

**Do place backing variables next to their properties.**

``` c#
// Correct
private string name;
public string Name
{
}

private int numberOfRecords;
public int NumberOfRecords
{
}

// Incorrect
private string name;
private int numberOfRecords;

public string Name
{
}

public int NumberOfRecords
{
}
```

## Formatting

**Do vertically allign curly braces on separate lines.**

``` c#
// Correct
if (NumberOfRecords > 100)
{
    NumberOfRecords = 0;
}

// Incorrect
if (NumberOfRecords > 100) {
    NumberOfRecords = 0;
}
```

**Do use null coalescing rather than if statements to protect from null values.**

``` c#
// Correct
return customer?.Address?.City;

// Incorrect
if (customer != null && customer.Address != null)
{
    return customer.Address.City;
}
else
{
    return null;
}
```
