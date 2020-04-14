# entry-009
Inserts a try-catch block with a handler type of null (used to implement finally
keyword). It will always delegate the control flow into a specific region of code.
Semantically equivalent Java code to poc.jar:
```
public class Test {
    private static int willBeTrue;
    
    private static void doThrow() {
        willBeTrue = 1;
        throw null;
    }
    
    public static void main(String[] a) {
        try {
            Test.doThrow();
        } catch(Throwable ignoredException) {
        }
        if (willBeTrue != 0) {
            System.out.println("Hello");
        }
    }
}
```

## Procyon
Procyon does not recognize the non-javac-like use of a null catch type. This
results in inaccurate code due to the exception not being handled correctly. Decompiled result of poc.jar:
```java
public class Test
{
    private static int willBeTrue;
    
    private static void doThrow() {
        Test.willBeTrue = 1;
        throw null;
    }
    
    public static void main(final String[] array) {
        try {
            doThrow();
        }
        finally {}
        if (Test.willBeTrue != 0) {
            System.out.println("Hello");
        }
    }
}
```

#### Patch Date
N/A

## FernFlower
FernFlower does not recognize the non-javac-like use of a null catch type.
This results in inaccurate code due to the exception not being handled correctly. Decompiled result of poc.jar:
```java
public class Test {
   private static int willBeTrue;

   private static void doThrow() {
      willBeTrue = 1;
      throw null;
   }

   public static void main(String[] var0) {
      try {
         doThrow();
      } finally {
         ;
      }

      if (willBeTrue != 0) {
         System.out.println("Hello");
      }

   }
}
```

#### Patch Date
N/A

## JD-GUI
JD-GUI does not recognize the non-javac-like use of a null catch type. This
results in completely wrong code which is in no way semantically equivalent. Decompiled result of poc.jar:
```java
import java.io.PrintStream;

public class Test
{
  private static int willBeTrue;
  
  private static void doThrow()
  {
    willBeTrue = 1;
    throw null;
  }
  
  public static void main(String[] paramArrayOfString)
  {
    for (;;)
    {
      if (willBeTrue != 0) {
        System.out.println("Hello");
      }
      return;
      try
      {
        doThrow();
      }
      finally {}
    }
  }
}
``` 

#### Patch Date
N/A
