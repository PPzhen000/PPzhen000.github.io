---
layout: post
title:      "Some JavaScript Basics"
date:       2018-12-24 01:27:37 -0500
permalink:  some_javascript_basics
---


JavaScript is a versatile and expressive language that is powerful for web development. When first start out learning this popular language, it is very beneficial to know some of the peculiarities of JavaScript like hoisting, scope, and context.

#### Hoisting 

Hoisting is, for many people starting to write JS, an unknown behavior of JavaScript that by default moves all variable declarations to the top of the current scope. 

```
Example 

var x = 5; 
console.log(x + " " + y);
var y = 3 
``` 

This will produce `5 undefined` in the console. 

With hoisting in JavaScript, the above example is the same as : 
```
var x = 5; //declare x and assign 5 to x
var y; // declare y
console.log(x + " " + y);
y = 3 ;  //assign 3 to y
``` 
y is undefined in the last example because the declaration of y is hoisted to the top and has an `undefined` value before it's used in `console.log(x + " " + y);`  followed by reassigning a value of 3 to y. 
It is always a good rule to declare all variables, assign values to each variables at the top. 

Note: Variables introduced with `let` and `const` are not affected by hoisting. 

#### Scope 

“Scope” in JavaScript refers to the availability of a variable to a piece of code at a given time. There are two type of scope:

* Local scope - Variables declared inside a JS function are LOCAL to the function and can only be accessed inside the function it was declared. 
* Global scope - The global scope is the complete JS environment. Global variables are those declared outside of a block or are declared without `var`. 

Codes outside the scope in which a variable was defined does not have access to the variable.

#### The `this` keyword 

How to determine the value of `this`? 
- Put a `debugger` in wherever you want to find out the value of `this` and ask the console. 

LOL... JK...

In JavaScript, `this` is a special keyword that is used within methods to refer to the object, also called parent object, on which the method is being invoked. 

```
For example:

let person = {
  firstName: "John",
  lastName : "Doe",
  foo : function() {
    console.log(this); 
  }
};
``` 

If you call `person.foo()`,  the person object, `{firstName: "John", lastName: "Doe", foo: ƒ}` will be logged in the console. `this` in this case, in the person object. 

However, when we invoke functions within functions, `this` becomes the global object.
If the function is invoked using `call()` or `apply()`, `this` will be the first argument passed to call/apply. 
If the function being invoked was created using `bind()`, `this` will be the first argument that was passed to bind at the time the function was created.

Note: when `this` is used in arrow function expression, it refers to the originating context as arrow functions don't bind their own `this`. 

#### Something about ES6... `let` and `const` vs. `var` 

The differences between the three:

| Keyword | Scope | Hoisting | Can Be Reassigned | Can Be Re-declared | 
| ---------- | --------| ---------- | ---------------------- | ---------------------- |
| `var` | Function scope | Yes | Yes | Yes | 
| `let` | Block scope | No | Yes | No |
| `const` | Block scope | No | No | No | 

General Rules:
* Use `const` as much as possible 
* Use `let` in the case of loops and reassignment
* Use `var`? AVOID it as much as possible 

