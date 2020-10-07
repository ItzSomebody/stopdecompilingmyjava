# entry-014

Uses invalid attributes to crash ASM:
```Java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 284
	at org.objectweb.asm.ClassReader.readUnsignedShort(ClassReader.java:3363)
	at org.objectweb.asm.ClassReader.readStringish(ClassReader.java:3493)
	at org.objectweb.asm.ClassReader.readModule(ClassReader.java:3523)
	at org.objectweb.asm.ClassReader.readModuleAttributes(ClassReader.java:720)
	at org.objectweb.asm.ClassReader.accept(ClassReader.java:544)
	at org.objectweb.asm.ClassReader.accept(ClassReader.java:400)
```

## How
Versions of ASM that support java > 8 include support for attributes such as Module, NestHost and more. 
ASM has no version check before parsing these attributes.

The JVM, however, does check the class files version before attempting to parse these attributes.
If the attribute was defined in a version younger than the class file, the attribute will be skipped.

Therefore, by defining a Java 8 class file with an invalid Module attribute ASM will fail to parse a valid class file.

Other attributes are also vulnerable and can be used to obfuscate newer class file versions.

## Example Code
```Kotlin
fun main() {
	val main = ClassNode().apply {
		name = "Test"
		superName = "java/lang/Object"
		version = V1_8
		
		methods.add(MethodNode().apply {
			access = ACC_STATIC or ACC_PUBLIC
			name = "main"
			desc = "([Ljava/lang/String;)V"
			
			// insn builder api is available in github.com/bytechef/paperbin sources
			instructions = insnBuilder {
				+printlnAsm("hi")
				_return()
			}
		})
		
		attrs = attrs ?: arrayListOf()
		attrs.add(DummyAttribute("Module"))
	}
	val cw = ClassWriter(ClassWriter.COMPUTE_MAXS)
	main.accept(cw)
	val bytes = cw.toByteArray()
	File("Test.class").writeBytes(bytes)
}

private class DummyAttribute(name: String, bytes: ByteArray = ByteArray(Random.nextInt(2))): Attribute(name) {
	init {
		content = bytes
	}
}
```
```Bash
$ java Test
hi
```

## History
I've been using this exploit in my obfuscator Binscure ever since I discovered it in March this year. Since its now found its way into many other obfuscators I am publishing this writeup.
