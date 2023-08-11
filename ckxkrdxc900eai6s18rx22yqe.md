---
title: "JS reduce"
seoTitle: "JS Reduce"
datePublished: Fri Dec 24 2021 19:00:21 GMT+0000 (Coordinated Universal Time)
cuid: ckxkrdxc900eai6s18rx22yqe
slug: js-reduce
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1640405883973/vDkIXI4ku.png
tags: javascript, functional-programming

---


1. Returns single value.
2. Doesn't mutate original array.
3. Doesn't execute the function for empty array elements.
4. Syntax: `array.reduce(function(previousValue, currentValue, currentIndex, arr), initialValue);`


![reduce1.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371675485/1f_8IyFD8.jpeg)

`previousValue:` value resulting from the previous call to callBackFn. On first call, `initialValue` if specified otherwise `array[0]`.

`currentValue:` value of the current element.On the first call, the value of array[0] if `initialValue` specified otherwise `array[1]`.

`currentIndex:` currentValue index. On first call it is 0 if `initialValue` specified otherwise 1.


![reduce2.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371885178/gASLw-Z0n.jpeg)

**Examples**


![reduce3.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371969868/QGmRI-Rbr.jpeg)

---------------------

![reduce4.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371977814/JfAEq0jVa.jpeg)

---------------------

![reduce5.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371984743/5Pdk5ZdSD.jpeg)

-----------------------
Functional Composition:

![reduce6.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1640371992374/BROpA6cQp.jpeg)

In above, example `input` is function returned by `(...functions)` as we are calling `multiply6(6)`.
Hence input is 6.

Reference:   [MDN official](https://developer.mozilla.org/en-US/) 

Thank you. :) 