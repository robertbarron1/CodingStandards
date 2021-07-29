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

## Formatting

**Do vertically allign curly braces on separate lines.**

``` c#
if (NumberOfRecords > 100)
{
    NumberOfRecords = 0;
}
```
