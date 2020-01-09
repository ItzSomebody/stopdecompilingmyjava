# entry-001
Modifies MANIFEST.MF byte headers by setting jar archive byte offsets of 0x6
and 0x7 to 0x0 and 0x8 to 0x8.

## Bytecode-Viewer
Bytecode-Viewer crashes upon trying to load the jar entries.

#### Scoring
Consistency: 10  
Practicality: 7  
Total score: 0.85  

#### Patch Date
2019-04-17

## Helios
Helios crashes upon trying to load the jar entries.

#### Scoring
Consistency: 10  
Practicality: 7  
Total score: 0.85  

#### Patch Date
N/A