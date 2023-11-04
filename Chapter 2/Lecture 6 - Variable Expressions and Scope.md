# Let definitions in toplevel
- `let x = e` is implicitly, **`in`** *rest of what you type*"
## E.g., you type:
- `let a = "big";;`
- `let b = "red";;`
- `let c = a ^ b;;`
## Toplevel understands as
- `let a = "big" in`
- `let b = "red" in`
- `let c = a ^ b in...`
-----------------------------------------
# Variable expressions
- How to evaluate just **`x`** at the toplevel?
- Answer: substitution from that giant nested **`let`** expression
-----------------------------------------
# Scope
- The **scope** of a variable is where its name is meaningful
## Example
```ocaml
let x = 42 in
(* y is not meaningful here*)
x + (let y = "3110" in
(* y is meaningful here*)
int_of_string y)
```
-----------------------------------------
# Overlapping scope
- What does this mean?
## Example
```ocaml
let x = 5 in
((let x = 6 in x) + x)
```
- *It's darn confusing because of the overlapping scope; we should avoid that in our own programs.*
-----------------------------------------
# Names
- **Principle of Name Irrelevance**: the name of a variable shouldn't intrinsically matter
## E.g., in math, these are the same functions
- f(x) = x + 1
- f(y) = y + 1
## Name irrelevance and substitution
- To ensure name irrelevance in programs, **stop substituting when you reach a binding of the same name**
- *Much later in semester, we will implement a careful definition of substitution inside interpreter. For now, this is good enough.*
# Examples
## Example 1
```ocaml
let x = 5 in (let x = 6 in x);;
-> "Warning 26: unused variable x."
-> - : int = 6
```
- `let x = 6 in x` is evaluated first, so `let x = 5 in` is rendered obsolete/redundant.
## Example 2
```ocaml
let x = 5 in x + (let x = 6 in x);;
-> - : int = 11
```
- `let x = 6 in x` -> `6`
-  `let x = 5 in x + 6` -> `11`
-----------------------------------------
