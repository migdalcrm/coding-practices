# Credit 

The following style guide is taken from [here](https://github.com/spatie/javascript-styleguide/blob/master/README.md), with some modifications.

# JavaScript Style Guide

- [Spacing and Indentation in Functions and Control Statements](#spacing-and-indentation-in-functions-and-control-statements)
- [Spacing and Indentation in Objects and Arrays](#spacing-and-indentation-in-objects-and-arrays)
- [Quotes](#quotes)
- [Multi Line Strings](#multi-line-strings)
- [String Interpolation](#string-interpolation)
- [Semicolons](#semicolons)
- [Variable Assignment](#variable-assignment)
- [Variable Names](#variable-names)
- [Function Keyword vs. Arrow Functions](#function-keyword-vs-arrow-functions)
- [If IE11 Support Is Not Needed](#if-ie11-support-is-not-needed)
  - [Arrow Function Parameter Brackets](#arrow-function-parameter-brackets)
  - [Object and Array Destructuring](#object-and-array-destructuring)

## Spacing and Indentation in Functions and Control Statements

Code must be indented with 1 tab.

```js
// Good
function greet(name) {
	return `Hello ${name}!`;
}

// Bad, only 2 spaces.
function greet(name) {
  return `Hello ${name}!`;
}
```

When it comes to spaces around symbols or keywords, the rule of thumb is: add them. 

```js
// Good
if (true) {
    // ...
} else {
    // ...
}

// Bad, needs more spaces.
if(true){
    // ...
}else{
    // ...
}
```

Infix operators need room to breath.

```js
// Good
const two = 1 + 1;

// Bad, needs more spaces.
const two = 1+1;
```

Braces should always be on the same as it's corresponding statement or declaration (known as *the one true brace style*).

```js
// Good
if (true) {
    // ...
}

// Bad
if (true)
{
    // ...
}
```

Named functions don't need a space before their parameters. Anonymous ones do.

```js
// Good
function save(user) {
    // ...
}

// Bad, no space before the parameters.
function save (user) {
    // ...
}
```

```js
// Good
save(user, function (response) {
    // ...
});

// Bad, anonymous functions require a space before the parameters.
save(user, function(response) {
    // ...
});
```

### Spacing and Indentation in Objects and Arrays

Objects and arrays require spaces between their braces and brackets. Arrays that contain an object or another array mustn't have a space between the brackets. Multiline objects and arrays require trailing commas.

```js
// Good
const person = { name: 'Sebastian', job: 'Developer' };

// Bad, no spaces between parentheses.
const person = {name: 'Sebastian', job: 'Developer'};
```

```js
// Good
const person = {
    name: 'Sebastian',
    job: 'Developer',
};

// Bad, no trailing comma.
const person = {
    name: 'Sebastian',
    job: 'Developer'
};
```

```js
// Good
const pairs = [['a', 'b'], ['c', 'd']];
const people = [{ name: 'Sebastian' }, { name: 'Willem' }];

// Bad, no extra spaces if the array contains arrays or objects.
const pairs = [ ['a', 'b'], ['c', 'd'] ];
const people = [ { name: 'Sebastian' }, { name: 'Willem' } ];
```

### Quotes

Use single quotes. 

```js
// Good
const company = 'Spatie';

// Bad, single quotes can be used here.
const company = "Spatie";

// Bad, single quotes can be used here.
const company = `Spatie`;
```
### Multi Line Strings

Don't use `+`. Instead, use `\` at line end.

```js
// Good
function getMessage() {
    return 'this is a very long message that should\
	    be continued in a separate line';
}

// Bad, don't use +
function getMessage(name) {
    return 'this is a very long message that should' +
	    'be continued in a separate line';
}
```

### String Interpolations

Don't use `+`. Instead, use template literals (if IE11 support is not required) or use a string formatting implemention.

```js
// Good
function greet(name) {
    return `Hello {name}!`;
}

// Bad, don't use +
function greet(name) {
    return 'Hello ' + name + '!';
}
```

### Semicolons

Always.

### Variable Assignment
- Use `const` to indicate that a variable will not be reassigned.
- Use `let` instead of `var` if IE11 support is not needed.

### Variable Names

Variable names shouldn't be abbreviated.

```js
// Good
function saveUser(user) {
    localStorage.set('user', user);
}

// Bad, it's hard to reason about abbreviations in blocks as they grow.
function saveUser(u) {
    localStorage.set('user', u);
}
```

##  If IE11 Support Is Not Needed

### Function Keyword vs. Arrow Functions

Function declarations should use the function keyword.

```js
// Good
function scrollTo(offset) {
    // ...
}

// Using an arrow function doesn't provide any benefits here, while the
// `function`  keyword immediately makes it clear that this is a function.
const scrollTo = (offset) => {
    // ...
};
```

Terse, single line functions can also use the arrow syntax. There's no hard rule here.

```js
// Good
function sum(a, b) {
    return a + b;
}

// It's a short and simple method, so squashing it to a one-liner is ok.
const sum = (a, b) => a + b;
```

```js
// Good
export function query(selector) {
    return document.querySelector(selector);
}

// This one's a bit longer, having everything on one line feels a bit heavy.
// It's not easily scannable unlike the previous example.
export const query = selector => document.querySelector(selector);
```

Higher order functions can use arrow functions if it improves readability.

```js
function sum(a, b) {
    return a + b;
}

// Good
const adder = a => b => sum(a, b);

// Ok, but unnecessarily noisy.
function adder(a) {
    return b => sum(a, b);
}
```

Anonymous functions should use arrow functions.

```js
['a', 'b'].map(a => a.toUpperCase());
```

Unless they need access to `this`.

```js
$('a').on('click', function () {
    window.location = $(this).attr('href');
});
```

> Try to keep your functions pure and limit the usage of the `this` keyword!


### Arrow Function Parameter Brackets (only if IE11 is not needed)

An arrow function's parameter brackets must be omitted if the function is a one-liner.

```js
// Good
['a', 'b'].map(a => a.toUpperCase());

// Bad, the parentheses are noisy.
['a', 'b'].map((a) => a.toUpperCase());
```

If the arrow function has it's own block, parameters must be surrounded by brackets.

```js
// Good, although according to this style guide you shouldn't be using an
// arrow function here!
const saveUser = (user) => {
    //
};

// Bad
const saveUser = user => {
    //
};
```

If you're writing a higher order function, you should emit the parentheses even if the returned function has braces.

```js
// Good
const adder = a => b => {
    sum(a, b);
};

// Bad, looks inconsistent in this context.
const adder = a => (b) => {
    sum(a, b);
};
```

### Object and Array Destructuring

Destructuring is preferred over assigning variables to the corresponding keys.

```js
// Good
const [ hours, minutes ] = '12:00'.split(':');

// Bad, unnecessarily verbose, and requires an extra assignment in this case.
const time = '12:00'.split(':');
const hours = time[0];
const minutes = time[1];
```

Destructuring is very valuable for passing around configuration-like objects.

```js
function uploader({
    element,
    url,
    multiple = false,
    beforeUpload = noop,
    afterUpload = noop,
}) {
    // ...
}
```
