## Table of Contents

- [Spacing](#spacing)
  + [Indentation](#indentation)
  + [Blocks](#blocks)
  + [Line Length](#line-length)
- [Brace Style](#brace-style)
- [Return Statement](#return-statement)

## Spacing

A single space is required following a control statement.

**AVOID:**

```csharp
if(someTest)
{
   // ...
}

while(someTest)
{
   // ...
}
```

**PREFER:**

```csharp
if (someTest)
{
   // ...
}

while (someTest)
{
   // ...
}
```

### Indentation

Indentation should be done using **tab** — never spaces.  

#### Blocks

Indentation for blocks uses **1 tab** for optimal readability.

### Line Length

Lines should be no longer than **180** characters long.

## Return Statement

`return` statement should appear once in a function, on its last line.

**AVOID:**

```javascript
function func() {
  // ...
  if (someTest) {
    return someResult;
  } else (someTest) {
    return otherResult;
  }
  return anotherResult;
}
```

**PREFER:**

```javascript
function func() {
  // ...
  var result = someDefault;
  if (someTest) {
    result = someResult;
  } else (someTest) {
    result = otherResult;
  }
  return result;
}
```

