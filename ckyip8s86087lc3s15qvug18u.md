---
title: "JS Functional Composition"
datePublished: Mon Jan 17 2022 13:04:32 GMT+0000 (Coordinated Universal Time)
cuid: ckyip8s86087lc3s15qvug18u
slug: js-functional-composition
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642418240560/Fp0N4jUQD.png
tags: javascript, 100daysofcode

---

[Twitter](https://twitter.com/urstrulyvishwak/status/1483063814300254208?s=20) [Youtube](https://youtu.be/qxx849bnfF0)


%[https://youtu.be/qxx849bnfF0]


It is an approach where result of one function passed on to next function.

```
const add = (x, y) => x+y;

const subtract = (x) => x-4;

const multiply = (x) => x * 8;

// result of `add` is passed to `subtract` and its result passed to `multiply`.
const result = multiply(subtract(add(2, 3)));

result;
> 8
```
That looks readable but what if we have more functions to call one after other.
Let's try little cleaner approach.

```
const compose = (...functions) => x => functions.reduceRight((total, f) => f(total), x);

const add = x => x+2;

const subtract = x => x-1;

const multiply = x => x * 8;

compose(multiply, subtract, add)(2);
> 24
```

We can also use  [reduce](https://vkglobal.hashnode.dev/js-reduce)  to implement:

```
const pipe = (...functions) => x => functions.reduce((total, f) => f(total), x);

const add = x => x+2;

const subtract = x => x-1;

const multiply = x => x * 8;

pipe(add, subtract, multiply)(2);
> 24
```

`pipe` - performs from left-to-right.
`compose` - performs from right-to-left.