# entry-001
Modifies MANIFEST.MF byte headers by setting JAR archive byte offsets of 0x6
and 0x7 to 0x0 and 0x8 to 0x8.

## Bytecode-Viewer
Bytecode-Viewer crashes upon attempting to load the JAR entries. Crash log:
```
java.util.zip.ZipException: invalid entry size (expected 0 but got 443 bytes)
	at java.util.zip.ZipInputStream.readEnd(ZipInputStream.java:384)
	at java.util.zip.ZipInputStream.read(ZipInputStream.java:196)
	at java.io.FilterInputStream.read(FilterInputStream.java:107)
	at the.bytecode.club.bytecodeviewer.util.JarUtils.getBytes(JarUtils.java:175)
	at the.bytecode.club.bytecodeviewer.util.JarUtils.put(JarUtils.java:65)
	at the.bytecode.club.bytecodeviewer.BytecodeViewer$6.run(BytecodeViewer.java:849)
java.util.zip.ZipException: invalid entry size (expected 0 but got 443 bytes)
	at java.util.zip.ZipInputStream.readEnd(ZipInputStream.java:384)
	at java.util.zip.ZipInputStream.read(ZipInputStream.java:196)
	at java.util.zip.ZipInputStream.closeEntry(ZipInputStream.java:140)
	at the.bytecode.club.bytecodeviewer.util.JarUtils.put(JarUtils.java:86)
	at the.bytecode.club.bytecodeviewer.BytecodeViewer$6.run(BytecodeViewer.java:849)
```

#### Patch Date
2019-04-17

## Helios
Helios crashes upon trying to load the JAR entries. Crash log:
```
java.util.zip.ZipException: invalid entry size (expected 0 but got 443 bytes)
	at java.util.zip.ZipInputStream.readEnd(ZipInputStream.java:384)
	at java.util.zip.ZipInputStream.read(ZipInputStream.java:196)
	at java.io.FilterInputStream.read(FilterInputStream.java:107)
	at org.apache.commons.io.IOUtils.copyLarge(IOUtils.java:2146)
	at org.apache.commons.io.IOUtils.copy(IOUtils.java:2102)
	at org.apache.commons.io.IOUtils.copyLarge(IOUtils.java:2123)
	at org.apache.commons.io.IOUtils.copy(IOUtils.java:2078)
	at org.apache.commons.io.IOUtils.toByteArray(IOUtils.java:721)
	at com.heliosdecompiler.helios.controller.files.OpenedFile.readQuick(OpenedFile.java:115)
	at com.heliosdecompiler.helios.controller.files.OpenedFile.reset(OpenedFile.java:69)
	at com.heliosdecompiler.helios.controller.files.OpenedFile.<init>(OpenedFile.java:53)
	at com.heliosdecompiler.helios.controller.files.OpenedFileController.lambda$openFile$0(OpenedFileController.java:54)
	at com.heliosdecompiler.helios.controller.backgroundtask.BackgroundTask.run(BackgroundTask.java:45)
	at java.lang.Thread.run(Thread.java:748)
```

#### Patch Date
N/A
