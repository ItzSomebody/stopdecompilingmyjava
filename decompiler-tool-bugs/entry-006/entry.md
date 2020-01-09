# Entry-006
Presents a primitive integer as an Object to a bootstrap method parameter via an invokedynamic opcode.

```java
methodVisitor.visitInvokeDynamicInsn("example", "(Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;)Ljava/lang/Object;", bsm, 1);
```

## CFR
CFR fails on decompiling the methods and leaves a relevant error in the method body.

#### Scoring
Consistency: 10  
Practicality: 5  
Decompiler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date
2018-12-14