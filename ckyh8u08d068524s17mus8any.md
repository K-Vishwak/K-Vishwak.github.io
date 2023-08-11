---
title: "JS Closure"
datePublished: Sun Jan 16 2022 12:37:23 GMT+0000 (Coordinated Universal Time)
cuid: ckyh8u08d068524s17mus8any
slug: js-closure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642326931951/KCrFml5tG.png
tags: javascript, 100daysofcode

---

 [Youtube](https://youtu.be/V_Q2t_aHCKU)   [Twitter](https://twitter.com/urstrulyvishwak/status/1482693569458872320?s=20)


%[https://youtu.be/V_Q2t_aHCKU]

 
Closure gives you access to an outer functions scope from inner function.

```
function outer() {
    const name = 'test';
    function inner() {
     // 'name' from outer function is accessible inside inner function
     console.log(name);
    }
    inner();
}
outer();

> test
```

```
function outerAdd(x) {
    return function(y) {
        return x + y;
    };
}

const outer12 = outerAdd(12); // x as 12.
const outer14 = outerAdd(14); // x as 14.

const outer12Result = outer12(12); // y as 12.
console.log(outer12Result);
> 24

const outer14Result = outer14(14); // y as 14.
console.log(outer14Result);
> 28

```



Alternatively, you can use arrow functions as well like below.

```
outerAdd = x => y => x + y;

const outer12 = outerAdd(12);
const outer14 = outerAdd(14);

const outer12Result = outer12(12);
console.log(outer12Result);
> 24

const outer14Result = outer14(14);
console.log(outer14Result);
> 28
```

Counter example using closure:
```
function outer() {
    let counter = 0;
    return function inner() {
        counter += 1;
        return counter;
    }
}
const out = outer();

console.log(out());
console.log(out());
console.log(out());

> 1
> 2
> 3
```


%[https://twitter.com/urstrulyvishwak/status/1482693569458872320?s=20]
