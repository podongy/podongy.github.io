---
layout: post
title: Effective Python
---

# * Readability Counts.
* Follow the PEP 8 Style Guide

  - <https://www.python.org/dev/peps/pep-0008/>

* **Write Helper Functions Instead of Complex Expressions**
> As soon as your expressions get complicated, it’s time to consider splitting them into
> smaller pieces and moving logic into helper functions. **What you gain in readability
> always outweighs what brevity may have afforded you. Don’t let Python’s pithy syntax for
> complex expressions get you into a mess like this.**
* Avoid Using start, end, and stride in a Single Slice
* **Use List Comprehensions Instead of map and filter** 
* **Avoid More Than Two Expressions in List Comprehensions**
* Avoid else Blocks After for and while Loops (because their behavior isn’t intuitive) 
> The `else` block after a loop only runs if the loop body did not encounter a `break` statement.
# * Pythonic Codes
* Consider Generator Expressions for Large Comprehensions
