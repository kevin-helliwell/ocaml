# Function application
- Syntax: `e0 e1 ... en`
- No parentheses required! (unless you need to force particular order of evaluation)
## Evaluation of `e0 e1 ... en`
1. Evaluate subexpressions:
   `e0 ==> v0, ..., en ==> vn`
   `v0` must be a function:
   `fun x1 ... xn -> e`
2. Substitute `vi` for `xi` in `e` yielding new expression `e'`. Evaluate it: `e' ==> v`
3. Result is `v`
-----------------------------------------
# Examples
## Example 1
```ocaml
(fun x -> x + 1) (2 + 3)
(fun x -> x + 1) 5
5 + 1
6
```
## Example 2
```ocaml
(fun x y -> x - y) (3 * 1) (3 - 1)
(fun x y -> x - y) 3 2
3 - 2
1
```
-----------------------------------------
