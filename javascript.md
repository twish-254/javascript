# Understanding Variables In Javascript

## Introduction
Variables are a way for programmers to name a value to reuse it, update it, or keep track of it.
In this article, we will go through naming variables correctly, declaring them, and initializing them.
We are also going to touch on the scope of variables to ensure that we understand variables fully.

## Prerequisites
To follow along with this tutorial, you need a web browser. You can get Google Chrome [here](https://www.google.com/chrome/)

### Accessing the JavaScript Console
We will use the JavaScript console to execute the JavaScript code in this tutorial. To open it in Google Chrome, press `Ctrl + Shift + J` on Windows and Linux and `Cmd + Option + J` in Mac OS.

### Understanding the scope Of variables
Scope determines the accessibility of variables, objects, and functions from different parts of your code.
In JavaScript, there are two types of scope, that is:
1. Global scope
2. Local scope
<!-- this should be an ordered list  -->
**1. Global scope**

When a variable is *globally scoped*, it means it is available anywhere in your program. 
If you declare a variable outside of a function, JavaScript adds it to the global scope.

Example:
```JavaScript
var car = 'sedan'
console.log(car);//sedan

function getCar(){
    console.log(car);//car is accessible here
}

getCar();//sedan

```
In the above example, the variable `car` can be accessed from both inside and outside the function because it is globally scoped.

**2. Local scope**
Variables declared within a function become Local to the function and are considered in the corresponding local scope.
The local scope can be subdivided into:
- function scope
- block scope

**a)Function scope**
When you say a variable is function scoped, it means that the variable defined within the function is not accessible from outside the function.
*var* is the keyword to define a function scoped variable.

``` javascript
function food(){
    var favouriteFood ='burger';
    console.log('inside function: ',favouriteFood);
}

food(); //inside function: burger
console.log(favouriteFood);  //error: favouriteFood is not defined
``` 
Once you run the above code, it produces an error message saying `favouriteFood is not defined`.
This is because you could not access the variable `favouriteFood` outside of the function it was defined in.

**b)Block scope**
A block is any space between an opening and closing curly brackets. 
A block in JavaScript is denoted by curly braces {}.
The `if...else, do...while` and `for` loop statements create blocks.
When a variable is block-scoped, it means that it exists inside the block, it was defined.
```javascript
function car(){
    if(true){
        var carType1 = 'coupe';//exist in function scope
        const carType2 = 'hatchback';//exist in block scope
        let carType3 = 'convertible';//exist in block scope

    }
    console.log(carType1);
    console.log(carType2);
    console.log(carType3);
}

car();
//result:
//coupe
//ReferenceError: carType2 is not defined
//ReferenceError: carType3 is not defined
```

### Naming Variables In JavaScript
Before you start declaring variables, you should first learn how to name them first.
A variable name should accurately identify your variable.
Below are some of the rules that one should follow to ensure that your JavaScript code is easy to understand and work with.
- Variable names should not have spaces.
- Variable names must begin with a letter, an underscore(_) or a dollar sign($).
- variable names are case-sensitive. This means *car_TYPE* is treated as an entirely different variable than one named *car_type*
- Variable names must contain only letters, numbers, underscores, or dollar signs.
- You can't use any JavaScript *reserved words* as a variable name.


### Declaring variables using the keyword `var`
The var statement declares a function-scoped or globally-scoped variable, optionally initializing it to a value.
Example:
```javascript
var x = 2;

if (x === 2) {
  var x = 3;

  console.log(x);
  // expected output: 3
}

console.log(x);
//expected output: 3
```
To declare a variable name, you use the *var* keyword followed by the variable name.
Example:
```javascript
var favouriteThing;
```
Upon declaring a variable, you should assign the variable a value such as a string or a number.
Example:
```javascript
var favouriteThing;
favouriteThing = "Icecream!";
```
Declaring a variable and at the same time initializing it is also possible using the following syntax;
```javascript
var favouriteThing = "Icecream";
```

You can also declare two or more variables using one statement, and each declaration is separated by a comma (,).
Example:
```javascript
var favouriteThing = "Icecream" ,bestMovie = "Code Eight";
```


### Declaring variables using the keyword `let`
The keyword `let` can be used to declare one or more variables. 
The main difference between keywords `var` and `let` is that variables declared using `let` are block-scoped, while `var` is both globally-scoped and function scoped.
Example:
```javascript
var a = 20, b = 10;
{
  let tmp = a;
  a = b;
  b = tmp;
}
console.log(tmp); // ReferenceError: tmp is not defined
```
In the above example, `tmp` variable only exists inside the block, and referencing it outside the block gets you a ` ReferenceError: tmp is not defined`.

### Declaring variables using the keyword  `const`
The keyword `const` works the same as the `let` keyword. The only difference is that the variable declared using the keyword `const` must be initialized immediately and with a value, and that value **can't be redeclared**.

Example:
```javascript
const p = 3.14;
p = 3.145;//SyntaxError: Identifier 'p' has already been declared
```
The error generated, `SyntaxError: Identifier 'p' has already been declared`, informs you that you can't change the value of `p`. 
Using the `const` keyword lets you declare variables or constants that should not be changed in your code.

### Conclusion
In summary, we have learnt about variables, how they are declared and used.
We have gone through different types of variable scopes.  At first, all this may not be very clear, especially if you are a beginner, but you will get there with practice. 