# Pokemon
```ocaml
(* mons.ml*)

type ptype = TNormal | TFire | TWater (* variant*)

type peff = ENormal | ENotVeryEffective | ESuper (* variant *)

let mult_of_eff = function
| ENormal -> 1.
| ENotVeryEffective -> 0.5
| ESuper -> 2.0

(* let eff = function
| (TFire, TFire) | (TWater, TWater) | (TFire, TWater) -> ENotVery
| (TWater, TFire) -> ESuper
| _ -> ENormal *)
let eff t1 t2 = match t1, t2 with
| TFire, TFire | TWater, TWater | TFire, TWater 
-> ENotVery
| TWater, TFire -> ESuper
| _ -> ENormal

type mon = {
name : string;
hp : int;
ptype: ptype;
}

let charmander = {
name = "Charmander";
hp = 39;
ptype = TFire;
}

(* mons.ml*)

(* utop *)

eff (TFire, TFire);; (* with commented out eff function *)
=> - : peff = ENotVery

eff TFire TFire;; (* with commented out eff function *)
=> "Error: This function has type ptype * ptype -> peff
It is applied to too many arguments; maybe you forgot an ';'."

eff TFire TFire;; (* with second eff function *)
=> - : peff = ENotVery

eff (TFire, TFire);; (* with second eff function *)
=> "Error: This expression has type 'a * 'b
but an expression was expected of type ptype"

(* utop *)
```
-------------------------------------------------------------
