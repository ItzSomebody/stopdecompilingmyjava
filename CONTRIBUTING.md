# StopDecompilingMyJava Contribution Guide

## Table of Contents
* [GitHub](#github)
    * [Issue Reports](#issue-reports)
    * [Pull Requests](#pull-requests)
* [Styleguides](#styleguides)
    * [Git Commit Messages](#git-commit-messages)
    * [Entry Documentation]

## Github
### Issue Reports
Make sure to read the following before submitting a report:

#### Before Submitting an Issue Report
* **Check if the issue has already been reported**. Should this be the case, add a comment on the existing issue instead of opening a new one.

#### Submitting an Issue Report as an Issue with Repo
* **Use a clear and descriptive title**.
    * Example of a **good** title: "Entry-XXX incorrectly documents FernFlower stacktrace"
    * Example of a **good** tite: "Entry-XXX misleadingly described as buggy invokedynamic"
    * Example of an **acceptable** title: "Entry-XXX has a misleading description"
    * Example of a **bad** title: "Entry-XXX is wrong"
    * Example of a **bad** title: "Entry-XXX"
* **Be as specific as possible when describing the issue**.  Anyone who is reading the issue should be able to understand exactly what the issue is with no further questions asked.
    * For example, saying that Entry-XXX incorrectly documents a FernFlower stacktrace but the report fails to post the correct stacktrace does not meet this goal.
* **If applicable, attach an updated PoC (proof of concept) Java binary.**  This is completely optional, but if this is applicable to the issue, please make sure to provide enough information for me or someone else to create a PoC.

Extra: [this video](https://www.youtube.com/watch?v=53zkBvL4ZB4&vl=en) by
[LiveOverflow](https://github.com/LiveOverflow) and this [webpage](http://www.catb.org/esr/faqs/smart-questions.html)
are good references for properly asking a question.

#### Submitting an Issue Report as a Entry Request
If, for whatever reason (maybe you don't know enough about Java bytecode, or something related), you decide to recommend/request entries via issues instead of pull requests, please make sure to do the following:

* **Use a clear and descriptive title**. Please also prefix the title with [Request/ER] so there's no room for confusion.
    * Example of a **good** title: "[ER] Recaf crasher from obfuscator XXXX"
    * Example of a **good** title: "[Request] Sample crashes FF/CFR/Procyon"
    * Example of a **bad** title: "suggestion"
    * Example of a **bad** title: "thing to make repo better"
* **Upload a sample binary or post a link to tool.** Please make sure to give me enough information to obtain whatever it is you want added to the repo.

Please also keep in mind that if you submit a request via issues and it is accepted, it will be committed to repo by me or whoever adds it.  This means that the actual commits to the repo will not be shown under your GitHub commit history; however, I will do my best to make sure you are credited for contributing.

### Pull Requests
Pull requests should fulfill one of the following:
* Fix spelling / grammatical errors.
* Fix issues reported on the issue tracker.
* Implement a request on the issue tracker..
* Documentation to adhere to the specified style guides.
* Replace poorly-written entries with properly written entries.
* If new entries are added, [QUICKLINKS.md](./QUICKLINKS.md) must be updated accordingly.

The rules for guidelines are pretty simple:
* Follow the style guides.
* No need to squash commits. Though, feel free to do so if you wish.

## Style guides
#### Git Commit Messages
* Use present tense.
* Use the imperative mood.

#### Entry Documentation
* All entries should be written in the third person and past tense.
* All entries should be written in English that is grammatically correct enough to where it is easy to read.
* All entries should adhere to the following format:

```md
# Entry name (Should be in the format entry-XXX.md)
Put description of bug / vulnerability / obfuscation technique here.

## Decompiler / Tool name (Do this for each tool this targets)
Do the following (each point should have heading level three):
* Describe how bug / vulnerability affects decompiler / tool.
* Detail which version of tool was being tested (git commit hash are acceptable provided you provide a link to the repo)
* Detail JVM behavior
* Any links to issue/bugtrackers, GitHub issues, etc. relevant to the entry.

#### Patch Date
Put patch date here in `YYYY-MM-DD` format. If non exists or unknown, put N/A. If possible, also add version patching the entry.
```
