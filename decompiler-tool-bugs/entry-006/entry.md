# entry-006
Presents a primitive integer as an Object to a bootstrap method parameter via an invokedynamic opcode. Example of reproduction via OW2's ASM library.

```java
methodVisitor.visitInvokeDynamicInsn("example", "(Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;Ljava/lang/Object;)Ljava/lang/Object;", bsm, 1);
```

## CFR
CFR fails on decompiling the methods with said invokedynamic present and leaves a relevant error in the method body.

#### Patch Date
2018-12-14