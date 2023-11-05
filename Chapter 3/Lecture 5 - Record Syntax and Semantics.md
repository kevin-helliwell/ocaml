# Records and tuples
- New kind of definition: type definition
- New kinds of types: record types, tuple types
# Record syntax
- `{f1 = e1; f2 = e2}` is a record with fields named `f1` and `f2`
  - Order of fields is irrelevant
  - Any number of fields permitted from 1 up to about 4 million
- `e.f` accesses field `f` of a record expression `e`
- Field names are identifiers not expressions
# Record semantics
## Evaluation
- If `ei ==> vi` then
  - `{f1 = e1; ...; fn = en} ==>`
    - `{f1 = v1; ...; fn = vn}`
- If `e ==> {...; f = v; ...}` then
  - `e.f ==> v`
## Type checking
- Record types must be defined before use so that OCaml knows the field names
- If `ei : ti` and if `t` is defined to be `{f1 : t1, ..., fn : tn}`, then
  - `{f1 = e1; ...; fn = en} : t`
- If `e : t` and if `t` is defined to be `{...; f: tf; ...}`, then
  - `e.f : tf`
# Record Copy
- `{e with f1 = e1}` creates a *copy* of record `e` with new field value for `f1`
  - **This is not mutation**: original record unchanged
  - Can have multiple new field values:
    - `{e with f1 = e1; f2 = e2; f3 = e3}` etc.
  - Sugar for
    - `{f1 = e1; ...; fn = en}`
    - `{g1 = e.g1; ...; gm = e.gm}` where `gi` are the fields of `e` that are not named in the copy
  - Cannot "add" new fields: type cannot change
# Examples
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

(* records.ml *)

(* utop *)

#use "records.ml";;
=> type student = { name: string; year: int;}
=> val rbg : student = {name = "Ruth Bader"; year = 1954}

rbg;;
=> - : student = {name = "Ruth Bader"; year = 1954}

{rbg with name = "Ruth Bader Ginsburg"};;
=> - : student = {name = "Ruth Bader Ginsberg"; year = 1954}

(* utop *)
```
-----------------------------------------
