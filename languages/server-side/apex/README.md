
# Credit

The following style guide is taken from [here](https://github.com/PolarisProject/salesforceStyleGuide/blob/master/Apex%20style%20guide.md), with some modifications.

# Apex Style Guide

- [Nomenclature](#nomenclature)
  + [Namespaces](#namespaces)
  + [Classes & Interfaces](#classes--interfaces)
  + [Methods](#methods)
  + [Fields](#fields)
  + [Parameters](#parameters--parameters)
- [Declarations](#declarations)
  + [Access Level Modifiers](#access-level-modifiers)
  + [Fields & Variables](#fields--variables)
  + [Classes](#classes)
  + [Interfaces](#interfaces)
- [Brace Style](#brace-style)
- [Switch Statements](#switch-statements)
- [Constructor](#Constructor)
- [SOQL](#SOQL)

## Nomenclature

On the whole, naming should follow Java standards.

### Namespaces

Namespaces are not supported (though they might be [in the future](https://trailblazer.salesforce.com/ideaview?id=08730000000Bp88AAC)).

### Classes & Interfaces

Classes and interfaces are written in **PascalCase**. For example `RadialSlider`. 

### Methods

Methods are written in **camelCase**. For example `doSomething()`. 

### Fields

All fields are written **camelCase**.  

For example:

```apex
public class MyClass {
    public integer publicField;
}
```

**AVOID:**

```apex
private integer _myPrivateVariable
```

**PREFER:**

```apex
private integer myPrivateVariable
```

### Properties

All properties are written in **camelCase**. For example:

```apex
public integer pageNumber {
    get { return pageNumber; }
    set { pageNumber = value; }
}
```

### Parameters

Parameters are written in **camelCase**.

**AVOID:**

```apex
void doSomething(Vector3 Location)
```

**PREFER:**

```apex
void doSomething(Vector3 location)
```

Single character values are to be avoided except for temporary looping variables.



## Declarations

### Access Level Modifiers

Access level modifiers should be explicitly defined for classes, methods and member variables.

### Fields & Variables

Prefer single declaration per line.

**AVOID:**

```java
String username, twitterHandle;
```

**PREFER:**

```apex
string username;
string twitterHandle;
```

### Classes

Exactly one class per source file, although inner classes are encouraged where scoping appropriate.

### Interfaces

All interfaces should be prefaced with the letter **I**. 

**AVOID:**

```apex
RadialSlider
```

**PREFER:**

```apex
IRadialSlider
```


## Brace Style

All braces are written in the Java convention:
Open braces should have a space before them and not a newline.  The matching close brace should line up with the start of the opening brace's line

**AVOID:**
```apex
class MyClass
{
    void DoSomething()
    {
        if (someTest)
        {
          // ...
        }
        else
        {
          // ...
        }
    }
}
```

**PREFER:**
```apex
class MyClass {
    void doSomething() {
        if (someTest) {
          // ...
        } else {
          // ...
        }
    }
}
```


Conditional statements are always required to be enclosed with braces,
irrespective of the number of lines required.

**AVOID:**

```apex
if (someTest)
    doSomething();  

if (someTest) doSomethingElse();
```

**PREFER:**

```apex
if (someTest) {
    doSomething();
}  
if (someTest) {
    doSomethingElse();
}
```
## Switch Statements

Switch-statements come with `default` case by default (heh). If the `default` case is never reached, be sure to remove it.

**AVOID:**  
  
```apex
switch (variable) {
    case 1:
        break;
    case 2:
        break;
    default:
        break;
}
```

**PREFER:**  
  
```apex
switch (variable) {
    case 1:
        break;
    case 2:
        break;
}
```

## Constructor
When creating an SObject, generally prefer the Apex-specific syntax wherein all fields can be initialized from the constructor.  When using this syntax, choose a different line for each property so that diff-ing and versioning is easier.

Example:

```apex
Contact contact = new Contact(
    RecordTypeId = CONTACT_RECORDTYPE_ID,
    FirstName = firstName,
    LastName = surname,
    MailingCountry = DEFAULT_COUNTRY
);
```


## SOQL

- SOQL keywords (e.g., `SELECT`, `WHERE`, `TODAY`) should always be written in `ALL CAPS`.  
- Each clause of the SOQL Query should be on its own line so that finding what changed in a diff is easier.  That is, each `SELECT`, `FROM`, `WHERE`, etc.,  should start a new line. 
- Long lists of fields in a `SELECT` clause should be ordered in a logical manner and broken to fit within page width, with subsequent lines aligned with the first field.
- Relationship-query should be on its own line, aligned with the first field of the top `SELECT`.  
- Always select `Id`, and always select it first.
- The SOQL's brackets and parantheses should conform to Java style.

Example:

**Avoid:**
```apex
String typeToSelect = 'abcde';
List<Contact> contacts = [SELECT Id, FirstName, LastName, Phone, Email, MailingCity, 
                          (SELECT Id, ActivityDate, Origin, Type, WhatId, What.Name
                          FROM ActivityHistories
                          WHERE Type = :typeToSelect)
                          FROM Contact
                          WHERE CreatedDate >= TODAY];
```

**Prefer:**
```apex
String typeToSelect = 'abcde';
List<Contact> contacts = [
  SELECT Id, FirstName, LastName, Phone, Email, MailingCity, (
         SELECT Id, ActivityDate, Origin, Type, WhatId, What.Name
         FROM ActivityHistories
         WHERE Type = :typeToSelect
  )
  FROM Contact
  WHERE CreatedDate >= TODAY
];
```
