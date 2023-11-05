```ocaml
(* matching.ml *)

let bad_empty lst =
match lst with
| [] -> true
(* | _ -> false *)(* missing branch *)

let rec bad_sum lst =
match lst with
| h :: t -> h + bad_sum t
(* | [x] -> x *) (* this match case is unused*)
| [] -> 0

let rec bad_sum' lst =
List.hd lst + bad_sum' (List.tl lst)

(* matching.ml *)

(* utop *)

#use "matching.ml";;
=> "2 | ..match lst with
3 | | -> true"
=> "Warning 8: this pattern-matching is not exhaustive.
Here is an example of a case that is not matched:
_::_"
=> "10 | | x :: [] -> x
Warning 11: this match case is unused."

=> val bad_empty : 'a list -> bool = <fun>

=> val bad_sum : int list -> int <fun>

=> val bad_sum' : int list -> int = <fun>

bad_empty [];;
=> - : bool = true

bad_empty [1];;
=> "Exception: Match_failure ("matching.ml", 2, 2)."

bad_sum [];;
=> - : int = 0

bad_sum [1;2;3];;
=> - : int = 6

bad_sum'[1;2;3];;
=> "Exception: Failure 'tl'".

(* utop *)
```
# Compiler checks for your errors
- Static semantics is more than just type checking
- OCaml compiler checks for
  - Exhaustiveness of patterns
  - Unused branches
- **Do not ignore these warnings**; the compiler is finding your errors and giving you a chance to fix them!
------------------------
