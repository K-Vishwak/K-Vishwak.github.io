---
title: "JS new features - ES 2021"
datePublished: Thu Jan 27 2022 16:16:39 GMT+0000 (Coordinated Universal Time)
cuid: ckyx6iczw03tu2qs1f4j34t5l
slug: js-new-features-es-2021
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643300282410/pUj-JRhVS.png
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

### 1. Logical & assignment operators

Three new parameters are added by combining logical and assignment operator as.

1. **&&=** - it assigns when value is truthy.
2. **||=** - it assigns when value is falsy.
3. **??=** - it assigns when value is null or undefined.

Let's quickly jump into using them:

1.



```
let x = 1;
if (x){
    x = 10;
}
> 10

// OR
let x = 1;
x = x && 10;
> 10

// can be written as:
let x = 1
x &&= 10;
> 10
```
OMG! Super cool. Isn't it? Next..

2. 


```
let x = 0;
if (!x){
    x = 10;
}
> 10

// OR
let x = 1;
x = x ||10;
> 10


let x = 0; // x = 0 means falsy.
x ||= 10;
> 10
```

3.

```
let x;
if (!x){
    x = 10;
}
> 10

// OR
let x;
x = x ?? 10;
> 10

// now
let x; // x is undefined here.
x ??=10;
> 10
```

### 2. Number Separator
We can now use underscore separator to separate group of digits in lengthy numbers according to our number system.

Let's dive:

```
const longNumber = 1000000000; // Not in a readable format.
longNumber;
> 1000000000

// By using separator underscore, we can read easily.
const longNumber = 100_00_00_000;
longNumber;
> 1000000000 // Still, result is same.
```
Hence using this separator readability improved. Also, this is not just limited to regular numbers but we can use for `Hex`, `Oct` and `Binary` formats also.

### 3. New String method
We know about `replace` string method it will replace first occurrence of matched value in a given string. Whereas, to replace everywhere new method has been introduced is `replaceAll'.

Let's see how these two methods work:

```
const testString = "Hey, Welcome to my JS articles about JS";
testString.replace('JS', 'JavaScript');
> 'Hey, Welcome to my JavaScript articles about JS'

const testString = "Hey, Welcome to my JS articles about JS";
testString.replaceAll('JS', 'JavaScript');
> 'Hey, Welcome to my JavaScript articles about JavaScript'
```

### 4. Access Private methods from class

Name itself says everything. Let's start experiments:

```
class PrivateMethodClass {
    publicMethod() {
        console.log('I am public');
    }
    #privateMethod() {
        console.log('I am private');
    }
}

const privateMethodClass = new PrivateMethodClass();
privateMethodClass.publicMethod();
privateMethodClass.privateMethod();
> I am public
> Uncaught TypeError: privateMethodClass.privateMethod is not a function // not accessible.
```

now, how can we access it.

```
class PrivateMethodClass {
    publicMethod() {
        console.log('I am public');
    }
    #privateMethod() {
        console.log('I am private');
    }
    printAllMethods() {
        this.publicMethod();
        this.#privateMethod();
    }
}

const privateMethodClass = new PrivateMethodClass();
privateMethodClass.printAllMethods();
> I am public
> I am private
```
### 5. private getters & setters

More like above but we use get & set here.

Let's see the example:
```
class PrivateGetNSet {

    userName;
    #password;

    // Regular use
    set userName(name) {
        this.userName = name;
    }

    get userName() {
        return this.userName;
    }

    set password(password) {
        this.#password = password;
    }

    // try to getPassword and returns undefined.
    get #getPassword() {
        return this.#password;
    }

    // newly introduced.
    get privateGetPassword() {
        return this.#getPassword;
    }
}

const privateGetNSet = new PrivateGetNSet();
privateGetNSet.userName = 'JS';
privateGetNSet.userName;
> JS;

privateGetNSet.password = 'test';
privateGetNSet.getPassword;
> undefined

privateGetNSet.privateGetPassword;
> 'test'
```


### 6. Promise.any()

Returns promise as soon as at least one promise is resolved in list of given promises. Whereas, existing `Promise.all()` resolves only when all given promises are resolved.

Example:

```
const errorPromise = new Promise((resolve, reject) => {
  reject("fail");
});

const resolveSlow = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, "Resolve Slowly");
});

const resolveFast = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, "Resolve fastly");
});

Promise.any([errorPromise, resolveSlow, resolveFast]).then((value) => {
  console.log(value);
});
> Promise {<pending>}[[Prototype]]: Promise[[PromiseState]]: "fulfilled"[[PromiseResult]]: undefined
> Resolve fastly

Promise.all([errorPromise, resolveSlow, resolveFast]).then((value) => {
  console.log(value);
});
>Promise {<rejected>: 'fail'}[[Prototype]]: Promise[[PromiseState]]: "rejected"[[PromiseResult]]: "fail"
> Uncaught (in promise) fail

```
If every promise fails then it will throw `AggregateError` exception.