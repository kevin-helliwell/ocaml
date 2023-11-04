# Application operators
## Application
- `let (@@) f x = f x`
## Reverse application (pipeline)
- `let (|>) x f = f x`
### Example
```ocaml
(*succ (successor) is ocaml's built-in version of the increment function (x -> x + 1)*)

succ;;
=> - : int -> int = <fun>

succ 1;;
=> - : int = 2

succ 2 * 10 = (succ 2) * 10;;
=> - : int = 30

succ (2 * 10);;
=> - : int = 21

(*using application operator @@*)
succ @@ 2 * 10;;
=> - : int = 21

let square x = x * x;
=> val square : int -> int = <fun>

square (succ 5);;
=> - : int = 36

(square succ) 5;;
=> "Error: This expression has type int -> int but an expression was expected of type int"

succ(square (square (succ 5)));;
=> - : int = 1297

5 |> succ |> square |> square |> succ;;
=> - : int = 1297
(*same answer using reverse application (pipeline) operator*)
```
-----------------------------------------
