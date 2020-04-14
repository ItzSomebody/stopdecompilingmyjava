# entry-008
Splits a block of code into two reordered sub blocks and wraps the first block
in a fake trap.

## CFR
CFR decompiles the method but merges the second block into the try block
with the first block resulting in behavior change.

Issue link: https://github.com/leibnitz27/cfr/issues/4

#### Patch Date
2019-06-13

## JD-GUI
JD-GUI decompiles the method completely wrong. The result is a behavior change and unreachable code. Decompiled result of poc.jar:
```java
import java.io.PrintStream;

public class Test
{
  public static void main(String[] paramArrayOfString)
  {
    for (;;)
    {
      System.out.println("Hello #2");
      return;
      try
      {
        System.out.println("Hello #1");
        null;
      }
      catch (FakeException localFakeException)
      {
        return;
      }
    }
  }
}
```

#### Patch Date
N/A