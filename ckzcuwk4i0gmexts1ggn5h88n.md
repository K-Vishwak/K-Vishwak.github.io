---
title: "Some X array utility functions in JS"
datePublished: Mon Feb 07 2022 15:36:05 GMT+0000 (Coordinated Universal Time)
cuid: ckzcuwk4i0gmexts1ggn5h88n
slug: some-x-array-utility-functions-in-js
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/8z2Q6XWLYa4/upload/v1644248077282/kcb5Q0v9x.jpeg
tags: javascript, hashnode, 100daysofcode, 2articles1week

---

`const array = [1,2,3,4,5];`

## Array Basic operations

### 1. Find the first item in the array
`console.log(array[0]);`
> 1

### 2. Find the last item in the array
`console.log(array[array.length - 1]);`
> 5

### 3. Addition of array values
`console.log(array.reduce((previousValue, currentValue) => previousValue += currentValue, 0));`
> 15

### 4. Arrange in descending order
`console.log(array.sort((a,b) => b-a));`
> [5,4,3,2,1]

### 5. Arrange in ascending order
`console.log(array.sort((a, b) => a-b));`
> [1,2,3,4,5]

### 6. Push item to array
`array.push(6);`

`console.log(array);`
> [1,2,3,4,5,6]

### 7. remove item from array
`array.pop();`

`console.log(array);`
> [1,2,3,4,5]

### 8. push item from beginning of an array
`array.unshift(0);`

`console.log(array);`
> [0,1,2,3,4,5]

### 9. remove the item from the beginning of an array
 `array.shift();`

`console.log(array);`
> [1,2,3,4,5]

### 10. slice array from index 3
`console.log(array.slice(3));`
> [4]

### 10. slice array in the range
`console.log(array.slice(3, 4));`
> [4]

### 11. Updated 3rd item with 0 in array
`array.splice(3, 1, 0);`

`console.log(array);`
> [1,2,3,0,5]

### 12. Convert to comma separated values
`console.log(array.toString());`
> '1,2,3,0,5'

### 13. Convert to comma separated using array method
`console.log(array.join());`
> '1,2,3,0,5'

### 14. Convert array to _ separated string
`console.log(array.join('_'));`
> '1_2_3_0_5'

### 15. update index 3 with value 4
`array[2] = 4;`

`console.log(array);`
> [1,2,3,4,5]

### 16. Merge two arrays
`const newArr = [6,7,8,9];`

`console.log(array.concat(newArr));`
> [1,2,3,4,5,6,7,8,9]

### 17. find max value from an array
`console.log(Math.max(...array));`
> 9

### 18. find min value from an array
`console.log(Math.min(...array));`
> 1

### 19. find index of a given number in array
`console.log(array.indexOf(4));`
> 3

### 20. find lastIndex of a given number in the array
`console.log(array.lastIndexOf(4));`
> 3

### 21. verify every element is greater than -1
`console.log(array.every(item => item > -1));`
> true

### 22. verify at least one element greater than 1
`console.log(array.some(item => item > 1));`
> true

### 23. Fill last two elements with number 1
`console.log(array.fill(1, 5));`
> [1,2,3,4,5,1,1,1,1]

### 24. Filter elements > 2
`console.log(array.filter(item => item > 2));`
> [3,4,5]

### 25. reverse array in place
`console.log(array.reverse());`
> [1,1,1,1,5,4,3,2,1]

### 26. remove falsy values from an array
`array.push(false, null, 0, undefined);`
`console.log(array);`

> [1,2,3,4,5,1,1,1,1,false, null, 0, undefined]

`console.log(array.filter(Boolean));`
> [1,2,3,4,5,1,1,1,1]

### 27. Multiply every item with 2
`console.log(array.map(item => item = item * 2));`
> [2,4,6,10,2,2,2,2]

### 28. Remove duplicates from an array
`console.log(...new Set(array));`
>[1,2,3,4,5]

### 29. capture only integers from an array
`array.push(1.23, 2.34);`
`console.log(array);`

> [1,2,3,4,5,1,1,1,1,1.23,2.34]


`console.log(array.filter(item => Number.isInteger(item)));`
> [1,2,3,4,5,1,1,1,1]

### 30. capture chunks of an array.
```
const firstArray  = [1,2,3,4,5];
const chunks = [];
for (let i = 0; i<firstArray.length;i+=2) {
    chunks.push(firstArray.slice(i, i+2));
}
console.log(chunks);
> [[1,2][3,4][5]]
```

