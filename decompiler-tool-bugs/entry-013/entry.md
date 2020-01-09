# entry-013
Traps a getstatic instruction and lets the fetched value fall-through into a method invocation.

## CFR
CFR decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 7  
Total score: 0.67  

#### Patch Date
N/A

## JADX
JADX decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 9  
Total score: 0.73  

#### Patch Date
N/A

## Procyon
Procyon decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 9  
Total score: 0.73  

#### Patch Date
N/A

## JD-GUI
JD=GUI decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 9  
Total score: 0.73  

#### Patch Date
N/A
