# entry-007
Wraps the handler type class name with `L` and `;` as found
[here](https://github.com/ItzSomebody/Radon/pull/60). This is verified to cause
Java 11 to refuse to load the class. Known to work all the way up to Java 8
(1.8.0_201).

## Krakatau
Krakatau is unable to decompile the method due to it not being able to find the
handler class.

#### Scoring
Consistency: 10  
Practicality: 3  
Decompiler Inaccuracy: 5  
Total score: 0.60  

#### Patch Date
2019-6-11
