# Entry-011

See: https://twitter.com/LeeAtBenf/status/1136035843955732486

Also see: https://github.com/ItzSomebody/openjdk-jdk8u/blob/e87709def542f064a7ab9fa75542230e40876310/hotspot/src/share/vm/classfile/classFileParser.cpp#L2137

Just for fun: a [crackme](http://crackmes.cf/users/warsaw/invisible_java_crackme/) by [Storyyeller](http://github.com/Storyyeller) which uses this trick.

Utilizes differences in the pre-Java 1 classfile format (major version 45, minor version 2 and below) and the modern Java classfile format.

Regularly, Java's [Method Code Attribute](https://docs.oracle.com/javase/specs/jvms/se12/html/jvms-4.html#jvms-4.7.3) obeys the following:

```c
Code_attribute {
    u2 attribute_name_index;
    u4 attribute_length;
    u2 max_stack;
    u2 max_locals;
    u4 code_length;
    u1 code[code_length];
    u2 exception_table_length;
    {   u2 start_pc;
        u2 end_pc;
        u2 handler_pc;
        u2 catch_type;
    } exception_table[exception_table_length];
    u2 attributes_count;
    attribute_info attributes[attributes_count];
}
```

However, pre-Java 1 classfiles do not. In pre-Java 1, the max_stack, max_locals, and code_length use half size data types. This means pre-Java 1's classfiles follow this format:

```c
Code_attribute {
    u2 attribute_name_index;
    u2 attribute_length;
    u1 max_stack; // uint8_t vs. uint16_t
    u1 max_locals; // uint8_t vs. uint16_t
    u2 code_length; // uint16_t vs. uint32_t
    u1 code[code_length];
    u2 exception_table_length;
    {   u2 start_pc;
        u2 end_pc;
        u2 handler_pc;
        u2 catch_type;
    } exception_table[exception_table_length];
    u2 attributes_count;
    attribute_info attributes[attributes_count];
}
```

This either crashes or corrupts almost all Java reverse-engineering tools due to the tool's classfile parser not taking this edge case into account.

## JD

JD parses the code attribute incorrectly leading to a decompile fail.

#### Scoring

Consistency: 10  
Practicality: 5  
Decompiler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Procyon

Procyon parses the code attribute incorrectly leading to a decompile fail.

#### Scoring

Consistency: 10  
Practicality: 5  
Decompiler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## FernFlower

FernFlower parses the code attribute incorrectly leading to a decompile fail.

#### Scoring

Consistency: 10  
Practicality: 5  
Decompiler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## ObjectWeb ASM

ASM parses and writes the code attribute incorrectly leading to a disassembly fail and an incorrectly written class.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Javassist

Javassist parses and writes the code attribute incorrectly leading to a disassembly fail and an incorrectly written class.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## BCEL

BCEL parses and writes the code attribute incorrectly leading to a disassembly fail and an incorrectly written class.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Bytecode-Viewer

BCV will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

2019-06-14

## JByteEdit

JBE will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## JByteMod-Beta

JBEB will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Helios

Helios will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## java-deobfuscator

java-deobfuscator will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Recaf

Recaf will either represent the class incorrectly or crash due to its reliance on ASM.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## dirtyJOE

DirtyJOE parses and writes the code attribute incorrectly leading to a disassembly fail and an incorrectly written class.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## radare2

radare2 parses the code attribute incorrectly leading to a disassembly fail..

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## Ghidra

Ghidra parses the code attribute incorrectly leading to a disassembly fail.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A

## javap

Javap parses code attribute incorrectly leading to a disassembly fail.

#### Scoring

Consistency: 10  
Practicality: 5  
Disassembler Inaccuracy: 5  
Total score: 0.67  

#### Patch Date

N/A
