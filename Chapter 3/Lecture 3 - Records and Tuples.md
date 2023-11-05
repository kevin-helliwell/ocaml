# Records
```ocaml
(* records.ml*)

type student = {
name : string;
year : int; (* grad year *)
}

let rbg = {
name = "Ruth Bader";
year = 1954;
}

(* records.ml *)

(* utop *)

#use "records.ml";;
=> type student = { name: string; year : int; }
=> val rbg : student = {name = "Ruth Bader"; year = 1953}

rbg.name;;
=> - : string = "Ruth Bader"

(* utop *)
```
# Tuples
```ocaml
(* tuples.ml *)

type time = int * int * string

(* let t = (10, 10, "am") *) 
(* syntactic sugar representation with type inferred *)

let t : time = (10, 10, "am")
(* equivalent to syntactic sugar representation; type is explicitly stated rather than inferred *)

type point = float * float

(*let p = (5., 3.5)*)
(* syntactic sugar representation with type inferred *)

let p : point = (5., 3.5)
(* equivalent to syntactic sugar representation; type is explicitly stated rather than inferred *)

(* tuples.ml *)

(* utop *)

#use "tuples.ml";;
=> type time = int * int * string
=> val t : time = (10, 10, "am")
=> type point = float * float
=> val p : point = (5., 3.5)

p;;
=> - : point = (5., 3.5)

fst;;
=> - : 'a * 'b -> 'a = <fun>
(* built-in function that returns first element in tuple of two elements *)

fst p;;
=> - : float = 5.

snd;;
=> - : 'a * 'b -> 'b = <fun>
(* built-in function that returns second element in tuple of two elements *)

snd p;;
=> - : float = 3.5

fst t;;
=> "Error: This expression has type time = int * int * string but an expression was expected of type a' * 'b"
(* fst and snd functions only work on tuples with two elements*)

(* utop *)
```