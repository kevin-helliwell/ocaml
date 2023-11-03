## Example 1
```ocaml
if then else
if "batman" > "superman" then "yay" else "boo";; 
-> - : string = "boo"
```
- Strings in OCaml are ordered *lexicographically*
- Z > Y > ... > A
## Example 2
```ocaml
if 0 then "yay" else "boo";; 
-> "Error: This expression has type int but an expression was expected of bool because it is in the condition of an if-statement"
```
- An int cannot be treated as a bool
- Strict type checking (no type coercion)
## Example 3
```ocaml
if true then "yay" else 1;;
-> "Error: This expression has type int but an expression was expected of type string"
```
- Then and else branches must be the same type
## Example 4
```ocaml
if true then "yay";;
-> "Error: This expression has type string but an expression was expected of type unit because it is in the result of a conditional with no else branch"
```
- Avoid leaving out the else branch
-----------------------------------------
# if expressions
## Syntax 
- if e1 then e2 else e3
## Evaluation
- if `e1` evaluates to `true`, and if `e2` evaluates to `v`, then `if e1 then e2 else e3` evaluates to `v`
- if `e1` evaluates to `false`, and if `e3` evaluates to `v`, then `if e1 then e2 else e3` evaluates to `v`
## Type checking
- if `e1` has type `bool` and `e2` has type `t` and `e3` has type `t`, then `if e1 then e2 else e3` has type `t`
## Note
- Write ==> to indicate evaluation
- Pronounce as "evaluates to"
- Write colon (:) to indicate type of expression
- Pronounce colon as "has type"
## Evaluation (New Notation)
- if `e1 ==> true` and `e2 ==> v`, then `(if e1 then e2 else e3) ==> v`
- if `e1 ==> false` and `e3 ==> v`, then `(if e1 then e2 else e3) ==> v`
## Type checking (New Notation)
- if `e1 : bool` and `e2 : t` and `e3 : t`, then `(if e1 then e2 else e3) : t`
-----------------------------------------

