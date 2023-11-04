```ocaml
let x = 3110;;
=> val x : int = 3110

fun x -> x + 1;;
=> - : int -> int = <fun>

let inc = fun x -> x + 1;;
=> val inc : int -> int = <fun>

inc 3110;;
=> - : int = 3111

let inc x = x + 1;;
=> val inc : int -> int = <fun>

inc 3110;;
=> - : int = 3111

let avg x y = (x +. y) /. 2.;;
=> val avg : float -> float -> float = <fun>

avg 0. 1.;;
=> - : float = 0.5

let avg = fun x y -> (x +. y) /. 2.;;
=> val avg : float -> float -> float = <fun>
```
-----------------------------------------
# Two syntaxes (definitions)
## Syntactically different but *semantically equivalent*
### Example 1
```ocaml
let inc = fun x -> x + 1;;
let inc x = x + 1;;
```
### Example 2
```ocaml
(fun x -> x + 1) 2;;
let x = 2 in x + 1;;
```
## Latter is *syntactic sugar*
- Not necessary
- Makes language "sweeter"
### Another example
```ocaml
let f = fun x y -> x - y in f 3 2;;
=> (fun x y -> x - y) 3 2;;
=> 3 - 2;;
=> 1

let f x y = x - y;;
=> val f : int -> int -> int <fun>
f 3 2;;
=> - : int = 1
```
-----------------------------------------
