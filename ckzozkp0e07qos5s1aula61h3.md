---
title: "Magic of window.open in browsers"
datePublished: Wed Feb 16 2022 03:20:03 GMT+0000 (Coordinated Universal Time)
cuid: ckzozkp0e07qos5s1aula61h3
slug: magic-of-windowopen-in-browsers
cover: https://cdn.hashnode.com/res/hashnode/image/unsplash/abkEAOjnY0s/upload/v1644981446050/cNzWddjEP.jpeg
tags: javascript, web-development, hashnode, 2articles1week

---

The `window` object is supported by most modern browsers. It represents the browser window. The `window` is the root object and every other javascript object, function, variables are members of it.

It has some properties and methods. Here, we are going to see about window.open which we mostly use when we want to open a new window to perform some action.

**Window.open()** - open a new window and returns the `windowProxy` object which is the wrapper on the window object.

**Syntax:**

`window.open(?url, ?target, ?features)` - all three params are optional.

`url` - url to navigate for.

`target` - window name - it opens a new window if a window with that name doesn't exist otherwise simply focus the existing and reloads.

`features` - browser features like width, height etc.

// -> Opens up a pop-up with  the mentioned URL with name `JS_Articles` (Its not a browser title)

`const windowObj = window.open('https://hashnode.com/@urstrulyvishwak', 'JS_Articles', 'popup');`

// -> Focus window - if the 'JS_Articles' window is behind the current browser then it will get focused.

`windowObj.focus();`

// -> blur window - out focus the window as opposed to focusing.

`windowObj.blur();`

// -> Count of windows opened in current window starting with index 0.

`windowObj.length;`

// -> close - to close the window

`windowObj.close();`

// -> closed - it returns boolean and tells whether the window has opened or closed.
`windowObj.closed;`

Using these properties we can completely deal with a new window that we opened. 

Thank you :). Happy reading.





