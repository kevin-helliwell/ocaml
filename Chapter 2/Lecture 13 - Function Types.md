# Function types
- Type `t -> u` is the type of a function that takes input of type `t` and returns output of type `u`
- Type `t1 -> t2 -> u` is the type of a function that takes input of type `t1` and another input of type `t2` and returns output of type `u`
## Note dual purpose for -> syntax
- Function types
- Function values
# Anonymous function expression
- Type checking
  ```ocaml
  if x1 : t1, ..., xn : tn
  and e : u
  then (fun x1 ... xn -> e) :
  t1 -> ... -> tn -> u
```
- Examples
```ocaml
fun (x : int) -> x + 1
x + 1 : int
(fun x -> x + 1) : int -> int

fun x y -> x + y
x : int
y : int
x + y : int
(fun x y -> x + y) : int -> int -> int
```
# Function application
- Type checking
```ocaml
if e0 : t1 -> ... -> tn -> u
and e1 : t1, ..., en : tn
then e0 e1 ... en : u
```
-----------------------------------------
