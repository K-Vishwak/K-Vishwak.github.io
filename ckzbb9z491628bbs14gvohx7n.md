---
title: "Relax, JS `this` is damn easy."
datePublished: Sun Feb 06 2022 13:38:52 GMT+0000 (Coordinated Universal Time)
cuid: ckzbb9z491628bbs14gvohx7n
slug: relax-js-this-is-damn-easy
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/6Wax86m-3K4/upload/v1644078507037/v1UNsyY3k.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

Once you know the concept then you would say the same. Yes. There are several cases around `this`. Hence by knowing all those scenarios you will be cleared. We are generally afraid out of imagination. Let's not simply imagine instead do some practice.

Hence let's look into the scenarios where and when we should ideally use `this` and what its importance in its scope with different possible examples.

So, basically what `this` actually refers to in Javascript?

It refers to an `object` in javascript. Based on the usage of `this` its reference will be changed. So, if you got all those references.

I hope this introduction would be fine. OK. Let's decipher `this` now:

Before entering into explanation I want to give a summary here:

<table>
<th>
<tr>
<td>S.No.</td>
<td>Scenario</td>
<td>`this` refers to</td>
</tr>
</th>
<tbody>
<tr>
<td>1.</td>
<td>Inside object</td>
<td>Refers to parent object only</td>
</tr>
<tr>
<td>2.</td>
<td>Inside browser window</td>
<td>Refers to the window object</td>
</tr>
<tr>
<td>3.</td>
<td>Strict mode in the browser window</td>
<td>Refers to the window object</td>
</tr>
<tr>
<td>4.</td>
<td>Inside function</td>
<td>Refers to the window object</td>
</tr>
<tr>
<td>5.</td>
<td>strict mode: Inside function</td>
<td>Returns undefined</td>
</tr>
<tr>
<td>6.</td>
<td>In Event handler</td>
<td>Refers HTML Element</td>
</tr>
<tr>
<td>7.</td>
<td>Using with call(), bind() and apply()</td>
<td>Refers to objects sent as arguments</td>
</tr>
<tr>
<td>8.</td>
<td>Inside JS classes</td>
<td>Refers to the current object.</td>
</tr>
<tr>
<td>9.</td>
<td>In arrow function</td>
<td>Refers to the window object.</td>
</tr>
</tbody>
</table>

## 1. Inside object

Refers to parent object only.
 
**Example:**

```
const testObj = {
    firstName: 'John',
    lastName: 'Carter',
    name: function name() {
        return this.firstName + " " + this.lastName; // Here this refers to `testObj`
    }
}

console.log(testObj.name());
> John Carter
```

## 2. Alone using this

### 1. Inside browser window

Refers to the window object.

Hence window methods like `alert, atob, blur` etc. are accessed using this.

**Example:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644079514753/jvwXHs7dC.png)

Access the` alert` function of the window object using this.

**Example:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644079665838/tYB5-PyNN.png)

### 2.  Strict mode in the browser window
Also `this` refers to the window object.

**Example:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644081701972/54OdktN6f.png)

## 3. Inside function

Also `this` refers to the window object

**Example:**

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644081870054/RlTVFWZZo.png)

Using strict mode returns undefined.

```
function thisInsideFunction() {
    'use strict'; // see strict mode
    return this;
  }
  
 console.log(thisInsideFunction());
> undefined
```

## 4. In Event handler

Users can trigger click, enter, keydown events on various form elements in HTML from the browser. While handling those events we bind those event handlers with functions generally. If we pass this from the handler then it refers to the corresponding `HTML element` object.

**Example:**
```
<button onclick="buttonClick(this)">Submit</button>

// this refers to button HTMLElement here.
```

## 5. Using with call(), bind() and apply() methods

These are javascript built-in methods. call() & apply() used to call object method of other object using another object as an argument. 

Complete article on these methods are [here](https://vkglobal.hashnode.dev/js-apply-call-and-bind)

Whereas bind borrows object method of another object and creates a new object altogether.

Essentially, all these three things will do a similar kind of work.

now, what `this` refers to in these methods. It refers to objects sent as arguments.

**Example**

```
const testObj = {
    firstName: 'John',
    lastName: 'Carter',
    name: function name() {
        return this.firstName + " " + this.lastName;
    }
}

const anotherObj = {
   firstName: 'new john',
   lastName: 'Carter'
}

console.log(testObj.name.apply(anotherObj)); // this refers to anotherObj
> new john Carter
```

Same in case of call & bind as well. 

## 6. Inside JS classes

 `this` refers to the current object.

**Example**

```
class TestThis {
    a;
    b;
    
    normalFunction() {
        console.log('normal function');
        console.log(this);
    }

    static staticFunction() {
        console.log('Static function');
    }
}

const test = new TestThis();
test.normalFunction();

```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644084643435/fUTlJh_3y.png)


Note that static properties are not part of `this`.

## 7. `this` in arrow function

Refers to the window object.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644151591116/dojBEW9ux.png)

 inside object method refers to the parent obj.

```
let testObj = {
    test: 10,
    bar: function() {
      let x = (() => this);
      return x;
    }
  };

 console.log(testObj.bar()());
```

I covered most possible cases of this. Please let me know by commenting if you come across any new scenarios.

Also, do comment if you don't understand any scenario.



