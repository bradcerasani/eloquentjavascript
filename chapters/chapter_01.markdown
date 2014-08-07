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



