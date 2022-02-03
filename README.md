# Colloquial Classification of Programming Languages

> There is no precise technical definition of what the terms mean and different authors disagree about the implied meaning of the terms and the relative rankings of the "strength" of the type systems of mainstream programming languages. (Strong and weak typing - Wikipedia, 2022)

These definitions were not defined by me. I have grouped information from multiple sites, books and different authors to create a more or less definitions and examples that could fit with the "generally" accepted definitions according to my online research

## Classifications

### Strongly vs Weakly Typed

#### Strongly typed

Strongly-typed languages do not allow implicit conversions between unrelated types. Strong typing, you will only be allowed operations on the data by direct manipulation of the objects of that data type. Variables and other data structures can be declared to be of a specific type and check the validity of their values

#### Weakly Typed - Loosely Typed - Untyped Language

Weakly-type languages make conversions between unrelated types implicitly. Weak typing allows you to operate on data without considering its type. You do not have to specify what type of information will be stored in a variable in advance

### Static vs Dynamic Typing

#### Dynamic Typing

Dynamically-typed languages perform type checking at runtime

#### Static Typing

Statically typed languages perform type checking at compile time

## Examples

### Go

* Strongly Typed: Allowing at any point to know exactly what type of value each variable and allow operations according to their type

#### Example 1

```go
package main

func main() {
    var variableName string = "Juan"
    var variableNumber int = 97
    variableName = variableNumber
}
```

The above example will fail to compile as `variableName` is type `string` and `variableNumber` is type `int` with the error message `cannot use 97 (type untyped int) as type string in assignment`

* Statically Typing: Go is a statically typed as a type is expected when declaring new variables

#### Example 2

This example will fail to compile

```go
package main

func main() {
    var variableName
}
```

The error when running the go compiler will be `syntax error: unexpected newline, expecting type` as the variable `variableName` is missing the type declaration or initial value to identify the type

### Python

* Strongly typed: Variable type `str` does not allow operations with type `int` ot any other type different to `str`

This will fail as the variable are not compatible

```python
variable_name: str = "1"
variable_number: int = 97
result_error = variable_name + variable_number
```

This will fail as the result would be `Line 3 - TypeError: can only concatenate str (not "int") to str`

* Dynamic typing: A variable type can be updated during runtime

This will finish successfully as the `variable_number` initially as type number has been assigned a value of type `string` during runtime

#### Example 1

```python
variable_name: str = "Juan"
variable_number: int = 97
variable_number = "Carlos"
result_success = variable_name + " " + variable_number
```

The `result_success` will have a value of `Juan Carlos`

#### Example 2

```python
variable_number: int = 97
variable_number = "Juan"
```

The variable `variable_number` initially declared as `integer` can be modified during runtime to hold a value of type `string` as `Juan`

### PHP

* Weakly typed: Variable type `string` allow operations with type `integer`

#### Example 1 

This will pass as the variable `$variable_string_number` is a string integer

```php
$variable_string_number = "1"
$variable_number = 97
$result_success = $variable_string_number + $variable_number
```

The result of the above operation would be `98` of type `integer`, as `$variable_string_number` is a numeric string

#### Example 12

This will fail as the variable `$variable_string` is a string and does not allow arithmetic operation between non numeric strings and `integer` types

```php
$variable_string_number = "Juan"
$variable_number = 97
$result_fail = $variable_string_number + $variable_number
```

The result of the above operation would be `Uncaught TypeError: Unsupported operand types: string + int [...]:3`

### JavaScript

* Weakly typed: Variable type `string` allow operations with type `number`

This will be executed successfully as JavaScript allows implicit conversion between unrelated types during runtime.

```js
let variableName = "Juan"
let variableNumber = 97
let resultSuccess = variableName + variableNumber 
```

The value that `resultSuccess` that will have at the end is `Juan97`

* Dynamic typing: A variable type can be updated during runtime

This will finish successfully as the `variableName` can change its type dynamically

```js
let variableName;
variableName = "Juan";
variableNumber = 97;
```

The value that `variableNumber` will have at the end of the execution will be `97` and type of `number`

### TypeScript

* Strongly typed: This will fail as Typescript does type check during compile

```ts
let variableName = "Juan";
variableName = 5; //Type 'number' is not assignable to type 'string'.
```

* Statically typing: TypeScript through type annotations enables type checking at compile time to avoid error

This will fail as the `variableName` cannot be updated with a value that is not type of `string`

```ts
let variableName: string;
variableName = "Juan";
variableName = 97; //Type 'number' is not assignable to type 'string'.
```

**Important note**

As TypeScript is a superset of JavaScript that will allow ignore rules set by TypeScript to use dynamically typing using `any` that will be the equivalent to `untyped` variable on JavaScript

#### Example 1

By not adding a variable type, by default the `variableName` has type `any`. The following example will pass successfully

```ts
let variableName;
variableName = "Juan";
variableName = 97;
```

After compilation, and executing the variable `variableName` will have the value `97` and will be type of `number`

#### Example 2

By adding a variable type as `string` and adding `@ts-ignore`. The following example will pass and compile to JavaScript successfully

```ts
let variableName: string;
variableName = "Juan";
//@ts-ignore
variableName = 97;
```

## References

* Artima.com. 2003. Typing: Strong vs. Weak, Static vs. Dynamic. [online] Available at: <https://www.artima.com/weblogs/viewpost.jsp?thread=7590> [Accessed 3 February 2022].

* Docs.oracle.com. 2015. Dynamic typing vs. static typing. [online] Available at: <https://docs.oracle.com/cd/E57471_01/bigData.100/extensions_bdd/src/cext_transform_typing.html> [Accessed 3 February 2022].

* Educative: Interactive Courses for Software Developers. 2022. Statically v. dynamically v. strongly v. weakly typed languages. [online] Available at: <https://www.educative.io/edpresso/statically-v-dynamically-v-strongly-v-weakly-typed-languages> [Accessed 3 February 2022].

* Wikipedia. 2022. Strong and weak typing - Wikipedia. [online] Available at: <https://en.wikipedia.org/wiki/Strong_and_weak_typing> [Accessed 3 February 2022].

* Medium. 2020. Understanding JavaScript: Coercion in a Dynamically Typed Language. [online] Available at: <https://levelup.gitconnected.com/understanding-javascript-coercion-in-a-dynamically-typed-language-8807d6331fa2> [Accessed 3 February 2022].

* Pratt, T. and Zelkowitz, M., 2001. Programming languages. Upper Saddle River, NJ: Prentice-Hall.

* Tate, B., 2005. Beyond Java. Beijing: O'Reilly.
