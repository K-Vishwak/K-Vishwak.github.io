---
title: "JavaScript Promises Unleashed: The Epic Battle of any vs race vs all!"
datePublished: Sun Aug 13 2023 06:20:54 GMT+0000 (Coordinated Universal Time)
cuid: cll924tk6000709l0amgi7fca
slug: javascript-promises-unleashed-the-epic-battle-of-any-vs-race-vs-all
tags: javascript, angularjs, web-development, webdev, reactjs

---

In short:

**Promise.all**: Returns all resolved values or first rejected.

**Promise.any**: Returns first resolved or aggregated all errors

**Promise.race**: Returns first resolved or rejected

Example1:

```javascript
const promise1 = Promise.resolve("Hello");
const promise2 = Promise.resolve("World");
const promise3 = Promise.resolve("!");

Promise.all([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:Hello,World,!

Promise.any([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:Hello

Promise.race([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:Hello
```

Example2:

```javascript
const promise1 = Promise.resolve("Hello");
const promise2 = Promise.resolve("World");
const promise3 = Promise.reject("!");

Promise.all([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:!

Promise.any([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:Hello

Promise.race([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:Hello
```

Example3:

```javascript
const promise1 = Promise.reject("Hello");
const promise2 = Promise.resolve("World");
const promise3 = Promise.resolve("!");

Promise.all([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:Hello

Promise.any([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Success:World

Promise.race([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:Hello
```

Example4:

```javascript
const promise1 = Promise.reject("Hello");
const promise2 = Promise.reject("World");
const promise3 = Promise.reject("!");

Promise.all([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:Hello

Promise.any([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:AggregateError: All promises were rejected

Promise.race([promise1, promise2, promise3])
  .then((results) => console.log("Success:" + results))
  .catch((error) => console.log("Error:" + error));

> Error:Hello
```

Please do add any more scenarios you came across.

Thanks.