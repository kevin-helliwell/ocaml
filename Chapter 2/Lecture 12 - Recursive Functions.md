# Recursive function definition
- Must explicitly state that function is recursive:
  `let rec f ...`
## Example - Factorial function
```ocaml
(* requires [n >= 0] *)
let rec fact n =
if n = 0 then 1
else n * fact (n - 1);;

fact 10;;
=> - : int = 3628800
```
-----------------------------------------
