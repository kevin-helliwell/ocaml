# Examples
## Example 1
```ocaml
(fun x -> x + 1);;
=> - : int -> int = <fun>
```
## Example 2
```ocaml
(fun x -> x + 1) 3110;;
=> - : int = 3111
```
## Example 3
```ocaml
(fun x y -> (x +.y) /. 2.);;
=> - : float -> float -> float = <fun>
```
## Example 4
```ocaml
(fun x y -> (x +. y) /. 2.0) 2110. 3111.;;
=> - : float = 2610.5
```
-----------------------------------------
