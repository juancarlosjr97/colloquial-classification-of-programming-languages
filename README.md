# Colloquial Classification of Programming Languages

> There is no precise technical definition of what the terms mean and different authors disagree about the implied meaning of the terms and the relative rankings of the "strength" of the type systems of mainstream programming languages. (Strong and weak typing - Wikipedia, 2022)

These definitions were not defined by me. I have grouped information from multiple sites, books and different authors to create a more or less definitions and examples that could fit with the "generally" accepted definitions according to my online research

## Classifications

### Strongly typed

Strongly-typed languages do not allow implicit conversions between unrelated types. Strong typing, you will only be allowed operations on the data by direct manipulation of the objects of that data type. Variables and other data structures can be declared to be of a specific type and check the validity of their values

### Weakly Typed - Loosely Typed - Untyped Language

Weakly-type languages make conversions between unrelated types implicitly. Weak typing allows you to operate on data without considering its type. You do not have to specify what type of information will be stored in a variable in advance

### Dynamic Typing

Dynamically-typed languages perform type checking at runtime

### Static Typing

Statically typed languages perform type checking at compile time

## Examples

### Python

* Strongly typed: Variable type `str` does not allow operations with type `int` ot any other type different to `str`

This will fail as the variable are not compatible

```python
variable_name: str = "Juan"
variable_number: int = 97
result_error = variable_name + variable_number
```

* Dynamic typing: A variable type can be updated during runtime

This will finish successfully as the `variable_number` initially as type number has been assigned `Carlos` as the value

#### Example 1

```python
variable_name: str = "Juan"
variable_number: int = 97
variable_number = "Carlos"
result_success = variable_name + variable_number
```

#### Example 2

```python
variable_number: int = 97
variable_number = "Carlos"
```

### JavaScript

* Weakly typed: Variable type `string` allow operations with type `number`

This will pass as JavaScript allows implicit conversion between unrelated types during runtime.

```js
let variableName = "Juan"
let variableNumber = 97
let resultSuccess = variableName + variableNumber 
```

* Dynamic typing: A variable type can be updated during runtime

This will finish successfully as the `variableName` can change its type dynamically

```js
let variableName;
variableName = "Juan";
variableNumber = 97;
```

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

#### Important note

As TypeScript is a superset of JavaScript that will allow ignore rules set by TypeScript to use dynamically typing

By not adding a variable type, by default the `variableName` has type `any`. The following example will pass successfully

```ts
let variableName;
variableName = "Juan";
variableName = 97;
```

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
