---
title: "JS Pure function"
datePublished: Sat Jan 15 2022 13:31:30 GMT+0000 (Coordinated Universal Time)
cuid: ckyfvbr680kym8gs1gc04hopf
slug: js-pure-function
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642250614426/gBhc8SyTl.png
tags: javascript, 100daysofcode

---

 [Twitter](https://twitter.com/urstrulyvishwak/status/1482344922502275077?s=20)  [Youtube](https://youtu.be/AwE87kYdWtc)


%[https://youtu.be/AwE87kYdWtc]

  
### Two Rules

1. Given the same input, always return same output.
2. Produces no side effects

**Use:** Easy to refactor, makes code more flexible and adaptable.

### Case 1

```
// Pure function.
const multiplyNumbers = (x,y) => x * y;

multiplyNumbers(2, 3);
> 6
``` 
```
// Impure function.
let a = 4;
const multiplyNumbers = (b) => a *= b;

multiplyNumbers(3);
console.log(a); // first time: 12
> 12
multiplyNumbers(3);
console.log(a); // second time: 36
> 36

// Mutates external variable so it isn't pure.
```

### Case 2

```
// Impure function.
addNumberarr = (arr, num) => {
arr.push(num);
};
const testArr = [1,2,3];
addNumberarr(testArr, 4);

console.log(testArr);
> [1, 2, 3, 4]

// Mutates input array so it isn't pure.
```
```
// pure version of above.
addNumberarr = (arr, num) => {
return [...arr, num];
};
const testArr = [1,2,3];
addNumberarr(testArr, 4);
> [1, 2, 3, 4]
```
JS Built-in Pure functions:
```
arr.reduce()
arr.map()
arr.filter()
arr.concat()
arr.slice()
arr.each()
arr.every()
... - spread syntax 
```

JS Built-in Impure functions:
```
arr.splice()
arr.push()
arr.sort()
Math.random()
```



 