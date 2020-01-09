# StopDecompilingMyJava

This is a repository intended to succeed [samczun's repository (fork)](https://github.com/Janmm14/decompiler-vulnerabilities-and-bugs) 
by attempting to find bugs in various Java reverse-engineering tools and posting obfuscation techniques. Some differences between
samczun's repository and this one for decompiler vulnerabilities are:
* A different scoring system.
* Vulnerabilities for multiple tools, not just the 5 decompilers samczun specifically targeted.

## Scoring

Scoring for decompiler bugs/vulnerabilities is per-decompiler/tool and is split up into the following several categories:
* **Consistency** - On a scale of 1 to 10, how frequently does this bug/vulnerability occur in various samples? 10 being always, 1 being now and then.
* **Practicality** - On a scale of 1 to 10, how practical is this kind of bug/vulnerability to use/implement? 10 being easy to implement and use, 1 being extremely difficult to implement or use correctly.
* **Decompiler Inaccuracy** - On a scale of 1 to 10, how inaccurately does a decompiler display the intent of the method? 10 being a completely wrong result, 1 being an unaffected result. (Crashing the decompiler counts as 5) This scoring is omitted for non-decompiler tools.
* **Total score** - Total score is the average score (`(Score) / (Maximum score)`) rounded off to two decimals.

## Entry format

```md
# Entry name (Should be in the format entry-XXX.md)
Put description of bug / vulnerability / obfuscation technique here.

## Decompiler / Tool name (Do this for each tool this targets)
Put description of how bug / vulnerability / obfuscation technique affects decompiler / tool.

#### Scoring
Consistency: Put consistency score here  
Practicality: Put practicality score here  
Decompiler Inaccuracy: Put decompiler inaccuracy here  
Total score: Put total score here  

#### Patch Date
Put patch date here in `YYYY-MM-DD` format. If non exists, put N/A.
```
