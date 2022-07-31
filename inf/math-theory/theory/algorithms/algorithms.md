# algorithms

⟮An algorithm⟯ is a ⟮finite⟯ ⟮sequence⟯ (in the math sense) of ⟮steps⟯ that ⟮precisely defines an operation⟯. 

## pseudocode

⟮pseudocode⟯ is ⟮a plain-language description⟯ of ⟮an algorithm⟯. 
⟮Pseudocode⟯ generally ⟮uses (structural) conventions of⟯ ⟮programming languages⟯, but not ⟮specific syntax⟯. 

```lang=text;
When a button is pressed:
  Get some memory, which will be used to remember the floor number
  Put the floor number into the memory
  Are we already on the target floor?
    If so, we have nothing to do: finished
    Otherwise:
      Wait until the lift is idle
      Go to the required floor
      Release the memory we used to remember the floor number
```

## properties

### determinism

a deterministic algorithim/callable unit will, given a particular input ⟮always produce the same output⟯

## complexity

Computational complexity is the amount of resources necessary to run an algorithm.
Computational complexity assumes the amount of resources to perform each operation are similar / average out.
there are two types of computational complexity commonly used, depending on the case: worst-case and average-case.
In general, if we only say 'complexity', worst case complexity is assumed.
there are two types of computational complexity commonly used, depending on the resource: time and space
Computational complexity is generally specified in Big O notation.
Computational complexity is generally specified as a function of the input size n.
Computational complexity/Big O notation only indicates orders of magnitude.

O(1)   constant complexity/time|Accessing an element in an array
O(n)   linear complexity/time|Iteratering over a one-dimensional array
O(log n)   logarithmic time
O(n⎴2⎴)   quadratic time

## static program analysis

static program analysis is reasoning about/analyzing the behavior of computer programs without actually running them
Linting is probably the most common form of static program analysis.