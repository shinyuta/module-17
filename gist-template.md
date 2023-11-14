# Title (replace with your title)


## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
****
### Anchors
The anchors ^ and \$ state that the expression after (or behind) it must be at the beginning of a line (^) or at the end of the line ($). 

In this case ^() must start a line and ()$ must end the line. More on the contents of these parentheses below.

****
### Quantifiers

In our regex expression, there are 2 quantifiers used, the + quantifier and the {} quantifier.

\+ is used to find 1 or more of the preceding expression.
In our case 

```code
[a-z0-9_\.-]
```
Anything from a-z (lowercase), 0-9, the _ character, the . character and the - character. For example: tes_ting.

*note: [] is used to match any character in the set*

Now, for the {} quantifier

```code
([a-z\.]{2,6})
```

It is being used to find anything from a-z and the . character. That is the **length** from 2-6 characters.
For example: com

****
### OR Operator

Our expression does not use the | or operator. When used in conjunction with a group though, you can (among other uses) search for words that contain a character and a couple characters after that. For example (t|T)he would find any words that contain capital T-he or lowercase t-he (so The and the).

****
### Character Classes

Character classes are also known as character sets are characterized by the characters []. They are used to find one of the expression held inside. 

```regex
[a-z0-9_\.-]
```
If this were alone, it would find any character from a-z, 0-9, the character _, the character . and the character -.

*Note: due the fact that the + quantifier is after it, the regex allows it to find any number of characters from that set (1 or more). As seen above.*

****
### Flags

The flags are not included in the original regex expression. But in order to test the regex expression I have found that the /g and /m flag are most useful. 

Flags are put the 

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
