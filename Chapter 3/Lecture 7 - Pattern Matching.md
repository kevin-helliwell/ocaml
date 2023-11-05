# Examples
## Example 1
```ocaml
(* matching.ml *)

let x = 
match not true with
| true -> "nope" 
| false -> "yep";;

let y =
match 42 with
| fooo -> fooo

let z =
match "foo" with
| "bar" -> 0
| _ -> 1

let a = match [1;2] with
| [] -> "empty"
| _ -> "not empty"

let b = match ["taylor";"swift"] with
| [] -> ["folklore"]
| h :: t -> t

let fst3 t =
match t with
| (a, b, c) -> a;;

(* matching.ml *)

(* utop *)

#use "matching.ml";;
=> val x : string = "yep"
=> val y : int = 42
=> val z : int = 1
=> val a : string = "not empty"
=> val b : string list = ["swift"]
=> val fst3 : 'a * 'b * 'c -> 'a = <fun>

fst (1,2,3);;
=> "Error: This expression has type 'a * 'b * 'c but an expression was expected of type 'd * 'e"
(* Only works with pairs *)

fst3 (1,2,3);;
=> - : int = 1

fst;;
=> - : 'a * 'b -> 'a = <fun>

fst (1,2);;
=> - : int = 1

(* utop *)
```
## Example 2
```ocaml
(* records.ml *)

type student = {
name : string;
year : int; (* grad year *)
}

let rbg = {
name = "Ruth Bader";
year = 1954;
}

let name_with_ear s =
match s with
| {name; year} -> name ^ " '" ^ string_of_int (year mod 100)

(* records.ml *)

(* utop *)

#use "records.ml";;
=> type student = { name : string; year : int; }
=> val rbg : student = {name = "Ruth Bader"; year = 1954}
=> val name_with_year : student -> string = <fun>

name_with_year rbg;;
=> - : string = "Ruth Bader '54"

(* utop *)
```
-----------------------------------------
