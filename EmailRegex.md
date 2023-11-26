# Regex Expressions with Emails.

## Summary

In this summary I will be going over the regex components found in the regex email search found below in regex components.

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

```regex
[a-z0-9_\.-]
```
Anything from a-z (lowercase), 0-9, the _ character, the . character and the - character. For example: tes_ting.

*note: [] is used to match any character in the set*

Now, for the {} quantifier

```regex
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

Flags are put at the end of expression and change how the expression is interpreted. For example the /g and /m flags make it so the regex reads multiple instances (global) and 
across multiple lines (multiline).

****
### Grouping and Capturing

Grouping and capturing involves the use of parenthesis. In this case an example of such is `([a-z\.]{2,6})` which takes everything in the parentheis and interprets 
it as one argument (the ending of a email, for example com). 

It uses similarly in math equations.

****
### Bracket Expressions

Brackets in regex expressions are used for matching. So, for example `[a-z]` will match anything from lowercase a to z.

****
### Greedy and Lazy Match

Greedy and Lazy matches are used with a quantifier (\*, +, ?, etc.) and question marks. Lazy quantifiers search for the shortest possible string and are denoted by the quantifier followed
by a ?. Greedy quantifiers search for the longest possible string and are denoted by the quantifier (without a question mark).

We are not using lazy quantifiers in our expression for matching purposes.

****
### Boundaries

Boundaries are defined by ^ and \$ and are used to denote the end and beginning of a line. In our regex search, ^ denotes the beginning of a string (and due to /m flag, it searches for the beginning of a string) and \$, likewise, searches for the end of a string (or line).

This is why `hi this@gmail.com` does not work due to the space. While `this@gmail.com` does work. Because this@gmail.com is at the beginning of a string/line

****
### Back-references

You can use back-references to capture and reuse regex expressions. For example, the following back-reference (/1) will reuse the expression before it and use it again. So in this case, it will find a word followed by a whitespace, and only match if there are two of the same words repeated one after another ("match match" would match).

```regex
(\w+)\s\1
```

We are not using backreferences in our regex expression.

****
### Look-ahead and Look-behind

Look aheads and look behinds look, starting at the current position of the regex, ahead or behind. For example, the following positive look ahead will look for the word "hello" only if the hello is followed by the another hello (denoted by (?=hello)).

```regex
word = "hello hello world"
expression = hello(?=hello)
will find 1 hello (first hello).
```

There are also negative look aheads and look behinds denoted by a !.

```regex
positive look ahead ?=something
negative look ahead ?!something
positive look behind ?<=something
negative look behind ?<!something
```

****
## Author

My github: https://github.com/shinyuta


