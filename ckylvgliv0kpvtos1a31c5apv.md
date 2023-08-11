---
title: "JS Splice"
datePublished: Wed Jan 19 2022 18:21:53 GMT+0000 (Coordinated Universal Time)
cuid: ckylvgliv0kpvtos1a31c5apv
slug: js-splice
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642615395448/tPIZ4bH3d.png
tags: javascript, 100daysofcode

---

[Twitter](https://twitter.com/urstrulyvishwak/status/1483868088219336709?s=20) [Youtube](https://youtu.be/JZJ7y17Vuss) 


%[https://youtu.be/JZJ7y17Vuss]


It is an array method works only on JS arrays.

It will remove, replace and/or adding new elements in array. 

*mutates original array*

`splice(start, deleteCount, item1, item2, ..., itemN);`

start - at which start changing the array.
deleteCount - no.of elements to remove from start and is optional.
item1, item2, and so on - to add elements to array after start.

splice returns removed items in array if none returns empty array.

```
const mainArr = ['apple', 'banana', 'mango', 'grapes', 'orange'];

// start > mainArr.length.
mainArr.splice(5, 1);
> []

// start < mainArr.length to delete on item.
mainArr.splice(1, 1);
> ['banana']
mainArr
> ['apple', 'mango', 'grapes', 'orange']

// add banana again at same location.
mainArr.splice(1, 0, 'banana'); // deleteCount is not optional when items are provided.
> []
mainArr
> ['apple', 'banana', 'mango', 'grapes', 'orange']

// negative offset.
mainArr.splice(-1, 1); // orange will be removed.
> ['orange']
mainArr
> ['apple', 'banana', 'mango', 'grapes']

// no changes to array as 0 elements removed & we are not adding any items to add.
mainArr.splice(1, 0); 
> []
mainArr
> ['apple', 'banana', 'mango', 'grapes']

// remove & insert at a time.
mainArr.splice(1, 1, 'newBanana');
> ['banana']
mainArr // banana removed & replaced with newBanana.
> ['apple', 'newBanana', 'mango', 'grapes']

// remove all items from specific index.
mainArr.splice(2);
> ['mango', 'grapes']
mainArr
> ['apple', 'newBanana']

// remove all items.
mainArr.splice(0);
> ['apple', 'newBanana']
mainArr
> []
```