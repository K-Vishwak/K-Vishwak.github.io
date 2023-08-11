---
title: "Simplified Type Coercion in JS."
datePublished: Wed Feb 02 2022 19:17:10 GMT+0000 (Coordinated Universal Time)
cuid: ckz5xlmfh0q9pghs19lof8bxw
slug: simplified-type-coercion-in-js
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/nDd3dIkkOLo/upload/v1643906557763/zaAte_YNX.jpeg
tags: javascript, 100daysofcode, 2articles1week

---

**Type Coercion**: Automatic conversion of a value from one data type to another data type is called `Type Coercion` or `implicit type conversion`. Javascript engine does this in different scenarios. Let's see where and when this conversion happens and what to remember while coding. 

>> **Declaimer:** Javascript supports explicit conversion as well and my topic is not that hence I am not covering any of its content though it is closely related.

So here,

`date type` - string, number, boolean, function, and object in Javascript.

> 🧐 Rule: all primitive types conversion happens to:  **string**, **number** or **boolean**

Coercion generally means `the practice of persuading someone to do something by using force or threats.` - According to Google. Thanks, Google. 

Hence, the `Javascript engine` does the same in converting the value from one type to another without your intervention. Ok. When does this generally happen in Javascript?

Yes. Instead of returning an error, it will do type coercion in the following scenarios:

1. Operate on incompatible types.
2. Output object or variable.

Not to worry if you don't get the above points instantly, I would definitely make you remember forever by end of this article. 

Let's start:

# 1. Operate on incompatible types

## String Coercion

Operator `+`: By default used for adding numbers. This also does some other work when used with strings i.e. concatenation. That is where coercion comes in to picture.

> 🧐 Rule: If any operand is a string and operated with + then the result is always concatenated and the result is a string.

```
console.log('str' + 1); // strstr
console.log('str' + true); // strtrue
console.log('str' + null); //strnull
console.log('str' + undefined); //strundefined
console.log('str' + NaN); //strNaN

```
## Number Coercion

Operators `/, -, *, %`: Division, Subtraction, Multiplication, Modulus in order. 

> 🧐 Rule: When you operate string numbers with these operators then result will **Number**. If one or both operands are non-numeric then result will be `NaN`

```
console.log('4' - 2); // 2
console.log('4' % 2); // 0
console.log('4' / 2); // 2
console.log('4' * 2); // 8
console.log('4' - NaN); // NaN
console.log('4' / 'str'); // NaN
console.log('4' / undefined); // NaN
``` 

**== Equality operator:** Used to compare values irrespective of their types. So, 

> 🧐 Rule: == operator coerces to number by default except in case of null. null is always equal to null or undefined.

```
console.log(1 == 1); // true
console.log(1 == '1'); // true - string 1 ocnverts to number. Hence both are equal.
console.log(1 == true); // true - true converts to number 1.
console.log(true == true); // true - 1 == 1 - true
console.log('true' == true); // false. String true converted to NaN. Hence result is false.
console.log('' == 0); // true

// Number coercion won't happen in case of null.
console.log(null == undefined); // true
console.log(null == null); // true
```

> Best Practice: Always use === instead of ==.


## Boolean Coercion

Happens with logical operators (||, && and !) and logical context.

```
// Logical context. if statement evaluates to boolean.
// Here number coerced to true.
if (4) {
    console.log('4 is not boolean');
}
```
```
// evaluated with coerced values as true && true and returns operand as result.

console.log(2 && 4); // 4
console.log(0 || 5); // 5
console.log(!!2); // true
```
> 🧐 Rule: `0, -0, undefined, null, '', false, NaN` are falsy as per Javascript engine `any` other thing is true.


# 2. Output object or variable

Javascript can output data in different ways like setting `innerHTML`, `alert(123)`, `console.log` etc.

> 🧐 Rule: In all the ways, the exposed object or variable is coerced to a string.

We are done. Anything below you can read out of your interest.

<hr>

There are a few things that make coercion looks hard to remember. You don't really need to remember any of the below scenarios.

There are many weird scenarios around different operators that result in different results. Here are the examples.

```
1. {}+[]+{}
2. !! 'false' == !! 'false'
3. ['1'] == 1
4. new Date() + 0
5. new Date() - 0
6. [] + null
7. '4' * new Array();
8. '4' / new String();
9. 4 + true
```

> Best Practice: Ignore them 😆. 

All of them have answers and nothing returns an error. I didn't provide the answer intentionally.

Let's talk practically,

Did you ever use this type of validation in your code?

If your answer is:

yes - don't do it.

no - don't try to use it.

What if the interviewer asks this question?

Most probably, questions asked in the following way:

1. Asks valid coercion question
2. Common sense related

Say, 

1. `1+2+'str' -> 3 + 'str' -> 3str ->` first two are numbers hence added and as per string coercion second part is concatenated.

2. `'str'+1+2 - str1 + 2 -> str12` - You might have understood.

- Execution happens from left to right.

Even if someone asks some weird scenario, you can say that this won't be legitimate coercion it might give some vague result. I don't think this question won't be a deciding factor for the selection.😃 

I would suggest having a look at the table shown on this page: 

https://www.w3schools.com/js/js_type_conversion.asp 

whenever possible. It will be useful.

Hope I have cleared confusion around `Type Coercion` in Javascript. Please do comment if I miss any valid coercion examples. I will update the article anytime.





