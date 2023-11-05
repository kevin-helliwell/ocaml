# Function keyword
- Immediately matching against implicit final argument is so useful there's syntactic sugar for it
```ocaml
let f x y z =
match z with
| p1 -> e1
| p2 -> e2

(* The above Can be written as follows: *)

let f x y = function
| p1 -> e1
| p2 -> e2

(* syntactic sugar method using function keyword *)

let empty = function
| [] -> true
| _ -> false

let rec sum = function
| [] -> 0
| h :: t -> h + sum t

let rec length = function
| [] -> 0
| h :: t -> 1 + length t
```
------------------------
