---
title: "JS String Search Methods"
datePublished: Sun Jan 23 2022 09:09:37 GMT+0000 (Coordinated Universal Time)
cuid: ckyr1hstb0iodans1hx1mc3a6
slug: js-string-search-methods
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642858662840/EQ02-xp7n.png
tags: javascript, web-development, 100daysofcode

---

### 1. indexOf

`inputStr.indexOf(str)` - returns `first` occurrence of mentioned `str` in given `inputStr`

`inputStr.indexOf(str, 10)` - returns `first` occurrence of string after 10 position.

```
const str = 'Hi, Welcome to Vishwaks JS articles';

str.indexOf('Welcome');
> 4

str.indexOf('Welcome', 10); // Search after 10th position.
> -1

const str = 'Hi, Welcome to Vishwaks JS articles - Welcome to JustCode';

str.indexOf('Welcome', 10); // Search after 10th position.
> 38

str.indexOf('hi'); // case sensitive
> -1
```

### 2. lastIndexOf

Same like indexOf but searches from end of the string.

`inputStr.lastIndexOf(str)` - returns `last` occurrence of mentioned `str` in given `inputStr`

`inputStr.lastIndexOf(str, 10)` - returns `last` occurrence of string from 10 index to beginning.

```
const testString = "locate string locate";

testString.lastIndexOf('locate');
> 14

testString.lastIndexOf('locate', 14);
> 14

testString.lastIndexOf('string');
> 7

testString.lastIndexOf('string', 6);
> -1

testString.lastIndexOf('string', 15);
> 7

testString.lastIndexOf('String'); // case sensitive
> -1

```
### 3. search

`search()` is same like `indexOf` but won't allow position param.

Whereas, `indexOf` won't support regex based search but `search()` supports it.

```
const str = 'Hi, Welcome to Vishwaks JS articles 1234';

str.search('Welcom');
> 4

str.search(/\d/);
> 36

str.search(1234);
> 36

str.search('welcome'); // case sensitive
> -1

```

### 4. match

`match()` searches specified string same like search but returns an array of matched strings.

```
const str = 'Hi, Welcome to Vishwaks JS articles 1234';

str.match('Hi');
> ['Hi', index: 0, input: 'Hi, Welcome to Vishwaks JS articles 1234', groups: undefined]

str.match('Welcome');
> ['Welcome', index: 4, input: 'Hi, Welcome to Vishwaks JS articles 1234', groups: undefined]

str.match(/\d/);
> ['1', index: 36, input: 'Hi, Welcome to Vishwaks JS articles 1234', groups: undefined]

str.match('hi'); // case sensitive
> null
```
### 5. includes

`includes()` returns true if string found.

```
const str = 'Hi, Welcome to Vishwaks JS articles 1234';

str.includes(1234);
> true

str.includes('JS');
> true

str.includes('test');
> false

str.includes('hi'); // case sensitive
> false

```

### 6. startsWith

Returns boolean if string starts with specified value.

`str.startsWith('test')` - if 'str' starts with 'test' then returns true otherwise false.

`str.startsWith('test', 10)` - 10th index in string starts with `test` or not.

```
const str = 'Hi, Welcome to Vishwaks JS articles';

str.startsWith('Hi');
> true

str.startsWith('Welcome', 4);
> true

str.startsWith('hi'); // case sensitive
> false
```

### 7. endsWith
Returns boolean if string ends with specified value.

`str.endsWith('test')` - if 'str' ends with 'test' then returns true otherwise false. 

`str.endsWith('test', 10)` - till 10th index in string ends with `test` or not.

```
const str = 'Hi, Welcome to Vishwaks JS articles';

str.endsWith('articles');
> true

str.endsWith('to', 14); // Check first 14 characters ends with to.
> true

str.endsWith('aRticles'); // case sensitive
> false
```

There are two more methods which are from `RegExp` are `test()` & `exec()` does the same.

`All the above methods are case sensitive methods.`
