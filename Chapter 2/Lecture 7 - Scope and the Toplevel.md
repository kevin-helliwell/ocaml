```ocaml
let x = 1;;
=> val x : int = 1

let x = 2;;
=> val x : int = 2

x;;
=> - : int = 2
```
# Seems like variable can mutate...
```ocaml
let x = 1;;
let x = 2;;
x;;
```
# But really it's just nested scopes
```ocaml
let x = 1 in
let x = 2 in
x
```
- `let x = 1` allocates memory that will always be 1
- `let x = 2` allocates memory that will always be 2
- `x` refers to the piece of memory in the **innermost scope**, as you would expect.
-----------------------------------------
