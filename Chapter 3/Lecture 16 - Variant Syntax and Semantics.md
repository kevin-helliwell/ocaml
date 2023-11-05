# Variant types
## Type definition syntax
```ocaml
type t =
| C1 of t1 
(* t1 optional data carried by constructor C1 *)
| ...
| Cn of tn 
(* Cn constructors aka tags; must be capitalized *)
```
# Non-constant variant expressions
## Syntax: `C e`
## Evaluation
- `if e ==> v then C e ==> C v`
## Type checking
- `C e : t`
- `if t = ... | C of t' | ...`
- `and e : t'`
## Pattern matching
- `C p` is a pattern
# Constant variant expressions
## Syntax 
- `C`
## Evaluation
- Already a value
## Type checking
- `C : t`
- `if t = ... | C | ...`
## Pattern matching
- `C` is a pattern
------------------------
