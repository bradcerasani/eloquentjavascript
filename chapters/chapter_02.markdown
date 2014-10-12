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
```

A single `var` statement can define multiple variables if the definitions are separated by commas.

### Keywords and Reserved Words

Some words in Javascript are keywords or reserved words, and may not be used as variable names. Here's a tatse:

- break
- case
- catch
- continue
- debugger
- default
- delete
- do
- else
- false
- finally
- for
- function
- if
- implements
- in
- instanceof
- interface
- let
- new
- null
- package
- private
- protected
- public
- return
- static
- switch
- throw
- true
- try
- typeof
- var
- void
- while
- with
- yield
- this

If a variable definition is doing something weird, make sure you aren't using one of these reserved words.

### The Environment

The collection of variables and their values is called the _environment_. Some variables are part of the language standard, and some provide ways to interact with the surrounding system (i.e. a browser).

### Functions

A function is a piece of program wrapped in a value. In a browser environment, the variable `alert` holds a function that displays a dialog box with a message.

 ```js
 alert("Hello world");
```

Executing a function is called invoking, calling, or applying it.

Functions can take in values known as _arguments_. The `alert` function only requires one argument (a string) while other functions may need more or differnt arguments.

### The `console.log` Function


