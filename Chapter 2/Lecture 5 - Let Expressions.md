# Example 1
```ocaml
let a = 0 in a;;
=> - : int = 0
```
# Example 2
```ocaml
let b = 1 in 2 * b;;
=> - : int = 2
```
# Example 3
```ocaml
a;;
=> "Error: Unbound value a"

b;;
=> "Error: Unbound value b"
```
# Example 4
```ocaml
let c = 3 in (let d = 4 in c + d);;
=> - : int = 7
```
# Example 5
```ocaml
let e = 5 in (let e = 6 in e);;
=> "Warning 26: unused variable e."
=> = : int = 6
```
-----------------------------------------
