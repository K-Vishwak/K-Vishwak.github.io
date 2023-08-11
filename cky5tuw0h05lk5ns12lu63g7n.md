---
title: "JS Destructuring"
datePublished: Sat Jan 08 2022 12:52:42 GMT+0000 (Coordinated Universal Time)
cuid: cky5tuw0h05lk5ns12lu63g7n
slug: js-destructuring
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1641644464991/eX1yFpZ5R.png
tags: javascript, 100daysofcode

---

[Twitter](https://twitter.com/urstrulyvishwak/status/1471178299967639554?s=20)  [Youtube](https://youtu.be/pHznPwz3Cls)


%[https://youtu.be/pHznPwz3Cls]
 

Different ways in array destructuring:

![4.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645563547/h3HD6Aey5.png)

You can skip items you don't want:

![5.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645592621/xy3EvHoep.png)

When you want to assign only few variables and rest as separate:

![6.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645619275/ql-OUOXQv.jpeg)

You can also set default values:

![7.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645659354/sogDC3am8.png)

assign variables via destructering:

```
const DAYS = {
  yesterday: 0,
  today: 1,
  tomorrow: 2
};
  
const {today: todayCount, tomorrow: tomorrowsCount  }  = DAYS;

console.log(todayCount);
> 1
console.log(tomorrowsCount);
> 2

```

assign variables for nested objects:

```
const DAYS = {
  yesterday: { low: 0, high: 1 },
  today: { low: 1, high: 2 },
  tomorrow: { low: 2, high: 3 }
};
  
const {today: {low: lowToday, high: highToday }} = DAYS;

console.log(lowToday);
> 1
console.log(highToday);
> 2
```

Swap using destructuring:

![8.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645691615/7nCDlDg8V.png)

We can also destructure nested ones like:

![9.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645726182/7JTsRaFHI.png)

We can also achieve multi array destrcuturing:

![10.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1641645749172/Rdme-O3KK.jpeg)



%[https://twitter.com/urstrulyvishwak/status/1471178299967639554?s=20]
