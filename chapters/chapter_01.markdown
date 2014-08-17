# Values, Types, and Operators

### Values

Six basic types of values:
- numbers
- strings
- booleans
- objects
- functions
- undefined

To create a value, you invoke its name.

#### Numbers

Javascript uses a fixed number of bits: 64. Given 64 binary digits, you can represent 2^64 different numbers (18 quintillion).

Not all whole numbers below 18 quintillion fit in a JS number - those bits also store negative numbers and decimal points. THe actual maximum whole number is ~9 quadrillion.

**Fractional numbers:** `9.81`

**Very small/large numbers:** `2.998e8 (2.998 * 10^8)`

Calculations < 9 quadrillion are guaranteed to be precise. Calculations with fractional numbers are generally not (i.e. pi).

##### Arithmetic

`100 + 4 * 11`

`(100 + 4) * 11`

_When in doubt about the order of operations, add parentheses._

The the `%` symbol is used to represent the _remainder_ operation. Remainder's precedence is the same as that of multiplication and division. You'll often see this operator referred to as _modulo_, though technically _remainder_ is more accurate.

##### Speical Numbers

There are three special values in JS that are _considered_ numbers, but don't _behave_ like normal numbers:

1. `Infinity`

2. `-Infinity`

Don't trust infinity-based computation. It isn't mathematically solid, and qill quickly lead to `NaN`.

2. `NaN`

`NaN` stands for "not a number", even though it is a value of the number type.

### Strings

The next basic data type is the _string_. Strings are used to represent text:

`"Patch my boat with chewing gum"`

`"Monkeys wave goodbye"`

Both single quotes and double quotes can be used to mark strings as long as the quotes at the start and the end of the string match.

Almost anything can be put in between quotes, with a few exceptions:

1. Newlines. Newlines can't be put between quotes.

To put a newline in a string, use a backslash to escape the character that follows: `\n` is a newline.

e.g. "This is the first line \nAnd this is the second"

```
This is the first line
And this is the second
```

Strings cannot be divided, multiplied, or subtracted, but the + operator can be used to concatenate them:

```
"con" + "cat" + "e" + "nate"
```

### Unary Operators

Not all operators are symbols; some are written as words.

```
console.log(typeof 4.5)
// -> number
console.log(typeof "x")
// -> string
```

Operators (like `typeof`) that use two values are called _binary_ operators, while those that only take one are called _unary_ operators. The minus operator can be used both as a _binary_ operator and as a _unary_ operator:

```
console.log(- (10 - 2))
// -> -8

### Boolean Values

`true` and `false`

##### Comparisons

```
console.log(3 > 2)
// -> true
console.log(3 < 2)
// -> false
```

The > and < signs are the traditional symbols for "is greater than" and "is less than", respectively. They are binary operators.

Strings can be compared just like numbers:

```
console.log("Aardvark" < "Zoroaster")
// -> true
```

Uppercase letters are always "less" than lowercase ones, so "Z" < "a" is true, and nonalphabetic characters (!, -, etc.) are also included in the ordering. The actual comparison is based on the Unicode standard.

When comparing strings, JavaScript goes over them from left to right, comparing numeric codes of characters one by one.

```
console.log("Itchy" != "Scratchy")
// -> true
```

The only value in JavaScript that is not equal to itself is `NaN` ("not a number").


##### Logical Operators

Some operations can be applied to Boolean values: `and`, `or`, and `not`. These can be used to "reason" about Booleans.

The && operator represents logical _and_. It is a binary operator, and its result is true only if both values given to it are true.

```
console.log(true && false)
// -> false
console.log(true && true)
//-> true
```

The || operator denotes logical _or_. It produces true if either of the values are given to it are true.

```
console.log(false || true)
//-> true
console.log(false || false)
//-> false
```

Not is written as an exclamation mark(!). It is a unary operator that flips the value given to it.

```
!true
//-> false
!false
//-> true
```

Expressions like the following do not need parentheses:

`1 + 1 == 2 && 10 * 10 > 50`

The last logical operator we will discuss is not unary, not binary, but _ternary_, operating on all three values. It is written with a question mark and a colon, like this:

```
console.log(true ? 1 : 2);
// -> 1
console.log(false ? 1 : 2);
// -> 2
```

This one is called the _conditional_ operator (or sometimes just _ternary_ operator since it is the only such operator in the language). The value on the left of the question mark "picks" which of the other two values will come out. When it is true, the middle value is chosen, and when it is false, the value on the right comes out.

### Undefined Values

Two special values: `null` and `undefined`, that are u sed to denote teh absense of a meaningful value. They themselves are values, but carry no information.




