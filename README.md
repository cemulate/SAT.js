SAT.js
======

A simple JavaScript SAT solver, see (http://www.comp.nus.edu.sg/~gregory/sat/) for a live demo & more information.

Usage
======

```javascript
import solveSat from 'boolean-sat';

// Solve a SAT problem with two variables.
// They will be numbered 1 and 2.
let numVars = 2;

// The SAT problem is given in conjuctive normal form.
// That is, an AND of ORs.

// The following input corresponds to the statement:
let clauses = [
    [1, 2],       //     (    1    OR    2    )
    [-1, 2],      // AND ( (NOT 1) OR    2    )
    [-1, -2]      // AND ( (NOT 1) OR (NOT 2) )
];

let solution = solveSat(numVars, clauses);

// Solution is false if the statement is not satisfiable.
if (solution) {
    // Otherwise, it contains (an) assignment of the variables that makes the statement true
    console.log(solution[1]); // false
    console.log(solution[2]); // true
    // Because 1=false, 2=true is the only assignment that satisifes the given statement
}
```
