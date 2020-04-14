# entry-010
Sets an invalid CRC for a ZipEntry. The JVM does not verify the CRC of a ZipEntry
allowing abuse to prevent zip extraction.

## Krakatau
Krakatau will crash on extracting the classes due to CRC verification.

#### Patch Date
N/A

## Bytecode-Viewer
Bytecode-Viewer will crash on attempting to load the JAR due to CRC verification.

#### Patch Date
2019-04-17

## Helios
Helios will crash on attempting to load the JAR due to CRC verification.  

#### Patch Date
N/A
