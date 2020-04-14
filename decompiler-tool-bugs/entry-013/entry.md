# entry-013
Traps a getstatic instruction and lets the fetched value fall-through into a method invocation. Semantically equivalent Java code to poc.jar:
```java
public class Hello {
    private static void doThrow(java.io.PrintStream a) {
        throw null;
    }
    
    public static void main(String[] a) {
        Hello.doThrow(System.out);
        System.out.println("you should never see this");
    }
}
```

## CFR
CFR decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change. Decompiled result of poc.jar:
```java
import java.io.PrintStream;

public class Hello {
    private static void doThrow(PrintStream printStream) {
        throw null;
    }

    /*
     * Enabled unnecessary exception pruning
     */
    public static void main(String[] arrstring) {
        try {
            Hello.doThrow((PrintStream)System.out);
        }
        catch (NullPointerException nullPointerException) {
            // empty catch block
        }
        System.out.println("you should never see this");
    }
}
```

#### Patch Date
N/A

## JADX
JADX decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change. Decompiled result of poc.jar:
```java
package defpackage;

import java.io.PrintStream;

/* renamed from: Hello */
public class Hello {
    private static void doThrow(PrintStream printStream) {
        throw null;
    }

    public static void main(String[] strArr) {
        try {
            Hello.doThrow(System.out);
        } catch (NullPointerException e) {
        }
        System.out.println("you should never see this");
    }
}
```

#### Patch Date
N/A

## Procyon
Procyon decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change. Decompiled result of poc.jar:
```java
import java.io.*;

public class Hello
{
    private static void doThrow(final PrintStream printStream) {
        throw null;
    }
    
    public static void main(final String[] array) {
        try {
            doThrow(System.out);
            null;
        }
        catch (NullPointerException ex) {
            System.out.println("you should never see this");
        }
    }
}
```

#### Patch Date
N/A

## JD-GUI
JD-GUI decompiles the method but moves the method invocation inside of the trapped range.
This results in a potential behavior change. Decompiled result of poc.jar:
```java
import java.io.PrintStream;

public class Hello
{
  private static void doThrow(PrintStream paramPrintStream)
  {
    throw null;
  }
  
  public static void main(String[] paramArrayOfString)
  {
    try
    {
      doThrow(System.out);
      return;
    }
    catch (NullPointerException localNullPointerException)
    {
      System.out.println("you should never see this");
    }
  }
}
```

#### Patch Date
N/A
