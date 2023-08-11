---
title: "Mistakes per day in JS"
datePublished: Fri Feb 04 2022 19:20:50 GMT+0000 (Coordinated Universal Time)
cuid: ckz8sm1j10k5kbbs109qpc2q1
slug: mistakes-per-day-in-js
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/8RXmc8pLX_I/upload/v1644002387482/4_AYOXvPe.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week, hashnodecommunity

---

`Beginner:` We are humans and mistakes are very much common. > 50 mistakes/day.

`Intermediate:` We are humans and we can avoid mistakes. < 50 mistakes/day.

`Expert:` We are humans and we can speak in Javascript 🤣. < 5 mistakes/day.

Quite interesting, isn't it? If you see in the above statements mistakes are there everywhere. So, what an expert mind will do generally? 

He can forecast the result and accordingly update the result whereas a beginner does the trial and error while coding. 

> If you know the disease well then you can cure it well instead of eating the whole medical shop.

There could be a good proverb in Google but suddenly got this in my mind so written it. Hope you got the context.

I don't like to beat around the bush. Let's start:

I want to provide some cool tips to avoid mistakes and to code in less time.

### Tip 1: Practice basics well

Whenever we code anything we decouple the whole feature into small parts as tiny as possible and will start coding.

In each phase of the coding, we somehow play with data that we want to show on the browser.

**Example:**

Let's say you have to show the employee list in your application and update the list as soon as the user adds a new employee.

```
// Initial list.
let employeeList = ['james', 'peter', 'roy', 'garreth'];

// you know you can use push and add a new employee to your existing array.
employeeList = employeeList.push('new james');

// But you are not sure what happens if you do like the above
console.log(employeeList);
> 5 // push returns the size of the array instead updated array.
```
So, knowing the basics is very much important to avoid mistakes. Also, to avoid trial and error trap.

>> I would say this is the main reason for mistakes in the whole coding journey.

### Tip 2: Learn before using

Yes. You don't use basic JS methods every time as you might have to depend on wrappers or libraries which are written to achieve a few specific real-time scenarios in web applications.

**Example:** `moment.js` - it is a javascript library used to deal with date and time very well.

We can directly import this library and we do the necessary time conversions etc. 

Now, these kinds of libraries provide different methods to use for different purposes. We shouldn't search StackOverflow and copy-paste the code.

Every library provides cleaner documentation for each feature they provide. Just go through them and try examples they provide and understand features  & shortcomings. After that use them.

> So, this tip is not just to avoid mistakes but also to avoid future bugs.

### Tip 3: Understand the flow of the execution

Executions generally happen from top to bottom in the script. Though, there are situations where flow slips a little bit.

**Aynschronous JS:**

JS has asynchronous support like Promises, setTimeout, setInterval etc. Whe you use these then the execution flow changes.

**Example:**

```
console.log('first message');

setTimeout(() => {
    console.log('async message');
});

console.log('last message');

> first message
> last message
> async message
```

**Operator Precedence:** It determines how operators are parsed concerning each other.

```
console.log(5 + 10 * 3 - 2); // 33
console.log(5 + 10 * (3 - 2)); // 15
console.log((5 + 10) * 3 - 2); // 43
```
In first scenario, multiplication has higher precedence so,

`5 + 10 * 3 - 2 -> 5 + 30 - 2 -> 35 - 2` - 33

In second scenario, parenthesis has higher precedence so,

`5 + 10 * (3 - 2) -> 5 + 10 * 1 -> 5 + 10 -> 15`

The third is self-explanatory.

So, the order of execution changes results here. 

So far good but there are many rules in operator precedence how can we remember?

Don't remember just bookmark this page: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence

> Keep in mind that debugging is not for mistakes.

I will cover debugging in another article where I will point where, when, and how to use debugging efficiently.

What are the takeaways?

1. Fewer mistakes == less time to code - Performance improvement
2. To avoid mistakes you will learn  - Knowledge is divine
3. You'll end up speaking in JS - Became the finest programmer 🤩

All these tips out my experience. Please do comment on which tip you follow the most and also comment your own tips.

Thank you 😊