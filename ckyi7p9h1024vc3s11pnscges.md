---
title: "JS Referential Transparency"
datePublished: Mon Jan 17 2022 04:53:28 GMT+0000 (Coordinated Universal Time)
cuid: ckyi7p9h1024vc3s11pnscges
slug: js-referential-transparency
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642395176006/f_6ghrS4x.png
tags: javascript, 100daysofcode

---

[Twitter](https://twitter.com/urstrulyvishwak/status/1482939524950867971?s=20)  [Youtube](https://youtu.be/bIH_2PCQFkw) 


%[https://youtu.be/bIH_2PCQFkw]


An expression in javascript can be replaced by its value is called referential transparency.

```
const add = (x,y)=>x + y;

const multiply = (x)=>x * 4;

// add (3, 4) can be replaced by 7. - Referential Transparency.

multiply(add(3, 4)); 
> 28

multiply(add(3, 4));
> 28
```
```
const arr = [];
const add = (x,y)=>{
    const addition = x + y;
    arr.push(addition);
    return addition;
}

const multiply = (x)=>x * 4;

// Here, we can't replace add(3,4) with 7 as it affects the program
multiply(add(3, 4));
> 28

> multiply(add(3, 4));
28
```