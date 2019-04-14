# Entry-010
Sets an invalid CRC for a ZipEntry. Java does not verify the CRC of a ZipEntry
allowing abuse to prevent zip extraction.

## Krakatau
Krakatau will crash on extracting the classes.

#### Scoring
Consistency: 10  
Practicality: 7  
Decompiler Inaccuracy: 5  
Total score: 0.73  

#### Patch Date
N/A

## Bytecode-Viewer
Bytecode-Viewer will crash on attempting to load the JAR.

#### Scoring
Consistency: 10  
Practicality: 7  
Decompiler Inaccuracy: 5  
Total score: 0.73  

#### Patch Date
N/A

## Helios
Helios will crash on attempting to load the JAR.

#### Scoring
Consistency: 10  
Practicality: 7  
Decompiler Inaccuracy: 5  
Total score: 0.73  

#### Patch Date
N/A
