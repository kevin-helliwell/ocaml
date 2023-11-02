# **What is a functional language?**
## A functional language:
- Defines computations as *mathematical functions*
- Avoids mutable *state*
-----------------------------------------
## State:
- The information maintained by a computation
### LinkedList class in Java
- Tracks how many elements contained within
- Tracks which nodes are at beginning and end
### Djikstra's Algorithm
- Tracks frontier set for shortest path computation
-----------------------------------------
## Mutable:
- Can be changed (antonym: *immutable*)
-----------------------------------------
# Mutability

## The fantasy of mutability:
- It's easy to reason about: the machine does this, then this...
-----------------------------------------
## The reality of mutability:
- Machines are good at complicated manipulation of state
- Humans are not good at understanding it!
- Mutability breaks *referential transparency:* ability to replace expression with its value without affecting result of computation
-----------------------------------------
# Imperative programming

## Commands specify *how to compute* by destructively changing state:
- `x = x + 1;`
- `a[i] = 42;`
- `p.next = p.next.next;`
## Functions/methods have *side effects*:
```
int x = 0;
int incr_x() {
x++;
return x;
}
```
-----------------------------------------
# Functional programming
## Expressions specify *what to compute*:
- Variables never change value
- Functions never have side effects
## The reality of immutability:
- No need to think about state
- Powerful ways to build correct programs
-----------------------------------------
