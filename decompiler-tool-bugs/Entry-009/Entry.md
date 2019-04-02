# Entry-009
Inserts a try-catch block which catches everything. It will always delegate the
control flow into a specific region of code.

## Procyon
Procyon does not recognize the non-javac-like use of a null catch type (used to
implement the finally keyword). This results in inaccurate code due to the
exception not being handled correctly.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 7  
Total score: 0.67  

#### Patch Date
N/A

## FernFlower
FernFlower does not recognize the non-javac-like use of a null catch type (used to
implement the finally keyword). This results in inaccurate code due to the
exception not being handled correctly.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 7  
Total score: 0.67  

#### Patch Date
N/A

## JD-GUI
JD-GUI does not recognize the non-javac-like use of a null catch type (used to
implement the finally keyword). This results in completely wrong code which is
in no way semantically equivalent.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 9  
Total score: 0.73  

#### Patch Date
N/A
