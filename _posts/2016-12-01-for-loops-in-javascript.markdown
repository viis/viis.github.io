---
layout: post
title:  "For loops in Javascript"
date:   2016-12-01 22:00:00 +0100
categories: post
---

I have been writing some Javascript code lately. As a fan of Python, I was hoping that modern Javascript offered an
equivalent to Python's `for x in y` construct. After much reading and some confusion, I now know that JS offers many
ways to do a for loop, and that these differ in non-intuitive ways. So, here is an overview of the for loops I've
encountered.

## The classic C-style loop with a counter and a condition

This style of loop is common in other languages, and will be familiar to many. The syntax is verbose and error prone.
Not recommended.

```javascript
var arr = [1,2,3];
for (var i=0; arr.length>i;i++) {
  console.log(i);
}
// Output:
// 1
// 2
// 3
```

## The for .. of loop

Although somewhat awkwardly named, this is very similar to Python's `for x in y`, and exactly was I was looking for.
Recommended for most purposes, but only works in browsers compatible with ES2015, and thus only safe to use if you
compile your code with Babel (or something similar).

```javascript
let arr = [1,2,3];
for (let i of arr) {
  console.log(i);
}
// Output:
// 1
// 2
// 3
```

## The for .. in loop

Looks good, but might not work as you expect. `for .. in` loops over the properties of an *object*, in
**arbitrary order**. Stay away from this one unless you know what you are doing!

```javascript
let arr = [1,2,3];
for (let i in arr) {
  console.log(i);
}
// Output:
// 0 (array index, not value!)
// 1
// 2
```

## The forEach loop

`forEach` is not a statement, but a method of an Array object. Nonetheless, it can serve as a for loop, and allows one
to apply a function to each element for an array. `forEach` does differ from a loop statement in that a `break`
statement has no effect inside of a `forEach` loop. The only way to break out of `forEach` is to throw an exception.

```javascript
let arr = [1,2,3];
arr.forEach(i => console.log(i));
// Output:
// 1
// 2
// 3
```

## Map

Like `forEach`, `map` is an Array method. It works like `forEach`, but returns a new array, with the provided function
applied to each element of the original array.

```javascript
let arr = [1,2,3];
console.log(arr.map(i => i*2));
// Output
// [2, 4, 6]
```
