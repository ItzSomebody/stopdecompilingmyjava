# StopDecompilingMyJava

This repository, inspired by [samczun's repository (fork)](https://github.com/Janmm14/decompiler-vulnerabilities-and-bugs),
contains edge cases which raise bugs in Java reverse-engineering tools. Some differences between
samczun's repository and this one for decompiler vulnerabilities are:
* No scoring system.
* The edge cases found in this repository also aim to work against RE tools in general, not just the 5 in samczsun's repository.

## Entry format

```md
# Entry name (Should be in the format entry-XXX.md)
Put description of bug / vulnerability / obfuscation technique here.

## Decompiler / Tool name (Do this for each tool this targets)
Put description of how bug / vulnerability / obfuscation technique affects decompiler / tool.

#### Patch Date
Put patch date here in `YYYY-MM-DD` format. If non exists, put N/A.
```
