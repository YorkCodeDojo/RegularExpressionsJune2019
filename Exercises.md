Regular Expressions Dojo
==========================

# Rules

1. You should work in pairs (or threes)

2. You should complete the exercises using Test-Driven-Development (TDD)

3. The refactoring stage is very important.  After each exercise discuss in your group alternative ways of solving the problem.  Re-write your solution if required.  The aim of tonight is not to complete all the exercises but think about different approaches.

4. Within your group you should take it in terms to write the code.  One approach is to swap roles after each test.

5. Don't use an existing regular expression library!

6. Any doubt on how the expression is meant to work,  then test it out online,  for example use https://regex101.com/ 

7. The exercises intentionally don't cover the full regular expression language.

8. Use Git/GitHub and regularly commit your changes.

# Exercises


## Single Literals

The pattern `a` matches any string which contains the letter 'a'

| Pattern | Input | Result      |
|---------|-------|-------------|
|    `a`    |  abc  | Matched     |
|    `b`    |  abc  | Matched     |
|    `b`    |  abc  | Matched     |
|    `2`    |  123  | Matched     |
|    `d`    |  abc  | Not Matched |

e.g
```
  Assert(True,  Match('a', 'abc') )
  Assert(False,  Match('d', 'abc') )
```


## Multiple Literals

The pattern `david` matches any string which contains the word 'david'

| Pattern | Input | Result      |
|---------|-------|-------------|
|    `ab`   |  abc  | Matched     |
|    `ab`   |  cde  | Not Matched |

---
## Starts with anchor
A `^` means the start of a string.  For example ^a will match abc but not cba

| Pattern | Input | Result      |
|---------|-------|-------------|
|    `^a`   |  abc  | Matched     |
|    `^b`   |  abc  | Not Matched |

---
## Ends with anchor
A `$` means the end of a string.  For example c$ will match abc but not cba

| Pattern | Input | Result      |
|---------|-------|-------------|
|    `c$`   |  abc  | Matched     |
|    `a$`   |  abc  | Not Matched |
|  `^abc$`  |  abc  | Matched     |

---
## OR
A `|` means OR.  For example a|b will match aaa and bbb but not ccc

| Pattern | Input | Result      |
|---------|-------|-------------|
|  `a|b`  |  a    | Matched     |
|  `a|b`  |  abc  | Matched     |
|  `a|b`  |  aaa  | Matched     |
|  `a|b`  |  b    | Matched     |
|  `a|b`  |  c    | Not Matched |
---

## Character Sets
Surrounding a rule with [] acts a bit like brackets in normal algebra.  For example `[a|b]c` will match `ac` and `bc` but not `cc`

| Pattern | Input | Result          |
|---------|-------|-----------------|
|  `[a|b]c` |  abc  | Matched (on bc) |
|  `[a|b]c` |  bac  | Matched (on ac) |
|  `[a|b]c` |   a   | Not Matched     |
|  `[a|b]c` |   c   | Not Matched     |
---

## ? Quantifier

? means 0 or 1 matches

| Pattern | Input | Result          |
|---------|-------|-----------------|
|  `a?b`  |  ab   | Matched  |
|  `a?b`  |  b   | Matched  |

---

## + Quantifier

+ means 1 or many matches

| Pattern | Input | Result          |
|---------|-------|-----------------|
|  `ca+b`  |  cb   | Not Matched  |
|  `ca+b`  |  cab   | Matched  |
|  `ca+b`  |  caab   | Matched  |
|  `ca+b`  |  caaab   | Matched  |

---

## * Quantifier

* means 0 or many matches

| Pattern | Input | Result          |
|---------|-------|-----------------|
|  `ca+b`  |  cb   | Matched  |
|  `ca+b`  |  cab   | Matched  |
|  `ca+b`  |  caab   | Matched  |
|  `ca+b`  |  b   | Not Matched  |