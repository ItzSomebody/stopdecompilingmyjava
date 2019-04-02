# Entry-008
Splits a block of code into two reordered sub blocks and wraps the first block
in a fake trap.

## CFR
CFR decompiles the method but merges the second block into the try block
with the first block resulting in behavior change.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 7  
Total score: 0.67  

#### Patch Date
N/A

## JD-GUI
JD-GUI decompiles the method completely wrong. The result is a behavior change and unreachable code.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 9  
Total score: 0.73  

#### Patch Date
N/A