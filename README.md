# JS-Functions
Many great JavaScript functions, as examples. Please visit.

# Difference between Regular functions and Arrow functions

In JavaScript, functions are essential building blocks. ES6 introduced Arrow Functions, offering a shorter syntax and simpler this handling. While both regular and arrow functions achieve similar tasks, they differ in syntax, behavior, and usage.

Regular function
A regular function is defined using the function keyword and can have its own this, arguments, and prototype.

```
// Defining a regular function
function greet(name) {
    console.log('Hello, ' + name + '!');
}

// Calling the function
greet('Geek');
```

Output

```
Hello, Geek!
```

Syntax

```
let x = function function_name(parameters){   // body of the function};
```

Main Features
1. Access arguments
In regular functions, you can access all passed arguments using the arguments object, which is an array-like object containing each argument passed to the function.

```
function showArgs() {
    console.log(arguments);
}
showArgs(1, 2, 3);
```

Output

```
[Arguments] { '0': 1, '1': 2, '2': 3 }
```

2. Duplicate named parameters

In regular functions, duplicate named parameters are allowed but not recommended. The last occurrence of the parameter overwrites previous ones, and only its value is used.

```
function example(a, b, a) {
    console.log(a, b);
}
example(1, 2, 3);
```

Output

```
3 2
```

3. Hosting

In regular functions, function declarations are hoisted to the top of their scope, allowing them to be called before they're defined in the code.

```
greet(); // Output: Hello Geeks!

function greet() {
    console.log('Hello Geeks!');
}
```

Output

```
Hello Geeks!
```

4. Using this keyword

In regular functions, this refers to the object that calls the function (runtime binding). Its value can vary based on how the function is called (method, event, or global).

```
const obj = {
    name: 'Geeks',
    greet: function() {
        console.log(this.name);
    }
};
obj.greet();
```

Output

```
Geeks
```

5. Using new keyword

Regular functions can be used as constructors with the new keyword, allowing the creation of new object instances. The new keyword sets this to the new object inside the function.

```
function Person(name) {
    this.name = name;
}
​
const p = new Person('Geeks'); // Creates a new Person object
console.log(p.name);
```

Output

```
Geeks
```

Arrow function
Arrow functions in JavaScript are a concise way to define functions using the => syntax. They do not have their own this context, instead inheriting it from the surrounding scope. Arrow functions also lack their own arguments object and are ideal for shorter functions and callbacks.

```
// Defining an arrow function
const greet = (name) => {
    console.log(`Hello, ${name}!`);
};
​
// Calling the function
greet('Geeks');
```

Output

```
Hello, Geeks!
```

Syntax

```
let x = (parameters) => {
    // body of the function
};
```

Main Features
1. Access arguments

Arrow functions do not have their own arguments object. To access arguments in arrow functions, use rest parameters (...args) to collect all arguments into an array.

```
const showArgs = (...args) => {
    console.log(args);
};
showArgs(1, 2, 3);
```

Output

```
[ 1, 2, 3 ]
```

2. Duplicate named parameters

Arrow functions do not allow duplicate named parameters, even in non-strict mode, and will throw a syntax error if duplicates are present. Always use unique parameter names in arrow functions.

```
const example = (a, b, a) => {
    console.log(a);
}; 
// SyntaxError: Duplicate parameter name not allowed in this context
```

Output:
SyntaxError: Duplicate parameter name not allowed in this context
3. Hoisting

Arrow functions are not hoisted like regular function declarations. They are treated as variables, so they cannot be called before being defined due to the temporal dead zone.

```
greet(); // ReferenceError: Cannot access 'greet' before initialization
​
const greet = () => {
    console.log('Hello!');
};
```

Output:

```
ReferenceError: Cannot access 'greet' before initialization
```

4. Using this keyword

In arrow functions, this is lexically inherited from the surrounding scope, not the function itself. It maintains the this value from where the arrow function is defined.

```
const obj = {
    name: 'Geeks',
    greet: () => {
        console.log(this.name);
    }
};
obj.greet(); // Output: undefined (inherited from outer scope)
```

Output

```
undefined
```

5. Using new keyword

Arrow functions cannot be used as constructors and do not support the new keyword. Attempting to use new with an arrow function will result in a TypeError.

```
const Person = () => {};
const p = new Person(); // TypeError: Person is not a constructor
```

Output:

```
TypeError: Person is not a constructor
```

Difference table of Regular functions and Arrow functions

<table>
  <tr>
    <th>Feature</th>
	<th>Regular Functions</th>
	<th>Arrow Functions</th>
  </tr>
  <tr>
    <td>Syntax</td>
	<td>Defined using the function keyword.</td>
    <td>Uses concise => syntax.</td>
  </tr>
  <tr>
    <td>this Binding</td>
	<td>this depends on the calling context.</td>
	<td>Inherits this from the surrounding scope.</td>
  </tr>
  <tr>
    <td>Arguments Object</td>
	<td>Has its own arguments object.</td>
	<td>Does not have its own arguments object.</td>
  </tr>
  <tr>
    <td>Constructor Usage</td>
	<td>Can be used as a constructor with new.</td>
	<td>Cannot be used as a constructor.</td>
  </tr>
  <tr>
    <td>Hoisting</td>
	<td>Function declarations are hoisted.</td>
	<td>Not hoisted; behaves like variables.</td>
  </tr>
  <tr>
    <td>Implicit Return</td>
	<td>Requires return for returning values.</td>
	<td>Supports implicit return for single expressions.</td>
  </tr>
  <tr>
    <td>Methods as Object Properties</td>
	<td>Suitable for object methods with proper this.</td>
	<td>Not suitable for methods due to lexical this.</td>
  </tr>
</table>  
  
  
