---
title: "JS No more confusion — Splice vs Slice"
datePublished: Mon Jan 31 2022 02:15:17 GMT+0000 (Coordinated Universal Time)
cuid: ckz227rix0e2qmjs12na93imt
slug: js-no-more-confusion-splice-vs-slice
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/8H9ph_Jp3hA/upload/v1643594451394/yR61uwjP4.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

They were built for different purposes but they look same in several scenarios. I will clear confusion first instead of dragging it to the end of the article.

**Tip 1:** Look at their meanings

`Splice:` join or connect (a rope or ropes) by interweaving the strands at the ends.

`Slice:` cut (something, especially food) into slices.

Ok. First I should thank Google for their meanings. Thank you, Google. 😃

Hope you got cleared to some extent.

**Tip 2:** Not a very intuitive tip but it is worth clearing your confusion a little more.
`Splice` — text `length` is greater than the `slice`. 
Based on which remember, the splice can take more params when compared to slice. See the declaration here:

`arr.splice(start, deleteCount, item1, item2, ..., itemN);`

`arr.slice(start, end);`

**Tip 3:** It's a technical tip here. Splice mutates original array whereas slice won’t. 

Just remember, if someone asks bread slice what would you do.

Don’t need to remember every tip. Just remember one that caught your attention.

➡️ Also, if you have remembered in another way. Please do comment.

**Now, tech stuff. What do they really do?**

**Splice first:**

It is an array method that works only on JS arrays. It removes, replaces, and/or adds new elements in the array.

mutates original array.

`splice(start, deleteCount, item1, item2, ..., itemN);`

`start` — where to start changing the array.

`deleteCount`— no.of elements to remove from the start and is optional. 

`item1, item2 and so on` — to add elements to the array after the start.

splice returns removed items in an array if none then returns an empty array.

%[https://gist.github.com/K-Vishwak/7a91e0fd55821b60177f56d949f4f69e#file-splice-js]

➡️ I hope, the above examples covered all scenarios. If you find any more interesting scenarios, please comment. I am very much happy to update the article with your suggestion any time.

**Slice now**

Slices the array and returns a shallow copy.

Doesn’t mutate (alter) the original array

slice(start, end); - slice from start (including) to end (excluding) and accepts negative values.

%[https://gist.github.com/K-Vishwak/36120f66e62597b5dcf958b9ccc7d7bb#file-slice-js]

Similar to `slice` in `Array`, there is a `slice` in `String` as well. Which also acts in the same manner but works on strings.

Thank you. 😊

