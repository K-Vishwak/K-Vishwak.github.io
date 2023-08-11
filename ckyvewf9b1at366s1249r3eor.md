---
title: "JS Stack Overflow"
datePublished: Wed Jan 26 2022 10:36:00 GMT+0000 (Coordinated Universal Time)
cuid: ckyvewf9b1at366s1249r3eor
slug: js-stack-overflow
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643193608902/LXFoezi4Z.png
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

In JS, every function is added to stack before being executed. It is called *call stack*.

Yes. Example speaks more:

```
function first() {
second();
console.log('I am first');
}

function second() {
console.log('I am second');
}


first();
> I am second
> I am first
```

When JS runs, there is a global function is being called & added to call stack first. Then, `first();` is the invocation where first function will get added to stack later `second();` is the function invocation is present inside first will get added to stack.

So, 🪄 magic here is.

Stack follows LIFO, last in first out..

Last in item is `second()` - Hence it will get executed first. Executed and pops out of stack.
Then, execution order completes `first()` and it will get pop out of stack.

Hmmm. OK. We got what stack is so far. What is overflow then?

It is just that keep adding function calls even more than the size of the stack. - Overflow.

When this generally happen in our code? To simply put `when we forgot`&#129299;

Again, example:

Best example falls in this scenario is `recursion` - means a function calls itself.

```
function callMySelf() {
callMySelf();
}

callMySelf();
VM1307:2 Uncaught RangeError: Maximum call stack size exceeded
    at callMySelf (<anonymous>:2:1)
    at callMySelf (<anonymous>:2:1)
    at callMySelf (<anonymous>:2:1)
    at callMySelf (<anonymous>:2:1)
    at callMySelf (<anonymous>:2:1)
    at callMySelf (<anonymous>:2:1)
    ......
```
What happened here? `We forgot` to add condition to exit the loop.




