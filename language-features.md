# Y-flat language examples

## Current Features

### Variable and Function Declarations
Type names come after the type. For functions, no stated return type is taken as
a return type of `void`.
```
x: int;
f(param1: int, param2: int): int {
    ret: int = param1 + param2;
    return ret;
}
do_a_thing() {

}
```

A return statement must always be run in a function that returns a value.
```
~~ Error ~~
x(p: int): int {
    if (p < 3)
        return 7;
}
```

### Expressions, Function Calls, and Literals
An expression is either a function call, a binary expression, or a literal.
Unary operators are not yet implemented.
```
my_func(): int { return 5; }
x1: int = my_func();
x2: int = 2 * (my_func() + my_func());
x3: int = 5;
x4: bool = true;
```

### Types
There are a number of builtin types in Y-flat. Most prominent are a built-in
`bool` type (unlike C) and builtin `i16, i32, i64, f32, f64`.

### Casting
Variables may be cast more or less freely, although the compiler will warn if
casting may lose information.

## Planned features
- Switch statements and expressions, including `fswitch` with automatic breaking
- Built-in project management and dependency location
- Arrays and strings
- Classes, inheritance, interfaces, and concepts
- A "constraint" system for more thorough compile-time checking
- Array additions, maps, etc., efficiently translating to C
