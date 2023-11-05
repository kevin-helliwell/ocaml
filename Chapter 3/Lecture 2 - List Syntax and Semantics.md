# List syntax
## Syntax
- `[]` is the empty list
- `e1 :: e2` prepends element `e1` to list `e2`
- `[e1; e2]` is sugar for `e1 :: e2 :: []`
- And similarly for longer lists `[e1; e2; e3]` etc.
## From Lisp
- `[]` is pronounced "nil"
- `::` is pronounced "cons" (short for "construct")
# List semantics
## Evaluation
- `[]` is a value
- To evaluate `e1 :: e2`,
  - evaluate `e1` to a value `v1`,
    - evaluate `e2` to a (list) value `v2`, and
      - return `v1 :: v2`
## Consequence of the above rules
- To evaluate `[e1; e2]`, 
  - evaluate `e1` to a value `v1`, 
    - evaluate `e2` to a value `v2`, and 
      - return `[v1; v2]`
# List types
- For any type `t`, the type `t list` describes lists where all elements have type `t`
  - `[1; 2; 3] : int list`
  - `[true] : bool list`
  - `[[1 + 1; 2 - 3]; [3 * 7]] : int list list`
# List semantics (cont.)
## Nil
- `[] : 'a list`
- i.e., empty list has type `t list` for any type `t`
## Cons
- if `e1 : t` and `e2 : t list`
  - then `e1 :: e2 : t list`
## *With parens for clarity*
- If `e1 : t` and `e2 : (t list)`
  - then `(e1 :: e2) : (t list)`
-----------------------------------------
