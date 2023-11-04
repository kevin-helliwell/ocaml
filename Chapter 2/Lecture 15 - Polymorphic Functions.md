```ocaml
let id x = x;;
=> val id : 'a -> 'a = <fun>

id 5;;
=> - : int = 5

id "hello";;
=> - : string = "hello"

id true;;
=> - : bool = true
```
# Type variables
- **Variable**: name standing for unknown value
- **Type variable**: name standing for unknown type
- Java example: `List<T>`
- OCaml Syntax: single quote followed by identifier
  e.g., `'foo`, `'key`, `'value`
- But most often simply just: `'a`
- Pronounced "alpha"
# Polymorphism
- Meaning: *poly* = many, *morph* = form
- Write function that works for many arguments regardless of their type
- Closely related to Java generics
- Also related to C++ template instantiation
- Parametric polymorphism
-----------------------------------------
