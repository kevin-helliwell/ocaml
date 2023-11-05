# Pattern matching
- Match shape of data
- Extract part(s) of data
# Pattern matching with lists
- A list can only be:
  - nil, or
  - the cons of an element onto another list
- Use **pattern matching** to access list in one of those ways:
```ocaml
(* matching.ml *)

let empty lst =
match lst with
| [] -> true
| _ -> false (* or h :: t -> false*)

let rec sum lst =
match lst with
| [] -> 0
| h :: t -> h + sum t

let rec length lst =
match lst with
| [] -> 0
| h :: t -> 1 + length t

(* example usage:
| append [1;2;3] [4;5;6] is [1;2;3;4;5;6] 
*)
let rec append lst1 lst2 =
match lst1 with
| [] -> lst2
| h :: t -> h :: append t lst2

(* matching.ml *)

(* utop *)

#use "matching.ml";;
=> val empty : 'a list -> bool = <fun>
=> val sum : int list -> int = <fun>
=> val length : 'a list -> int = <fun>
=> val append : 'a list -> 'a list -> 'a list = <fun>

sum [];;
=> - : int = 0

sum [1;2;3];;
=> - : int = 6

#trace sum;;
=> "sum is now traced."

sum [1;2;3];;
=> sum <-- [1;2;3];;
=> sum <-- [1; 2; 3]
=> sum <-- [2; 3]
=> sum <-- [3]
=> sum <-- []
=> sum --> 0
=> sum --> 3
=> sum --> 5
=> sum --> 6
=> - : int = 6

#untrace sum;;
=> "sum is no longer traced."

length [];;
=> - : int = 0

length [1;2;3];;
=> - : int = 3

append [1;2;3] [4;5;6];;
=> - : int list = [1;2;3;4;5;6]

[1;2;3] @ [4;5;6];;
=> - : int list = [1;2;3;4;5;6]
(* built-in append method *)

(* utop *)
```
-----------------------------------------
