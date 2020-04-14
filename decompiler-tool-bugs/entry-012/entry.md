# entry-012

In newer versions of JVM 1.8 and above, the JVM allows classefile JAR file entries to be suffixed
with "/" in fooling multiple tools into treating the classfile as a directory. Notably used in
the [Paramorphism](https://paramorphism.dev/) Java bytecode obfuscator.

A more detailed writeup can be found [here](https://github.com/cookiedragon234/fakedirectory).

Note: this will not work on earlier versions of JVM 1.8 and below.

## Bytecode-Viewer

BCV does not take this edge case into account when loading the JAR archive entries and as a result
does not parse the classfiles.

#### Patch Date

N/A

## JByteEdit

JBE does not take this edge case into account when loading the JAR archive entries and as a result
does not parse the classfiles.

#### Patch Date

N/A

## JByteMod-Beta

JBM does not take this edge case into account when loading the JAR archive entries and as a result
does not parse the classfiles.

#### Patch Date

N/A
