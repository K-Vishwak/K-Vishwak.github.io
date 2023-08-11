---
title: "JS Immutability"
datePublished: Mon Jan 24 2022 17:29:02 GMT+0000 (Coordinated Universal Time)
cuid: ckysyrw890bsksus10treekx9
slug: js-immutability
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643043881334/RT7ErlCPB.png
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

It is one of the core principles of `functional programming`.

`Meaning:` Objects whose state can't be altered once it is created.

Simple example would be `slice` to make you easily grasp the meaning.

```
const arr = [1,2,3,4];

const slicedArray = arr.slice(1,2);

slicedArray
> [2]

arr
> [1, 2, 3, 4]
```

If you see above example, `slice` didn't alter or modify or mutate original array `arr`. Whereas, if you see below example:

```
const arr = [1,2,3,4];

arr.push(5);
> 5

arr
> [1, 2, 3, 4, 5]
```
original array `arr` has been mutated. It's not that we shouldn't use `push` but we can avoid in most of the situations. Simple example would be:

```
const arr = [1,2,3,4];

const newArr = [...arr, 5];

arr
> [1, 2, 3, 4]

newArr
> [1, 2, 3, 4, 5]
```

The above all are simple examples and won't create any issue possibly. But, situations where we keep on modifying same object wherever possible across whole file will create many issues. As we need to maintain the track as how many times and ways that object has been altered.

So, to solve this issue we need to avoid mutating the object.

There are several ways to avoid mutation in javascript.

Using Object.freeze() - You can make objects immutable using this to some extent. Quickly grasp what it would do using [Object.freeze](https://vkglobal.hashnode.dev/js-objectfreeze)

We can use spread operator or [Object.assign](https://vkglobal.hashnode.dev/js-objectassign) to create shallow copies of original object to avoid mutating.



