# Use a record or variant?
- A *coin*, which can be a penny, nickel, dime, or quarter (variant)
- A *student*, who has a name and id number (record)
- A *dessert*, which has a sauce, a creamy component, and a crunchy component (record)
- Conjunction "or" implies a variant
- Conjunction "and" implies a record
# One-of vs. Each-of
- Records and tuples: *each-of* types
  - Aka *product* types
  - Familiar? Like a Cartesian product (Ex. string x int)
- Variants: *one-of* types
  - Aka *sum* types
  - Maybe less familiar?
# Variant aka *tagged union*
```ocaml
type string_or_int =
| String of string
| Int of int
```
- Ex. string U int
- Variants get us heterogenous lists:
  - `[string_or_int list]` is a list whose values are either `[string]` or `[int]`
```ocaml
type blue_or_pink_int =
| Blue of int
| Pink of int
```
# Algebraic data type
- Sums and product: algebra
- Hence variants known as *algebraic data types*
- ADT also stands for abstract data type
------------------------------------------------------
