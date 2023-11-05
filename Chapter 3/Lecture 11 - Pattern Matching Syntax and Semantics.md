# Pattern matching
## Syntax
```ocaml
match e with
| p1 -> e1
| p2 -> e2
```
## Can have more branches, or even just one

## `p` is a new syntactic class
- Pattern expressions
# Match expressions
```ocaml
match e with
| p1 -> e1
| p2 -> e2
| ...
| pn -> en
```
## Evaluation
- if `e ==> v`
  - And `pi` is the first pattern, top-to-bottom, that matches `v`
  - And `ei ==> vi`
  - Then `(match e ...) ==> vi`
- But if no patterns match, raise an exception `Match_failure`
## Type checking
- If `e` and `pi` have type `ta`
- And `ei` have type `tb`
  - Then entire match expression has type `tb`
# Basic pattern syntax
- `x` i.e., any identifier
- `_` i.e., underscore
- any constant
# Semantics of pattern matching
- A constant matches itself
- An identifier aka *pattern variable* matches anything and *binds* it in the scope of the branch
- The underscore aka *wildcard* matches anything but doesn't bind it
# Data type patterns
- `[]`
- `p1 :: p2` etc.
- `[p1; p2]` etc.
- `(p1, p2)` etc.
- `{f1 = p1; f2 = p2}` etc.
## All of which match the corresponding data type values, and can bind parts of them
------------------------
