# Program Structure

### Expressions and Statements

A fragment of code that produces a value is called an _expression_, as is a value written literally, i.e. `"41"` or `"waffles"`.

In english language terms, _expression_ == sentence fragment, _statement_ == full sentence.

The simplest kind of statement is an expression with a semicolin after it. This is a program:

```js
1;
!false;
```

### Variables

Variables set and hold values:

```js
var bacon = 5 * 5;
```

`var` indicates that this statement is going to define a variable. Once a variable is defined, it can be used in an expression:

```js
var ten = 10;
console.log(ten * ten);
// -> 100
```

Variable names _may not_ contain reserved keywords (such as var), spaces, or puctuation other than `$` or `_`.

Variable names _may_ contain digits, as long as the name doesn't start with a digit.

The `=` operator can be used to change the value of a variable anytime.

```js
var mood = "light";
console.log(mood);
// -> light
mood = "dark";
console.log(mood);
// -> dark

Variables are like tentacles; they do not _contain_ values; they _grasp_ them.

Let's say Luigi owes me money:

```js
var luigisDebt = 140;
luigisDebt = luigisDebt - 35;
console.log(luigisDebt);
// -> 105
