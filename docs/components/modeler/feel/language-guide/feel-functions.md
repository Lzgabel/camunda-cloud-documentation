---
id: feel-functions
title: Functions
description: "This document outlines various functions and examples."
---

### Invocation

Invokes a built-in function (e.g. [contains()](/docs/components/modeler/feel/builtin-functions/feel-built-in-functions-string#contains)) or user-defined
function by its name. The arguments of the function can be passed positional or named.

* Positional: Only the values, in the same order as defined by the function (e.g. `f(1,2)`).
* Named: The values with the argument name as prefix, in any order (e.g. `f(a: 1, b: 2)`).

```js
contains("me@camunda.com", ".com")
// true

contains(string: "me@camunda.com", match: ".de")
// false
```

### User-defined

```js
function(a,b) e
```

Defines a function with a list of argument names, and an expression (i.e. the function body). When
the function is invoked, it assigns the values to the arguments and evaluates the expression.

Within an expression, a function can be defined and invoked in a context.

```js
{
  age: function(birthday) (today() - birthday).years
}
```
