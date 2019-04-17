# Entry-004
Integers are split into XOR operations and is manipulated on the stack using `swap`, `dup_x1` and
`pop2`.

```
L86:    ldc -893664644 ; Stack = [-893664644]
L88:    ldc 2030482428 ; Stack = [2030482428, -893664644]
L90:    swap           ; Stack = [-893664644, 2030482428]
L91:    dup_x1         ; Stack = [-893664644, 2030482428, -893664644]
L92:    pop2           ; Stack = [-893664644]
L93:    ldc -893664644 ; Stack = [-893664644, -893664644]
L95:    ixor           ; Stack = [0]
```

## FernFlower
FernFlower is unable to parse the stack correctly and displays an incorrect bitwise evaluation
and/or tries to invoke on integers for some weird reason on larger samples.

#### Scoring
Consistency: 10  
Practicality: 7  
Decompiler Inaccuracy: 6  
Total score: 0.77  

#### Patch Date
Unknown

## JD-GUI
JD-GUI is unable to parse the stack correctly and displays a significant amount of confusing
and illegal code on larger samples.

#### Scoring
Consistency: 10  
Practicality: 8  
Decompiler Inaccuracy: 8  
Total score: 0.87  

#### Patch Date
N/A