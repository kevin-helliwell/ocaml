```ocaml
[ ];;
=> - : 'a list = []

[];;
=> - : 'a list = []

[1];;
=> - : int list = [1]

[1; 2];;
=> - : int list = [1; 2]

[1; 2; 3]
=> - : int list = [1; 2; 3]

[1.; 2.; 3.];;
=> - : float list = [1.; 2.; 3.]

[true; false];;
=> - : bool list = [true; false]

[[1;2]; [3;4]; [5;6]];;
=> - : int list list = [[1; 2]; [3; 4]; [5; 6]]

1 :: [2;3];;
=> - : int list = [1; 2; 3]

1 :: 2 :: 3 :: [];;
=> - : int list = [1; 2; 3]
```
# OCaml lists
- Immutable: can't change elements
- Singly-linked:
  - Good for sequential access of short-to-medium length lists (say, up to 10k elements)
  - Data structures are tools: none is perfect
  - Next week we'll study the implementation
-----------------------------------------
