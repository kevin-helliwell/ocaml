# :: vs @
- ::
  - "cons"
  - Add an element onto the head of a list
  - `'a -> 'a list -> 'a list`
  - Constant time: O(1)
- @
  - "append"
  - Combine two lists
  - `'a list -> 'a list -> 'a list`
  - Linear time in first list: for `lst1 @ lst2`, it's O(length `lst1`)
```ocaml
let rec length = function
| [] -> 0
| h :: t -> 1 + length t
(* implements cons *)

let rec append lst1 lst2 =
match lst1 with
| [] -> lst2
| h :: t -> h :: append t lst2
(* implements append *)
```
------------------------

