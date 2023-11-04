```ocaml
let add x y = x + y;;
=> val add : int -> int -> int = <fun>
add 2 3;; (*2 + 3 -> 5*)
=> - : int = 5
add 2;; (*returns a function y -> 2 + y, partial application of x y -> x + y**)
=> - : int -> int = <fun>
(add 2) 3;; (*3 -> 2 + 3 -> 5*)
=> - : int 5
```
# More syntactic sugar
## Multi-argument functions do not exist
- `fun x y -> e` is syntactic sugar for `fun x -> (fun y -> e)
- `let add x y = x + y` is syntactic sugar for `let add = fun x -> fun y -> x + y`
- `fun x y z -> e` is syntactic sugar for `fun x -> (fun y -> (fun z -> e))`
# Again: Functions are values
## Can use them *anywhere* we use values
- Functions can **take** functions as arguments
- Functions can **return** functions as results
- This is an incredibly powerful language feature!
-----------------------------------------

