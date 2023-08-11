---
title: "JS apply, call and bind"
datePublished: Tue Jan 25 2022 17:13:36 GMT+0000 (Coordinated Universal Time)
cuid: ckyudnwbi08wj2vs1etaj6pd6
slug: js-apply-call-and-bind
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643129981309/sgfHolUCm.png
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

# 1. call

Using call, an object can use method of another object. &#129320;

No worries let's start with first step.

```
const object = {
    id: 1234,
    firstName: 'James',
    lastName: 'Peter',
    // Object method
    getFullName() {
        return this.firstName + " " + this.lastName;
    }
}

object.getFullName();
> 'James Peter'
```

So, as per definition of call - getFullName method can be used by other object. &#129320;

Let's see:

```
const anotherObject = {
    firstName: 'James1',
    lastName: 'Peter1'
}

object.getFullName.call(anotherObject);
> 'James1 Peter1'
```
Done. So, here - call used to invoke method with owner object as an argument.

# 2. apply

Apply is also same. Only difference as is it accepts arguments in the form of an array instead simple arguments. 

Yes. Always, examples enlighten us well rather theories around them.

Let's see:

In case of call,

```
const object = {
    id: 1234,
    firstName: 'James',
    lastName: 'Peter',
    getFullName(id, email) {
        return this.firstName + " " + this.lastName + " " + id + " " + email;
    }
}

const anotherObject = {
    firstName: 'James1',
    lastName: 'Peter1'
}

object.getFullName.call(anotherObject, '345', 'jamesp@gmail.com');
> 'James1 Peter1 345 jamesp@gmail.com'
```

Same example using apply would be:
```
const object = {
    id: 1234,
    firstName: 'James',
    lastName: 'Peter',
    getFullName(id, email) {
        return this.firstName + " " + this.lastName + " " + id + " " + email;
    }
}

const anotherObject = {
    firstName: 'James1',
    lastName: 'Peter1'
}

object.getFullName.apply(anotherObject, ['345', 'jamesp@gmail.com']);
> 'James1 Peter1 345 jamesp@gmail.com'
```
No major difference, just we sent remaining arguments in array in case of apply.

# 3. bind

Bind also does the similar work instead using other object methods it will create new function with particular `this` context.

Ok. Let's see:

```
const object = {
    multiply(num1, num2) {
        return num1 * num2;
    }
}

const result = object.multiply.bind(this, 3, 2);

// result is function created by bind to return multiplication of 3 & 2. Hence it always returns the same.
result();
> 6

// if you try giving different params like 4 & 5.
result(4, 5);
> 6 
// because bind created a function to return the result of multiplication of 3 & 2.
```
Then, how we can reuse the created function. To do this:

```
const object = {
    multiply(num1, num2) {
        return num1 * num2;
    }
}

const result = object.multiply.bind(this);

result(3, 2);
> 6

result(5, 6);
> 30
```

Hope you got idea of how to use them. Yes. When to use them is obviously a question &#129322;?

No hard and fast rules to use these. Few features of any language we use regularly and few others based on context & need. Requirement determines when to use it.

Thank you