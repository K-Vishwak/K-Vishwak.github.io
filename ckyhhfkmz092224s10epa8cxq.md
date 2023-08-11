---
title: "Simple Higher-order functions"
datePublished: Sun Jan 16 2022 16:38:06 GMT+0000 (Coordinated Universal Time)
cuid: ckyhhfkmz092224s10epa8cxq
slug: simple-higher-order-functions
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/eYwn81sPkJ8/upload/v1644043790063/bj7Xq7l3p.jpeg
tags: javascript, 100daysofcode

---

A function can take a function as an argument or can return a function as a value is called a higher-order function.

1. A function that returns a function

```
const higherOrderFunc = function() {
    return function() {
        return 12;
    }
}

// which returns below function hence it is higher order function.
higherOrderFunc(); 
> ƒ () {
        return 12;
    }

higherOrderFunc()();
> 12
```

2. A function that takes a function as an argument

```
const testFunc = function(x) {
    return x + 12;
}

//which takes function as an argument.
const higherOrderFunc = function(testFunc) {
    return testFunc(8);
}

higherOrderFunc(testFunc);
> 20
```

**Example: 1**

```
function calculate(operation, numbers) {
    return operation(numbers);
}

function addition(numbers) {
    let sum = 0;
    for (const number of numbers) {
        sum+=number;
    }
    return sum;
}

function multiply(numbers) {
    let sum = 1;
    for (const number of numbers) {
        sum*=number;
    }
    return sum;
}

const numbers = [1,2,3,4,5];
console.log(calculate(addition, numbers));
> 15

console.log(calculate(multiply, numbers));
> 120
```
> calculate(multiply, numbers) - Don't append parenthesis while sending function as an argument.


**Benefits of higher-order functions:**

1. Reduces code duplication
2. Single responsibility 


In Javascript, functions can take arguments as primitives or objects and return the same called `first-order functions`. 


JS built-in higher order functions are:

`arr.reduce(), arr.forEach(), arr.filter(), arr.map()`
