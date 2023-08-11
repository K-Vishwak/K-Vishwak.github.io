---
title: "JS IIFE - Immediately Invoked Function expression"
datePublished: Fri Jan 28 2022 06:59:44 GMT+0000 (Coordinated Universal Time)
cuid: ckyy220ot0bo42qs11ii10a9c
slug: js-iife-immediately-invoked-function-expression
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643353142969/MMTCsiB_0.png
tags: javascript, 100daysofcode, 2articles1week

---

Regular function in javascript is:

```
// function declaration
function myFunction() {
    console.log('I am normal JS function');
}

// function invocation
myFunction();
> I am normal JS function
```
Ok. What is `function expression`?

`Expression` - evaluate to a value.

```
const value = 1;
const comeToThePoint = value === 1 ? 'yes' : 'no';
```
the above one is an expression statement that evaluates to value `yes`. So, what?

in the same way, We can assign a function to a variable which we call `function expression`.

```
const myExpressiveFunction = function(a, b) {
    return a + b;
}
myExpressiveFunction(10, 20);
> 30

```

`Note it: ` The above function has no name hence it is an anonymous function. To use the above function you need to call using the variable name.

ook. What is immediately invoked? Hmm. Maybe I get it as it gets executed as soon as defined, right?

Exactly. Which we called an `Immediately Invoked Function expression` and it can only be achieved using anonymous functions.

Cool. What next? 

Let's understand the importance of parenthesis in javascript.

```
// it is an expression that you can put inside parentheses and it will get executed.
(a = 10);

// declaration inside parenthesis results in SyntaxError
(var a);
```
in the same way, if we put the above function expression inside parentheses becomes IIFE.

Example:
```
(function(a, b) {
    return a + b;
})(10, 20);
```

it can be shortened by arrow functions as:

```
((a,b)=>a + b)(10, 20);
```
We are done!

