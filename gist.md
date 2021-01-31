# RegEx Tutorial

Regular expressions (regexes) are a pattern of characters That are used for specific purposes. They are used in algorithims when wanting to search for specific text. They are also used when wanting to validate inputs. Each character in the expression has a specific meaning which is compared to text and determines if the text matches a defined pattern.

## Summary

This gist will focus on how regular expressions can validate the inputs in an email. Here is an example of a regular expression for an email. 

<center>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</center>
<br/><br/>
Each component in this expression will be descibed in detail.
<br/><br/>
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Escaping](#escaping)

## Regex Components

### Anchors
Anchors are characters that define what is at the start and end of the string that is being evaluated. You have have an anchor at the beginning which is denoted by a "^", or an anchor at the end which is denoted by a "$" or neither where you don't have a "^" or a "$". 
In the email expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, a begiinning anchor and a ending anchor have been stated.
The beginning anchor "^" says that the text at the starting of the string matches the expression. In the email, [a-z0-9_\.-] says that that the email can have a alphabet character from a to z, the character can be a number from 0 to 9, can be an underscore, dot, or hyphen.
The  "$" says that the end for the string has requirements.  The expression  ([a-z\.]{2,6})$ states that the end of the string can only be a alphabet a-z or a dot and must be between 2 and 6 characters long.
### Quantifiers
Quantifiers are characters that specifies how often a preceding element can occur.
- "?" says that the preceding element can occur zero or one time.
- "*" says that the preceding element can occur zero or more times.
- "+" says that the preceding element can occur one or more times.
- "{min,max}" says that the preceding element must occur a minimum number of times but not more than the max number of times.

In the email expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, The "+" quantifier says that the items preceding the "+" (which are the what is in the brackets) can be one and repeated more times.
The {2,6} quantifier says that the items in the bracket must be at least 2 characters and no more than 6 characters long.
### OR Operator
The "or" operator "|" allows there to be a choice in matching where the expression matches before or after is acceptable. In this email example, there are no "or" operators.
### Character Classes
Character classes are characters that represent a larger group of characters. Here are some examples.
- "." which represents any character except characters on a new line
- "\w" repesents words
- "\W" represents not words
- "\d" represents digits
- "\D" represents ont digits
- "\s" represents whitespace
- "\S" represents not whitespace
- "[abc]" represents a,b, or c
- "[^abc]" represents not a,b, or c
- "[a-z]" represents character between a and z

In the email /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. character classes a-z and "d" are used.
This means that a letter a to z and a digit from 0 to 9 can be in the string.

### Flags
Flags are optional arguments that change the meaning of the expression pattern. Here are some examples.
- "i" which says to ingore capital casing so that "A" and "a" are considered the same when searching.
- "g" which looks for all matches when there is a search.
- "m" which affects "^" and "$" behavior across multiple lines. when searching.
- "s" flag enables "dotall" to match newline character.
Flags were not used in the email pattern.
### Grouping and Capturing
Capturing is enclosing portions of a regex pattern with parentheses so that quantifiers can be applied to what is inside the parentheses.
In the email expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, the expression is broken down to ^()@().()$
### Bracket Expressions
Brackets encase a set of characters to match. In the first part of the expression [a-z0-9_\.-], inside the brackets says that a character can be a alphabet from a to z, it can also be a number from 0 to 9, it can be a underscore, or it can be a hyphen.
The second bracket [\da-z\.-], the characters can be a digit or a letter from a to z, The third bracket [a-z\.], the characters can be a letter from a to z or a dot.
### Greedy and Lazy Match
Greedy and lazy matching are algorithims that try to match a pattern but do it in different ways.
When searching a string, at every position in the string, greedy tries to match the pattern at every position in the string. If no match is found, the search continues to the next position.
Once the string ends and if the pattern has not completed, the search backtracks by one character attempting to match the next pattern expression. It will continue this step until the pattern is complete or it does not validate.
Lazy matching, which has a "?" behind the quantifier, matches the pattern differently. Once a match is made for the expression, the next expression is searched. The search engine does not backtrack through the string once it is complete.
This email example doe not use greedy or lazy matching.
### Escaping
In emails, the is a dot in the email address. Since dot is a special character which has a special meaning, there needs to be a way to just have a dot in the expression.
in order to make a special character not a special character (escaping), a backlash is put in front of the special character.
So in the pattern, you see in several places a \. which is the expression for the character dot.

## Author

Just a student learning how to code!  

Github: https://github.com/anthonykieu/RegEx-Tutorial