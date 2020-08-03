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

* **Prefer Helper Classes Over Bookkeeping with Dictionaries and Tuples**
  *  **(Avoid dictionaries that contain dictionaries!!!)**
> **Avoid making dictionaries with values that are other dictionaries or long tuples.**
> Use `namedtuple` for lightweight, immutable data containers before you need the
> flexibility of a full class.

# * Pitfalls 

* Be Defensive When Iterating Over Arguments
> An iterator only produces its results a single time. If you iterate over an iterator or generator 
> that has already raised a StopIteration exception,
> you won’t get any results the second time around. 

* Use None and Docstrings to Specify Dynamic Default Arguments
> Default arguments are only evaluated once: during function definition at module
> load time. This can cause odd behaviors for dynamic values (like {} or []).
> Use None as the default value for keyword arguments that have a dynamic value.
> Document the actual default behavior in the function’s docstring.
```python
def log(data,default=[]):
    default.append(data)
    print(default)

log(1,[]) -> [1]
log(1)    -> [1]
log(3,[]) -> [3]
log(3)    -> [1,3] (not [3])
```

* Use Threads for Blocking I/O, Avoid for Parallelism
> Python threads can’t run bytecode in parallel on multiple CPU cores because of the
> global interpreter lock (GIL)

* Use Lock to Prevent Data Races in Threads
> Although only one Python thread runs at a time, the GIL will not protect you. 

* Define Function Decorators with functools.wraps

# * Pythonic Codes
* Consider Generator Expressions for Large Comprehensions
* Prefer Public Attributes Over Private Ones
* **Inherit from collections.abc for Custom Container Types**
> **Much of programming in Python is defining classes that contain data and describing how
such objects relate to each other.**
> Have your custom container types inherit from the interfaces defined in
> collections.abc to ensure that your classes match required interfaces and
> behaviors.
* Use Plain Attributes Instead of Get and Set Methods
* Use subprocess to Manage Child Processes
* Consider contextlib and with Statements for Reusable try/finally Behavior
* Make pickle Reliable with copyreg
* Profile Before Optimizing
* Use tracemalloc to Understand Memory Usage and Leaks
* Use Built-in Algorithms and Data Structures


   Data Structure | Description
   ---------------|----------------------
   Double ended Queue (deque) | inserting or removing items from its beginning or end    
  Ordered Dictionary (OrderedDict)| keeps track of the order in which its keys were inserted 
  Default Dictionary (defaultdict)| automatically storing a default value when a key doesn’t exist  Heap Queue (heapq)| maintaining a priority queue
  Bisection (bisect)|  provide an efficient binary search through a sequence of sorted items.

# * Not sure...
* Enforce Clarity with Keyword-Only Arguments
* Use @classmethod Polymorphism to Construct Objects Generically
  * Is it better than Factory pattern?
* Use Multiple Inheritance Only for Mix-in Utility Classes
  * Or don't use multiple inheritance
* Inherit directly from Python’s container types (like list or dict) for simple use cases.
  * Beware of the large number of methods required to implement custom container types correctly.
* Consider @property Instead of Refactoring Attributes
  * 
