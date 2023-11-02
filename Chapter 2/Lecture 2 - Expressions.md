# Expressions
- Primary building block of OCaml programs
- Akin to statements or commands in imperative languages
## Every kind of expression has
### Syntax
### Semantics
- **Type-checking rules** (*static semantics*): produce a type, or fail with an error message
- **Evaluation rules** (*dynamic semantics*): produce a *value*, or exception or infinite loop
-----------------------------------------
# Values
- A **value** is an expression that does not need any further evaluation (it's "done")
- All values are expressions, but not all expressions are values
- `3110;;` -> `- : int = 3110`
- `false;;` -> `- : bool = false`
-  `3110 > 2110;;` -> `- : bool = true`
-  `"big";;` -> `- : string = "big"`
-  `"big" ^ "red";;` -> `- : string = "bigred"`
-  `2.0 * 3.14;;*` -> `Error: This expression has type float but an expression was expected of type int`
- `2.0 *. 3.14;;` -> `- : float = 6.28`
-----------------------------------------
# Type inference and annotation
##  OCaml compiler infers types
- Compilation fails with type error if it can't
- Hard part of language design: guaranteeing compiler can infer types when program is correctly written
## You can manually annotate types anywhere
- Replace `e` with `(e : t)`
- Useful for diagnosing type errors
- `(3110 : int);;` -> `- : int - 3110`
- `(3110 : bool);;` -> `Error: This expression has type int but an expression was expected to be bool`
-----------------------------------------
