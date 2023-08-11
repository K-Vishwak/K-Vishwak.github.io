---
title: "JS Slice, Substring, Substr"
datePublished: Sat Jan 22 2022 11:30:49 GMT+0000 (Coordinated Universal Time)
cuid: ckypr3j1008do7js19xhq0wgd
slug: js-slice-substring-substr
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642851002053/G_TcVaPEH.png
tags: javascript, 100daysofcode

---

All these methods are used to extract part of given string.

**Declarations:**
- `slice(start, end);` - slice from start (including) to end (excluding) and accepts negative values.
- `substring(start, end);` - same like slice but won't accepts negative values.
- `substr(start, length);` - same like slice but second param is length.

Below examples explain the differences.

```
const testString = "Hey, Welcome to urstrulyvishwaks articles";

// slice.
testString.slice(5,12); // start including end excluding.
> 'Welcome'

testString.slice(5); // only start value - Hence starting from 5 to end.
> 'Welcome to urstrulyvishwaks articles'

testString.slice(-25, -10); // accepts negative range.
> 'urstrulyvishwak'

// substring.
testString.substring(5,12);
> 'Welcome'

testString.substring(5);
> 'Welcome to urstrulyvishwaks articles'

testString.substring(-25, -10); // Didn't return any result as it won't support.
> ''

// substr.
testString.substr(5,7); // second param is length
>'Welcome'

testString.substr(5);
> 'Welcome to urstrulyvishwaks articles'

testString.substr(-25, 15);
> 'urstrulyvishwak'
```

Slice detailed article: [here](https://vkglobal.hashnode.dev/js-slice)

