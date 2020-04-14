# entry-007
Wraps the handler type class name with `L` and `;` as found
[here](https://github.com/ItzSomebody/Radon/pull/60). This is verified to cause
Java 9+ to refuse to load the class. Known to work completely fine Java 8.

## Krakatau
Krakatau is unable to decompile the method due to it not being able to find the
handler class.

#### Patch Date
2019-6-11
