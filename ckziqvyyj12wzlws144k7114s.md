---
title: "Explore ES 2017 features: javascript"
datePublished: Fri Feb 11 2022 18:30:16 GMT+0000 (Coordinated Universal Time)
cuid: ckziqvyyj12wzlws144k7114s
slug: explore-es-2017-features-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/cKjbI0Y00X0/upload/v1644515412826/hd6x5GzIP.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

Javascript is bringing new features every year. I have covered ES 2021 features in one article so far. You can have a look:

%[https://vkglobal.hashnode.dev/js-new-features-es-2021]

<hr>

Let's learn about ES 2017 features now:

## 1. Object.entires and Object.values:
Which are used to iterate over JS objects. We usually use `for...in` to iterate over an object in a more declarative way. Let's see an example here:

```
let keys = [];
let values = [];

const testObj = {
  id: "1",
  name: "urstrulyvishwak",
  about: "JS Content creator"
};

for (const key in testObj) {
  keys.push(key);
  values.push(testObj[key]);
}

console.log("Keys in Object: " + keys);
> Keys in Object: id,name,about

console.log("Values in Object: " + values);
> Values in Object: 1,urstrulyvishwak,JS Content creator 
```
We need to iterate over the object and fetch all the keys. Also, using these keys we have captured values for the same.

Here, in ES 2017 release, there is `Object.entries` that directly fetch keys & values whereas `Object.values` directly fetch values.

Example:

```
const testObj = {
    id: "1",
    name: "urstrulyvishwak",
    about: "JS Content creator"
  };

// Using Object.entries.
const keys = [];
const values = [];
Object.entries(testObj).forEach(([key, value]) => {
    keys.push(key);
    values.push(value);
});

console.log("Keys in Object: " + keys);
console.log("Values in Object: " + values);
> Keys in Object: id,name,about
> Values in Object: 1,urstrulyvishwak,JS Content creator

// Using Object.values
console.log('Values are: ' + Object.values(testObj));
> Values are: 1,urstrulyvishwak,JS Content creator
  
// Using Object.Keys -  this was introduced in ES 2015
console.log('Keys are: ' + Object.keys(testObj));
> Keys are: id,name,about
```
<hr>

## 2. String Padding
Appends a string with other either from starting using `padStart()` or to end using`padEnd()`

`padStart(maxLimit, fillString?)`: pads a string with other string from beginning.

`maxLimit` - expected string length after padding.

`fillString` - string to append.

The same applies to `padEnd(maxLimit, fillString?)` whereas it pads from ending.

Example:

```
let testString = 'truly';

testString = testString.padStart(8, 'urs');

console.log(testString);
> urstruly

console.log(testString.padEnd(15, 'vishwak'));
> urstrulyvishwak
```
We have seen a basic example above. Let's dive a little deeper to see what more is there.

`Case 1:` What happens if `maxLimit` is less than the length of the input string?

It won't pad anything it will just display the input string as it is. See the example below.

```
let testString = 'truly';

console.log(testString.padStart(4, 'urs'));
> truly

```

The same applies to `padEnd()` as well. 

`Case 2:` Does `padStart` & `padEnd` mutates/modifies original string? 

NO. See the example below:

```
let testString = 'truly';

console.log(testString.padStart(8, 'urs'));
> urstruly

console.log(testString);
> truly
```
`Case 3:` What if I give only `maxLimit` but not the optional `fillString`?
Appends empty till reaches length to maxLimit. See below exmple:

```
let testString = 'truly';

console.log(testString.padStart(8));
>    truly // 3 empty spaces appended before truly.
```
`Case 4:` What if `maxLimit` less than the length of input + fillString?
Input string displayed as it is and remaining length appends chars from fillString.
See the below example:

```
let testString = 'truly';

console.log(testString.padStart(6, 'urs'));
> utruly
``` 
Observe that the input string `truly` displayed as it is whereas the first character from the fillString is appended as the maxLimit is 6.

The same applies to padEnd as well. Hope these cases & examples make you remember `padStart & padEnd` forever.

<hr>

## 3. Object.getOwnPropertyDescriptors
The method returns an object describing the configuration of a specific property on a given object. Hmm, we might not get it for the first instance. Let's understand by a simple example:

```
const testObj = {
    property: 'test'
}

console.log(Object.getOwnPropertyDescriptor(testObj, 'property'));
> {value: 'test', writable: true, enumerable: true, configurable: true}
```
These are the configurations of the property in testObj.

So here, 

`value` - Actual value of property

`writable` - `true` if and only if the value can be modified - applicable for data descriptors only

`enumerable` - `true` if the property shows while enumeration

`configurable` - `true` if the property descriptor can be modified or removed.

If you observe syntax: `Object.getOwnPropertyDescriptor(testObj, 'property')`  - first param is the object in which we have to look second param that is property.

In case of getter & setter:

```
const getObj = {
    item: 'first',
    get test() {
        return 'test';
    },
    set _test(item) {
        this.item = item;
    }
}

console.log(Object.getOwnPropertyDescriptor(getObj, 'test'));
> {get: ƒ, set: undefined, enumerable: true, configurable: true}

console.log(Object.getOwnPropertyDescriptor(getObj, '_test'));
> {get: undefined, set: ƒ, enumerable: true, configurable: true}
```
We have seen all other properties. Now, we can see about `get` & `set` here:

`get` - a function that serves as a getter for a property
`set` - a function that serves as a setter for a property

<hr>

## 4. Trailing Commas in function calls parameter & arguments list

In earlier versions, trailing commas are accepted in arrays like `[1,2,3,4,]`. Here, we are talking about the comma after number 4 in the array. Yes, that won't throw any error in javascript. But there is a caveat here that if you add one more comma then array length will be increased by 1.

As part of this feature, in ES 2017 this same implementation expanded to functions parameters & arguments list.

A simple example would explain more:

```
const test = (a,b,) => {
    return a + b;
}
console.log(test(1,2));
> 3

console.log(test(1,2,));
> 3
```
`test` function parameters & arguments list allowed trailing comma and returned valid result.

🤔 What it's importance?

 If the trailing comma is already present and you added new property then the diff in GitHub is shown properly. Otherwise, changes would be shown for both lines as you have to add a comma and add a new property.

<hr>


There are two more items to cover as part of this article. I will update this article as soon as my investigation is done. 

Thank you. Happy reading.




