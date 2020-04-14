# entry-004
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
In the PoC linked with the entry, this should decompile to
```java
public class Example {
    public static void main(String[] var0) {
        System.out.println(-893664644 ^ -893664644);
    }
}
```

## FernFlower
FernFlower is unable to parse the stack correctly resulting in changed code and sometimes illegal
code. Decompiled result of poc.jar:
```java
public class Example {
   public static void main(String[] var0) {
      int var10001 = -893664644;
      System.out.println(-893664644 ^ 2030482428);
   }
}
```

#### Patch Date
Unknown

## JD-GUI
JD-GUI is unable to parse the stack correctly resulting in changed and, in some cases, illegal code. Decompiled result of poc.jar:
```java
import java.io.PrintStream;

public class Example
{
  public static void main(String[] paramArrayOfString)
  {
    -893664644;
    System.out.println(0x7906B3FC ^ 0xCABBC27C);
  }
}
```

#### Patch Date
N/A