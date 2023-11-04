# Example 1
```ocaml
let x = 42;;
=> val x : int = 42
```
## Example 2
```ocaml
x;;
=> - : int = 42
```
## Example 3
```ocaml
let (y : int) = 3110;;
=> val y : int = 3110
```
## Example 4
```ocaml
let y : int = 3110;;
=> val y : int = 3110
```
## Example 5
```ocaml
x + y;;
=> - int = 3152
```
-----------------------------------------
# Definitions
- A *definition* gives a name to a value
- Definitions are not expressions, or vice-versa
- But definitions syntactically contain expressions
-----------------------------------------
# let definitions
## Syntax
- Let `x = e` where `x` is an *identifier*
## Evaluation
- Evaluate `e` to a value `v`
- Bind `v` to `x`: henceforth, `x` will evaluate to `v`
- Under the hood: there is a memory location named `x` that contains `v`
- The let definition is not an expression itself
## Example
```ocaml
(let z = 1) + 2;;
=> "Error: Syntax error: operator expected."
```
-----------------------------------------
