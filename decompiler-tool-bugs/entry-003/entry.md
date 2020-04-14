# entry-003
Prepends META-INF/\u0000/ to the start of a class name which is a method of hiding classes against file
archivers popularized by samczsun. However, this trick is incompatible with Java 7, and any Java version above 9.

## Non-Java Archivers
Non-Java archivers (7zip, WinRAR, Windows, etc.) are unable to display the classes.

#### Patch Date
N/A
