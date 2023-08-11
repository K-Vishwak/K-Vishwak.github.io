---
title: "JS Currying"
datePublished: Tue Jan 18 2022 18:54:26 GMT+0000 (Coordinated Universal Time)
cuid: ckykh6mao0bbx7js15j4lb9m4
slug: js-currying
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642529138453/jKMl9RRJf.png
tags: javascript, 100daysofcode

---

**Currying:** Splitting up function that takes multiple arguments into a sequence of functions that each take its individual argument.

### Example 1:

Generally, we write:

```
function addition(x, y, z) {
    return x + y + z;
}

addition(1, 2, 3);
> 6
```
Currying:

```
function addition(x) {
    return function addY(y) {
        return function addz(z) {
            return x+y+z;
        }
    }
}

addition(1)(2)(3);
> 6
```
Using arrow functions:

```
addition = (x)=>(y)=>(z)=>x + y + z;

addition(1)(2)(3);
> 6
```
### Example 2:

```
function formWelcomNote(name) {
    name = `Hello ${name}, `;
    return function(location) {
        location = `Welcome to ${location},`;
        return function(section){
            return `${name}${location} Please visit ${section} section`
        }
    }
}

formWelcomNote('Yester')('VK Just Code Articles')('JS Articles');
> 'Hello Yester, Welcome to VK Just Code Articles, Please visit JS Articles section'
```

We can also write as:

```
formWelcomNote = (name)=>{
    name = `Hello ${name}, `;
    return (location)=>{
        location = `Welcome to ${location},`;
        return (section)=>{
            return `${name}${location} Please visit ${section} section`
        }
    }
}

formWelcomNote('Yester')('VK Just Code Articles')('JS Articles');
> 'Hello Yester, Welcome to VK Just Code Articles, Please visit JS Articles section'
```

### Example 3:

```
function calculation(fn) {
    switch (fn) {
        case 'add': return (a, b) => a + b;
        case 'sub': return (a, b) => a - b;
        case 'mul': return (a, b) => a * b;
        case 'div': return (a, b) => a / b;
    }
}
console.log(calculation('mul')(4, 2));

```