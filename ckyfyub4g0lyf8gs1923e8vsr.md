---
title: "JS Linear Search"
datePublished: Sat Jan 15 2022 15:09:54 GMT+0000 (Coordinated Universal Time)
cuid: ckyfyub4g0lyf8gs1923e8vsr
slug: js-linear-search
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642259055795/BqcdaYJY4.png
tags: javascript, 100daysofcode

---

Sequentially checks the target value in given list and match found.

Time Complexity:
     best  :  O(1)
     Worst: O(n)

Space Complexity:  O(1)

```
function linearSearch(arr, target) {
    for (let i in arr) {
        if(arr[i] === target) return i;
    }
return -1;
};

linearSearch([1,2,3,4], 3);
> '2'
linearSearch([1,2,3,4], 5);
> -1
```

Linear search is best to use while searching in unsorted array.

JS `indexOf(), includes(), find() & findIndex()` implemented using linear search.