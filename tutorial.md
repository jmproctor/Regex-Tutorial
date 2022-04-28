# Title (replace with your title)

A regular expression, or Regex, is a string that defines the search pattern in an algorithm or some software code, common uses for regex would be to validate that a valid email is input when required, or to search for a specific string  of text within a larger article. The easiest way to see it in action may be to open up webpage or document and press 'CTRL + F' to "find" whatever text you are looking for.

 ## Summary

The regex used for this tutorial is one used to search a given text for an email and the expression for it is:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  

This regex matches an email search and can be used to find all emails within a body of text or to verify an input.

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

### Anchors

When examining a regex, the starting starting points for the expression would be the anchors. In our expression, they are the symbols `^` and `$`. They indicate the beginning and end of the expression respectively.  Anchors do not match any characters in the expression, but instead are in specific `positions`.  

Looking at what is between the Anchors: `([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`. Since these contents are between the anchors, then our search much match characters defined by these parameters. We'll break this down into individual components below and make more sense of it.  

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. 

The {} quantifier can be used a couple of ways. In our case, it is written as {2,6} which means that the preceding character search must match between 2 and 6 times.

Here is a table to show the list of quantifiers supported commonly

```
* = Match 0 or more times.
+ = Match 1 or more times.
? = Match either 0 or 1 time.
{ n } = Match exactly n times.  
{ n, } = Match at least n times.  
{ n, m } = Match between n and m times.
```

### OR Operator

OR Operators, also known as "bracket expressions" are indicated by square brackets in regex expressions `[]`. 

`[a-z0-9_\.-]` | This group is saying that any letter from a-z, OR any integer from 0-9, OR a `.` OR a `-` would return a match.  
`[\da-z\.-]` | This group is saying that any DIGIT, OR any letter from a-z, OR a `.`, OR a `-` would return a match.  
`[a-z\.]` | This group is saying that any letter from a-z, OR a `.` would return a match.

You can see that the `[]` group up possible characters to indicate that the section can contain any of the different types between the brackets.

### Character Classes

A character class defines a set of characters, any one of which can occur in an input string for a match to succeed. In our expression we have a couple of these.

`\d` is a character class that looks for any digit 0-9.
`\da-z\` indicates we are looking specifically for a character that is either a digit or letter from a-z. 

### Flags

Flags are indicated by forward slashes `/` are used to begin and end the expression. Expressions use the forward slash flags to set boundaries within a search pattern. In our example, the flags are using standard functionality to begin and end the expression. Some other ways to utilize flags might be to make the search case insensitive, or look for all matches vs only the first match, or to find text within a specific position of the text.

### Grouping and Capturing

You use parentheses to group and capture the regex expression. As you can see with our example, our email search is divided into 3 `groups` using `()`.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Let's separate them to make them easier to see:

`([a-z0-9_\.-]+)` `([\da-z\.-]+)` `([a-z\.]{2,6})`  

The grouping of this breaks the search into segments that will match an email. For example, we can designate each section by an X here: `X @ X . X`

### Bracket Expressions

Bracket expressions are used to define the matchable characters within a capture group. In our case, the groups are indicated by the parentheses so each `()` is always inwardly followed by `[]`. However, we could use bracket expressions to separate types of characters within a group. For example, rather than `([])` we could have a regex with `([][])`.

### Greedy and Lazy Match

Greedy and Lazy matches refer to the restrictiveness of a particular character type or group in the regex. 

In our email regex, we only have one of these as indicated by the `+`. In our use case, the `+` is "greedy" because it will match as many times as possible within the group. If our regex contained `A+`, then it would match with "A", "AA" or for as many "A"s that are in that segment.

Lazy matches, on the other hand, operate in the opposite manner in that it would try to limit the search to as few instances as possible. Lazy matches are indicated by a `?`.

### Boundaries
Boundaries are the position between a word and a non-word character, or vice versa.

The following three positions are qualified as word boundaries: 
```
Before the first character in a string if the first character is a word character. 
After the last character in a string if the last character is a word character. 
Between two characters in a string if one is a word character and the other is not.
```

### Back-references

back-references are regular expression commands which refer to a previous part of the matched regular expression. Back-references are specified with backslash and a single digit (e.g. ' \1 ').

### Look-ahead and Look-behind

The lookbehind asserts that what immediately precedes the current position is a lowercase letter. And the lookahead asserts that what immediately follows the current position is an uppercase letter.

## Author

My name is John, I recently finished a coding bootcamp and am a new Fullstack Developer. If you want to reach out to me with and questions or feedback, feel free to message me and I will respond as soon as possible.

Github: [https://github.com/jmproctor/](https://github.com/jmproctor/)
Github Gist: https://gist.github.com/jmproctor/3052ea090f424003f6309f7cef44ff9e