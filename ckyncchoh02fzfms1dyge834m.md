---
title: "JS Binary Search"
datePublished: Thu Jan 20 2022 19:02:21 GMT+0000 (Coordinated Universal Time)
cuid: ckyncchoh02fzfms1dyge834m
slug: js-binary-search
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642701082798/W_V4u6WM5.png
tags: javascript, 100daysofcode

---

### Precondition
Array must be sorted first to apply binary search.
### Implementation
Which works on Divide (Divide into sub problems) & conquer(solve each problem and combine) approach.

## Approaches:

### 1. Recursive
a function calls itself is called recursive function.
```
const recursiveApproach = (array,searchItem,start,end)=>{

    // startIndex > endIndex then there no elements in input array.
    if (start >= end) {
        return -1;
    }

    // Divide array in middle.
    const mid = Math.floor((start + end) / 2);

    // You might find searchItem in middle itself. Hence to avoid recursive loop.
    if (array[mid] === searchItem) {
        return mid;
    }

    // Checking mid is greater than the searchItem.
    if (array[mid] > searchItem) {
        // if mid is greater, then we can search in between start and middle. 
        return recursiveApproach(array, searchItem, start, mid - 1);
    } else {
        // if mid is lesser, then we can search in between mid and end.
        return recursiveApproach(array, searchItem, mid + 1, end);
    }
}

const givenArr = [1, 2, 3, 4, 5];
recursiveApproach(givenArr, 5, 0, givenArr.length - 1);

> 4
```

We can improve a little:

```
const recursiveApproach = (array,searchItem,start,end)=>{

    if (start > end)
        return -1;

    if (array[start] === searchItem)
        return start;

    if (array[end] === searchItem)
        return end;

    const mid = Math.floor((start + end) / 2);

    if (array[mid] === searchItem)
        return mid;

    return array[mid] > searchItem ? recursiveApproach(array, searchItem, start, mid - 1) : recursiveApproach(array, searchItem, mid + 1, end);
}

const givenArr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
recursiveApproach(givenArr, 5, 0, givenArr.length - 1);
> 4

```
### 2. Iterative

```
const iterativeApproach = (array,searchItem)=>{
    // Initializing start and end.
    let start = 0;
    let end = array.length - 1;

    // Checking each iteration with start < = end.
    while (start <= end) {

        // dividing into middle.
        let mid = Math.floor((start + end) / 2);

        // if item found at middle.
        if (array[mid] === searchItem)
            return mid;

        else if (array[mid] < searchItem)
            // if item greater than mid. Search start from mid.
            start = mid + 1;
        else
            // else item is less than mid. Search between start & mid.
            end = mid - 1;
    }

    // if item not present return -1;
    return -1;
}

const givenArr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
iterativeApproach(givenArr, 11);

> 4
```

Time Complexity: O(logN).
Better than linear as it fallows O(n).

*Hence JS methods like `indexOf(), includes(), find() & findIndex()` slower than this binary search.*

%[https://twitter.com/urstrulyvishwak/status/1484241071660232705?s=20]