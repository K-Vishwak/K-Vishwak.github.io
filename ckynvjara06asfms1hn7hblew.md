---
title: "JS Best ways to verify isNumber, isBoolean, isString, isObject, isArray, isInteger, isFunction"
datePublished: Fri Jan 21 2022 03:59:31 GMT+0000 (Coordinated Universal Time)
cuid: ckynvjara06asfms1hn7hblew
slug: js-best-ways-to-verify-isnumber-isboolean-isstring-isobject-isarray-isinteger-isfunction
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642781230977/9093CAcxp.png
tags: javascript, 100daysofcode

---

Basically,

```
typeof 1;
'number'

typeof 1.2;
'number'

typeof NaN;
'number'

typeof false;
'boolean'

typeof '';
'string'

typeof function () {};
'function'

typeof undefined;
'undefined'

typeof null;
'object'

typeof {};
'object'

typeof [];
'object'
```

Use above as reference and write `isFunctions` now:

### isNumber

```
const isNumber = value => typeof value === 'number' && !isNaN(value);

isNumber(1);
true

isNumber(1.2);
true

isNumber(-1);
true

isNumber(-1.2);
true

isNumber(01);
true

isNumber(00);
true

isNumber(Infinity);
true

isNumber(-Infinity);
true

isNumber(NaN);
false

isNumber(undefined);
false

isNumber(true);
false

isNumber('23');
false

isNumber(null);
false

isNumber('');
false

isNumber('23');
false

isNumber([]);
false

isNumber({});
false

isNumber(function () {})
false
```

(+/-)Infinity are of type number in javascript as if you want to avoid then you can update logic as:

```
const isNumber = value => typeof value === 'number' && !isNaN(value) && isFinite(value);
undefined

isNumber(Infinity);
false

isNumber(-Infinity);
false
```

### isBoolean

```
isBoolean = value => typeof value === 'boolean';

isBoolean(true);
true

isBoolean(false);
true

isBoolean('test');
false

isBoolean(1);
false

isBoolean(0);
false

isBoolean(undefined);
false

isBoolean(null);
false

isBoolean([]);
false

isBoolean(NaN);
false

isBoolean({});
false

isBoolean(function () {});
false
```

### isString

```
const isString = value => typeof value === 'string';

isString('test');
true

isString(undefined);
false

isString(null);
false

isString(undefined);
false

isString({});
false

// you can validate remaining as they return false.
```

### isObject

```
isObject = value => typeof value === 'object';

isObject({});
true

isObject([]); // failed.
true

isObject(null); // failed.
true

isObject = value => value !== null && !Array.isArray(value) && typeof value === 'object';

isObject({});
true

isObject(null);
false

isObject([]);
false
```
### isArray
```
// you can directly use Array.isArray(value);

isArray = value => Array.isArray(value);

isArray([]);
true

isArray({});
false

isArray(null);
false

// Validate for other values.
```
### isFunction

```
isFunction = value => typeof value === 'function';

isFunction(function() {});
true

isFunction(null);
false

isFunction(undefined);
false

isFunction({});
false
```
### isInteger

We can use `Number.isInteger(value)`


Yes. There are some exceptions based on where do we use these functions.

Please do suggest if I miss any mandatory validations in above isFunctions.

Thank you!

