---
title: "JS How much Math do you do?"
datePublished: Sun Jan 30 2022 10:42:07 GMT+0000 (Coordinated Universal Time)
cuid: ckz14vpdu0qbf9js1ho6g7yev
slug: js-how-much-math-do-you-do
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/qDY9ahp0Mto/upload/v1643535459372/bXEPrTRMD.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

Yes. Javascript provides the built-in object `Math`. It has several useful methods to work on numbers. Let's go through, which we really use.

### Round to integer

1. **round()** - ➡️ Rounds to its nearest integer. 
2. **ceil()** - ⬆️ Rounds up to its nearest integer.
3. **floor()** - ⬇️ Rounds down to its nearest integer.

```
const num = 10.5;

console.log(Math.round(num)); // 11
console.log(Math.ceil(num)); // 11
console.log(Math.floor(num)); // 10

const num1 = 10.4;

console.log(Math.round(num1)); // 10
console.log(Math.ceil(num1)); // 11
console.log(Math.floor(num1)); // 10
```
`Remember like this:`

round - 10.0 - 10.4 -> 10 and 10.5 -> 11.0 -> 11

ceil (up) - 10.1 - 10.9. -> 11

floor (down) - 10.1 - 10.9 -> 10

The same applies to negative numbers.

### Return Integer part

**trunc()** - returns integer part as it is.

```
const num = 10.547;

console.log(Math.trunc(num));
> 10
```

### Return absolute number

**abs()** -  returns positive number.

```
const num = 10.547;
const num1 = -10.547;

console.log(Math.abs(num)); // 10.547
console.log(Math.abs(num1)); // 10.547
```

### power & sqrt

Hope no explanation is needed.

```
const num = 9;

console.log(Math.pow(num, 2)); // 81
console.log(Math.sqrt(num)); // 3

```

### max & min

Returns Max number and min number in the given list.

```
console.log(Math.max(3,4,5,1,2)); // 5

console.log(Math.min(3,4,5,1,2)); // 1

```

### random number

random() - method used to return random number between 0 - 1.

```
console.log(Math.random()); // 0.34609498534013383

```

Few more methods of `Math` object that we rarely use them.

Those are:

`Math.sign()` - returns -1 (negative), 0 (null), 1 (positive) based on the number provided.

`Math.sin() & Math.cos()` -  trignometric operations - sin 90 - 1.

`Math.log(x) & Math.log2() & Math.log10()` - returns logarthmic conversion.

Thanks 😊














