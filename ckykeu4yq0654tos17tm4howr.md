---
title: "JS Declarative VS Imperative"
datePublished: Tue Jan 18 2022 17:48:45 GMT+0000 (Coordinated Universal Time)
cuid: ckykeu4yq0654tos17tm4howr
slug: js-declarative-vs-imperative
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1642526614290/AkY0FiYEE.png
tags: javascript, 100daysofcode

---

 [Twitter](https://twitter.com/urstrulyvishwak/status/1483497277927079936?s=20) [Youtube](https://youtu.be/MMD-75-8dv0) 


%[https://youtu.be/MMD-75-8dv0]


These are programming paradigms:

Declarative: tells `What to do`

Imperative: tells `How to do`

**Example: Find the employees with dept 'justCode' and summation of their salary.**

### Imperative Style:

```
const employees = [
{id: 1, name: 'james', dept: 'admin', salary: 10000},
{id: 1, name: 'Tom', dept: 'finance', salary: 10000},
{id: 1, name: 'peter', dept: 'justCode', salary: 12500},
{id: 1, name: 'tunner', dept: 'justCode', salary: 14500},
];

const justCodeDept = [];

// filter employees based on dept name.
for (let i=0; i<employees.length; i++) {
  if (employees[i].dept === 'justCode') {
    justCodeDept.push(employees[i]);
  }
}

// summation of justCodeDept employees.
let summation = 0;
for (j = 0; j<justCodeDept.length; j++) {
  summation = summation + justCodeDept[j].salary;
}

console.log(summation);
```
### Declarative Style:

```
const employees = [
{id: 1, name: 'james', dept: 'admin', salary: 10000},
{id: 1, name: 'Tom', dept: 'finance', salary: 10000},
{id: 1, name: 'peter', dept: 'justCode', salary: 12500},
{id: 1, name: 'tunner', dept: 'justCode', salary: 14500},
];

console.log(employees.filter(item => item.dept === 'justCode').reduce(((previousValue, currentValue) => previousValue += currentValue.salary), 0));
```