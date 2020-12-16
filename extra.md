## Undefined vs. undeclared variables
An undefined variable is a variable that has been declared but not assigned a value and due to this the variable uses the undefined as the initial value. 
In contrast, an undeclared variable is the variable that has not been declared.
See the following example:

```javascript
var message;
console.log(message); // undefined
console.log(counter); // ReferenceError: counter is not defined
```
In this example, the message variable is declared but not initialized therefore its value is
undefined whereas the counter variable has not been declared hence accessing it causes
a ReferenceError .

## Global and local variables
In JavaScript, all variables exist within a scope that determines the lifetime of the variables
and which part of the code can access them.
JavaScript mainly has global and function scopes . ES6 introduced a new scope called block scope

In JavaScript, you define a function as follows:
function functionName() {
// logic
}
and call the function using the following syntax:
functionName();

The following example defines a function named say that has a local variable named
message .
```javascript
function say() {
var message = "Hi";
return message;
}
```
The message variable is a local variable. In other words, it only exists inside the function.
If you try to access the message outside the function as shown in the following example, you
will get a ReferenceError because the message variable was not defined:
```javascript
function say() {
var message = 'Hi';
}
console.log(message); // ReferenceError
```

Variable shadowing
See the following example:
```javascript
// global variable
var message = "Hello";
function say() {
// local variable
var message = 'Hi';
console.log(message); // which message?
}
say(); // Hi
console.log(message); // Hello
```
In this example, we have two variables that share the same name: message . The first
message variable is a global variable whereas the second one is the local variable.

Inside the say() function, the global message variable is shadowed. It cannot be accessible
inside the say() function but outside of the function. This is called variable shadowing.
Accessing global variable inside the function
See the following example:
// global variable
var message = "Hello";
function say() {
// local variable
message = 'Hi';
console.log(message); // which message?
}
say(); // Hi
console.log(message); // Hi
In this example, we define a global variable named message . In the say() function, we
reference the global message variable by omitting the var keyword and change its value
to a string of Hi .
Although it is possible to refer to a global variable inside a function, it is not recommended.
This is because the global variables are very difficult to maintain and potentially cause much
confusion.
Non-strict mode
The following example defines a function and declares a variable message . However, the
var keyword is not used.
function say() {
message = 'Hi'; // what?

console.log(message);
}
say(); // Hi
console.log(message); // Hi
When you execute the script, it outputs the Hi string twice in the output.
Because when we call the say() function, the JavaScript engine looks for the variable
named message inside the scope of the function.
As a result, it could not find any variable declared with that name so it goes up to the next
immediate scope which is the global scope in this case and asks whether or not the message
variable has been declared.
Because the JavaScript engine couldn’t find any of global variable named message so it
creates a new variable with that name and adds it to the global scope.
strict mode
To avoid creating a global variable accidentally inside a function because of omitting the var
keyword, you use the strict mode by adding the "use strict"; at the beginning of the
JavaScript file (or the function) as follows:
"use strict";
function say() {
message = 'Hi'; // ReferenceError
console.log(message);
}
say(); // Hi
console.log(message); // Hi 

From now on, you should always use the strict mode in your JavaScript code
to eliminate some JavaScript silent errors and make your code run faster.
JavaScript variable hoisting
When executing JavaScript code, the JavaScript engine goes through two phases:
1. Parsing
2. Execution
In the parsing phase, The JavaScript engine moves all variable declarations to the top of the
file if the variables are global, or to the top of a function if the variables are declared in the
function.
In the execution phase, the JavaScript engine assigns values to variables and execute the
code.
Hoisting is a mechanism that the JavaScript engine moves all the variable declarations to the
top of their scopes, either function or global scopes.
If you declare a variable with the var keyword, the variable is hoisted to the top of its
enclosing scope, either global or function scope.
As a result, if you access a variable before declaring it, the variable evaluates to undefined .
See the following example:
```javascript
console.log(message); // undefined
var message;
```
The JavaScript engine moves the declaration of the message variable to the top, so the
above code is equivalent to the following:
```javascript
var message;
console.log(message); // undefined
```
If there were no hoisting, you would get a ReferenceError because you referenced to a
variable that was not defined.
See another example:
console.log(counter);
var counter = 100;
The JavaScript engine moves only the declaration of the variables to the top. However, it
keeps the initial assignment of the variable remains intact. As a result, the code above is
equivalent to the following code:
```javascript
var counter;
console.log(counter); // undefined
counter = 100;
The hoisting uses redundant var declarations without any penalty:
var counter;
var counter;
counter = 1;
console.log(counter); // 1
```