---
title: "JS OOPS❗️ - Inheritance ⬆"
datePublished: Sat Jan 29 2022 09:05:34 GMT+0000 (Coordinated Universal Time)
cuid: ckyzlzokm09u49js189u1d9en
slug: js-oops-inheritance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643447068739/VAmLys2r8.png
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

### Inheritance 

📕 - Mechanism which acquires `properties` and `methods` from the parent.

Let's achieve:

```
class Parent {
    parentProperty;

    constructor(parentProperty) {
        this.parentProperty = parentProperty;
    }

    parentMethod() {
        return 'I am parent class method';
    }
}

class Child extends Parent {
    constructor() {
        super('parent property'); // setting parent property from child.
    }
    childMethod() {
        console.log(this.parentMethod()); // accessing parent methods.
        console.log(this.parentProperty); // accessing parent property.
    }
}

const child = new Child();
child.childMethod();

> I am parent class method
> parent property

```
Here, `super()` refers to parent class constructor and `extends` is the key word used to inherit.

### Overriding

 👨‍👧 child class has same properties & methods like parent.


```
class Parent {
    property = 'I am parent property';

    method() {
        return this.property;
    }
}

class Child extends Parent {

    // same parent property name.
    property = 'I am child property';

    // same parent method name.
    method() {
        console.log('I am a child method');
    }
}

const child = new Child();
child.method(); // overrides parent method and logs child details.
console.log(child.property); // overrides parent property and logs child property

> I am a child method
> I am parent property
```
### Accessing Static

👨‍🦲 child can also access static properties and methods.

```
class Parent {
    static property = 'I am parent class static property';

   static method() {
        return 'I am parent class static method';
    }
}

class Child extends Parent {
}

// We can call static entity with Class name directly.
console.log(Child.property);
console.log(Child.method());

> I am parent class static property
> I am parent class static method

``` 
### Inherit Built-in classes

Javascript allows us to inherit from built-in classes like `Array`, `String`, `Map` etc.

```
class MyArray extends Array {
    find() {
        console.log('This is my array find method');
    }
}

const myArray = new MyArray();
myArray.find();
> This is my array find method
```
In above case, find is the method of built-in `Array` whereas it is overridden in `MyArray` class. 

**Use**

Code reusability



