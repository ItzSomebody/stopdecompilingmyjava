# Entry-006
Presents a primitive integer as an Object to a bootstrap method parameter via an invokedynamic opcode.

```java
methodVisitor.visitInvokeDynamicInsn("example", "(Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;)Ljava/lang/Object;", bsm, 1);
```

## CFR
CFR is unable to decompile the method.

#### Scoring
Consistency: 10  
Practicality: 5  
Decompiler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date
N/A