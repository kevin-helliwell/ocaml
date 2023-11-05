```ocaml
(* variants.ml *)

type primary_color = Red | Green | Blue

(* let r : primary_color = Red *)
let r = Red

type point = float * float

type shape =
| Circle of {center : point; radius : float}
| Rectangle of {lower_left : point; upper_right : point}

let c1 = Circle {center = (0.,0.); radius = 1.}

let r1 = Rectangle {lower_left = (-1., -1.); upper_right = (1.,1.)}

let avg a b =
(a +. b) /. 2.

let center s =
match s with
| Circle {center; radius} -> center
| Rectangle {lower_left; upper_right} ->
let (x_ll, y_ll) = lower_left in
let (x_ur, y_ur) = upper_right in
(avg x_ll x_ur, y_ll y_ur)

(* variants.ml *)

(* utop *)

#use "variants.ml";;
=> type primary_color = Red | Green | Blue
=> var r : primary_color = Red
type point = float * float
type shape = Circle of { center: point; radius : float; } | Rectangle of { lower_left : point; upper_right : point; }
=> val c1 : shape = Circle {center = (0., 0.); radius = 1.}
=> val r1 : shape = Rectangle {lower_left = (-1., -1.); upper_right = (1., 1.)}
=> val avg : float -> float -> float = <fun>
=> val center : shape -> point = <fun>

center c1;;
=> - : point = (0., 0.)

center r1;;
=> - : point = (0., 0.)

(* utop *)
```
------------------------------------------------------
