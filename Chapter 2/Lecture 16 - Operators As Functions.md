```ocaml
1 + 2;;
=> - : int = 3

( + ) 1 2;;
=> - : int = 3

( * ) 1 2;;
=> - : int = 2

( = );;
=> - : 'a -> 'a -> bool = <fun> 
(*polymorphic: input types can vary type as long as they are consistently the same type*)

( = ) 1 2;;
=> - : bool = false

( = ) 1 false;;
=> "Error: This expression has type bool but an expression was expected of type int"

( < );;
=> - : 'a -> 'a -> bool = <fun>
(*polymorphic*)

max;;
=> - : 'a -> 'a -> 'a = <fun>

max 1 2;;
=> - : int = 2

let ( <^> ) x y = max x y;;
=> val ( <^> ) : 'a -> 'a -> 'a = <fun>
(*custom infix binary operator: <^> x y is defined as max x y*)

1 <^> 2;;
=> - : int = 2
```
-----------------------------------------
