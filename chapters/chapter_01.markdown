# Values, Types, and Operators

### Values

There are six basic types of values:
- numbers
- strings
- booleans
- objects
- functions
- undefined

To create a value, invoke its name.

#### Numbers

JS uses a fixed number of bits: 64. With 64 binary digits it is possible to represent 2^64 different numbers (18 quintillion).

Negative numbers and decimal points also use these 64 digits, so the maximum _whole_ number in JS is ~9 quadrillion.

**Fractional numbers:** `9.81`

**Very small/large numbers:** `2.998e8 (2.998 * 10^8)`

Calculations < 9 quadrillion are guaranteed to be precise. Calculations with fractional numbers are generally not (i.e. pi).

##### Arithmetic

```js
100 + 4 * 11
(100 + 4) * 11
```

_When in doubt about the order of operations, add parentheses._

The the `%` symbol represents the _remainder_ operation (a.k.a. _modulo_). Remainder's precedence is the same as multiplication and divison.

##### Speical Numbers

These three numbers don't behave like normal numbers:

1. `Infinity`

2. `-Infinity`

_Infinity-based computation will quickly lead to `NaN`. Don't trust it._

3. `NaN`

_`NaN` ("not a number") is a value of the number type._

### Strings

Strings are used to represent text:

```js
'I love scotch'
"I'm gonna punch you right in the ovary"
```

Use single _or_ double quotes, just make sure they match.

Almost anything can go inbetween quotes, except characters like _newlines_. To put a newline in a string, use `\n`.

e.g. "This is the first line \nAnd this is the second"

prints as

```js
This is the first line
And this is the second
```

The + operator can be used to _concatenate_ strings:

```js
"con" + "cat" + "e" + "nate"
```

### Unary Operators

Not all operators are symbols; some are written as words:

```js
console.log(typeof 4.5)
// -> number
console.log(typeof "x")
// -> string
```

Operators that use two values are called _binary_ operators, while those that only take one (i.e. `typeof`) are called _unary_ operators. Minus can be used as binary or unary:

```js
console.log(- (12 - 6))
// -> -6
```

### Boolean Values

`true` and `false`

##### Comparisons

```js
console.log(1 > 2)
// -> true
console.log(2 < 1)
// -> false
```

The > and < symbols ("is greater/less than") are binary operators.

Strings can be compared just like numbers:

```js
console.log("Aardvark" < "Zoroaster")
// -> true
```

Uppercase letters are always "less" than lowercase ones, so "Z" < "a" is true, and nonalphabetic characters (!, -, etc.) are also included in the ordering. The actual comparison is based on the Unicode standard.

When comparing strings, JavaScript goes over them from left to right, comparing numeric codes of characters one by one.

```js
console.log("Itchy" != "Scratchy")
// -> true
```

The only value in JavaScript that is not equal to itself is `NaN` ("not a number").


##### Logical Operators

Some operations can be applied to Boolean values: `and`, `or`, and `not`. These can be used to "reason" about Booleans.

The && operator represents logical _and_. It is a binary operator, and its result is true only if both values given to it are true.

```js
console.log(true && false)
// -> false
console.log(true && true)
//-> true
```

The || operator denotes logical _or_. It produces true if either of the values are given to it are true.

```js
console.log(false || true)
//-> true
console.log(false || false)
//-> false
```

Not is written as an exclamation mark(!). It is a unary operator that flips the value given to it.

```js
!true
//-> false
!false
//-> true
```

Expressions like the following do not need parentheses:

`1 + 1 == 2 && 10 * 10 > 50`

The last logical operator we will discuss is not unary, not binary, but _ternary_, operating on all three values. It is written with a question mark and a colon, like this:

```js
console.log(true ? 1 : 2);
// -> 1
console.log(false ? 1 : 2);
// -> 2
```

This one is called the _conditional_ operator (or sometimes just _ternary_ operator since it is the only such operator in the language). The value on the left of the question mark "picks" which of the other two values will come out. When it is true, the middle value is chosen, and when it is false, the value on the right comes out.

### Undefined Values

Two special values: `null` and `undefined`, that are u sed to denote teh absense of a meaningful value. They themselves are values, but carry no information.

### Automatic Type Conversion

Here's JavaScript doing some weird shit:

```js
console.log(8 * null)
// -> 0
console.log("5" - 1)
// -> 4
console.log("5" + 1)
// -> 51
console.log("five" * 2)
// -> NaN
console.log(false == 0)
// -> true
```

When an operator is applied to the "wrong" type of value, JavaScript will quietly convert that value to the type it wants. This is process is called _type coercion_.

When something that doesn't map to a number in an obvious way (such as `"five"` or `undefined`) is converted to a number, the value NaN is produced. Further arithmetic operations on NaN keep producing NaN, so if you find yourself getting one of those in an unexpected place, look for accidental type conversions.

More weird shit:

```js
console.log(null == undefined)
// -> true
console.log(null == 0)
// -> false
```

That last piece of behavior is often useful. When you want to test whether a value has a real value instead of `null` or `undefined`, compare it to `null` with the `==` or `!=` operators.


Boolean values state that `0`, `Nan`, and the empty string`""` count as `false`, while all other values count as `true`. If you want to test whether something refers to the precise value `false`, use either `====` or `!==`.

It is recommended practice to use three-chracter comparison operators defensively to prevent unexpected type conversions.

##### Short-Circuiting of Logical Operators

When `&&` and `||` handle values of different types, they convert the value on the left side to a Boolean, and, depending on the operator and the result of that conversion, return either the _original_ left-hand value or the right-hand value.

The `||` operator, for example, will return the value to its left when it can be converted ot true, and will return the value on the right otherwise.

```js
console.log(null || "user")
//-> user
console.log("Karl" || "user")
//-> Karl
```

This functionality allows the `||` operator to be used as a way to fall back on a default value. If you give it an expression that might produce an empty value on the left, the value on the right will be used as a fallback.

The `&&` operator works the other way around. When the value to its left is somethign that evaluates to false, it returns that value, otherwise it returns the value on its right.

With both `&&` and `||`, the expression on the right is only evaluated when necessary. This is called _short-circuit evaluation_.

### Summary

We looked at four types of JavaScript values in this chapter: numbers, strings, Booleans, and undefined values. You can combine and transform values with operators. We saw binary operators for arithmetic (+, -, *, /, and %), string concatenation (+), comparison (==, !=, ===, !==, <, >, <=, >=), and logic (&&, ||), as well as several unary operators (- to negate a number, ! to negate logically, and typeof to find a value's type).
