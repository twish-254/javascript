## **Understanding Variables In Javascript**

## Introduction
 As a programmer interested in JavaScript language, variables are among the most important concepts you should have. In this article, we will learn all there is to know about variables that include how to declare the variables and initialize them to enable us to move forward with learning JavaScript. Variables are a way for programmers to name a value to reuse it, update it, or keep track of it.


## **Prerequisites**
As you start this tutorial, all you need is the chrome browser to access the console tab.

## **Accessing The Console Tab**
First things first, we need to access the console tab.
- Using the short cut Ctrl + Shift + J on Windows and Linux 
- If you are using MAC, you can use the following command Cmd + Option + J

## **Declaring Variables In JavaScript**

### Basic concepts
A certain way that a variable should be written below will show you some of the rules that should be followed when naming variables.
- Variables are written in lower camel cases, and the first letter of the name must be lower.  
eg
```javascript
carType
```
- Variables should always begin with a letter and not a number.
 eg
```javascript
firstHouse
```

- Variables are case sensitive, i.e., firstHouse is different from firstHOUSE
- Last but not least is that you should use exact names to describe the value being stored; this is because abbreviations may have a different meaning for each user, and also, in the long run, you might end up confusing yourself together.

### *Declaring var Keyword*
When using the var keyword, you are telling JavaScript that you will be declaring a variable.
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
var favouriteThing = "Icecream" ,
bestMovie = "Code Eight";
```
As we said earlier, a variable can store any data; it can store even numbers.
Example:
```javascript
var favouriteNumber = "2";
```
Even though variables can represent numbers, it is not recommended.

### *Declaring let keyword*
 *let* keyword can be used just as var to declare one or more variables.
The main difference between *var* and *let* is that variables declared using *let* are block-scoped, not function or globally scoped like *var* variable.
 A block is any space between an opening and closing curly brackets.
 A block in JavaScript is denoted by curly braces {}.
 Example: 
 The *if...else, do...while* and *for* loop statements create blocks.
 Example:
 ```javascript
 var a = 20, b = 10;
 {
   let tmp = a;
   a = b;
   b = tmp;
 }
 console.log(tmp); //ReferenceError
 ```
 The above example tmp variable only exists inside the block, and referencing it outside the block gets you a Reference Error.

### *Declaring the const variable*
*const* keyword works the same as the *let* keyword.
The only difference is that the variable you declare using the *const* keyword must be initialized immediately and with a value, and that value can't be changed.
By can't be changed, I mean it can't be redeclared.

Example:
```javascript
const p = 3.14;
p = 3.145;//TypeError:'code is read only.'
```
The error generated informs you that you can't change the value of *p*. 
Using the *const* keyword can help you write your code because you will receive an error message if you accidentally try to reassign a variable.

## **Understanding The Scope Of Variables**
Scope determines the accessibility of variables, objects, and functions from different parts of the code.
In JavaScript, there are two types of scope, that is:
- Local scope
- Global scope
- Block-level scope 

When a variable is *globally scoped*, it means it is available anywhere in your program; in other words, this is to say, if you declare a variable outside of a function, JavaScript adds it to the global scope.
Example:
```JavaScript
var firstName = "Ann";
funtion printName(){
  console.log(firstName)
}
printName()
```
In this example, we've created a function, printName, that will print the value of the name var, Ann.
This will be printed in your console because var was created outside of the function, meaning it is globally scoped.
Next, we are going to discuss the *locally scoped variables*.
First, let's go through an example.
Example:
```javascript
funtion printAge(){
  var age = 20
}
console.log(age)//year not defined
```
Can you the difference between the example above and the one I gave for globally scoped variables? The difference is the placement of the variable.
Once you run the above code, you get an error message *age not defined*; this is because var age is locally scoped or function-scoped. That is, it exists inside the function it was created in. 
The error occurs because we have no access to it outside the function, so we are trying to run our console.log.
In the long run of learning JavaScript, you will realize that it is more useful for you as a programmer to use function-scoped variables rather than global-scoped variables.
When a variable is block-scoped, it means that it exists in the block, it was defined.
Let go through an example using the const variable.
Example:
```javascript
var age = 26
If (age) {
const doubleAge = age + age
console.log(`Double your current age is ${yearPlusTwenty}`)
}
```
Now, type doubleAge into your console and hit enter. You should get an error, *double is not defined*. This is because const is block-scoped: it only exists in the block it was declared.
The doubleAge variable is *' trapped’* inside the two curly brackets it was declared in.

## **Conclusion**
In summary, we have learnt about variables, how they are declared and used.
We have gone through different types of variable scopes.
Variables can be declared using the *var, let* or *const* keywords. At first, all this may not be very clear, especially if you are a beginner, but you will get there with practice.
As a JavaScript programmer, make sure you build a strong foundation on *var, let*, and *const* because they will help you not only as you start your JavaScript career but throughout its entirety.