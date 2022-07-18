# RegEx, URLs, and You - A Guide to Understanding Regular Expression Matching in URLs

A regular expression (shortened as `RegEx`) is a sequence of characters that specifies a search pattern in text. Fields of application range from validation to parsing/replacing strings, passing through translating data to other formats and web scraping.

The concept of regular expressions began in the 1950s, where [Stephen Cole Kleene](https://en.wikipedia.org/wiki/Stephen_Cole_Kleene) formalized the concept of a regular language. Since then, regular expressions have creeped into our everyday work processes, such as search engines and the "search and replace dialogue" functions in word processors and text editors.

One of the most interesting features is that once you’ve learned the syntax, you can actually use this tool in (almost) all programming languages ​​(JavaScript, Java, C #, C / C++, Python, Ruby, and many others) with the slightest distinctions about the support of the most advanced features and syntax versions supported by the engines.

Let's take a look at an example below:


## Summary

For this example, we will look at how regular expression is used for matching a URL - specifically to work with HTTP/HTTPS protocols. The RegEx for matching to a URL is as follows:

` /^(https?://)?([\da-z\.-]+)\.([a-z.]{2,6})([/\w\.-]*)/?$/ `

To fully understand this RegEx pattern, we will break it down into its individual components below. You can also choose to move directly to a specific component in the [Table of Contents](#table-of-contents) in the following section.

## Table of Contents

- [Summary](#summary)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors

The purpose of the Anchors are to denote where the expression text begins and finishes. 

The URL RegEx anchors are denoted by the following symbols:
- " ^ " (the caret sign) marks the `start` of the RegEx and is found at the beginning of the expression.
- " $ " (the US dollar sign) marks the `end` of the RegEx and is located at the end of the expression.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.

` /^   (https?://)  ?   ([\da-z\.-]+) \.  ([a-z.]{2,6})   ([/\w\.-]*) /?$/ `

        Group 1      Group 2          Group 3         Group 4 

The URL RegEx quantifiers are denoted by the following symbols in their respective groups above:
- " ? " (the question mark sign) after `https` in Group 1 is looking for an "s" after http (which in this example, there is).
- " + " (the plus sign) in Group 2 is denoting that at least one or more of the characters in `[\da-z\.-]` will be present.
- " {} " (curly bracket signs) in Group 3 denotes that pattern `[a-z.]` will be matched at least 2 times, and a maximum of 6 times.
- " * " (the asterisk sign) in Group 4 denotes that `[/\w\.-]` may or may not appear.

### OR Operator

The OR Operator is symbolized by " | ", which is not demonstrated in the URL RegEx provided but should still be covered. Here are a few simple examples and how they would be read:
<br><br>
`"hi|hello"` matches a string that has either "hi" or "hello" in it
<br><br>
`"(b|cd)ef"` a string that has either "bef" or "cdef"
<br><br>
`"(a|b)*c"` a string that has a sequence of alternating a's and b's ending in a c
<br><br>

### Character Classes

Character Classes, sometimes referred to as "Character Sets", tell the RegEx to match only one out of several characters.

`(https?://)  ([\da-z\.-]+) ([a-z.]{2,6})  ([/\w\.-]*)`

    Group 1      Group 2       Group 3      Group 4 

The URL RegEx contains a Character Class in Group 2 and is denoted by:
- " \d " which means to find _any_ digit available and is equivalent to saying `[0-9]`.

There are more character class examples available [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes).

### Flags

Flags are optional parameters to a RegEx that modify its behavior of searching, and are located at the end of the RegEx to define additional functionality or limits within the RegEx. 

While not demonstrated in the provided URL RegEx, Regular Expressions can be modified by the following Flags:
- " i " - which denotes "Case Insensitive Search", which modifies the behavior to ignore all cases while matching a string.
- " g " - which denotes "Global Search", which modifies the behavior by testing _all_ possible matches in a string.
- " m " - which denotes "Mulitiple Line Search", which modifies the behavior to treat a multiple line input string AS multiple lines.

There are more Flag examples available [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#advanced_searching_with_flags).

### Grouping and Capturing

Groups and Capturing do exactly what they say - groups multiple patterns as a whole, and capturing groups provide extra submatch information when using a RegEx pattern to match against a string. You have already seen the RegEx broken into groups earlier, but here it is again for a fresh visualization:

`(https?://)  ([\da-z\.-]+) ([a-z.]{2,6})  ([/\w\.-]*)`

    Group 1      Group 2       Group 3      Group 4 

### Bracket Expressions

A bracket expression is either a matching list expression or a non-matching list expression, and is enclosed in two square brackets `[ ]`.

Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

Notice the use of Bracket Expressions in Group 2, 3, & 4:

`(https?://)  ([\da-z\.-]+) ([a-z.]{2,6})  ([/\w\.-]*)`

    Group 1      Group 2       Group 3      Group 4 

### Greedy and Lazy Match

Like OR Operator, this is not demonstrated in the URL RegEx provided but should still be covered. 

"Greedy" and "Lazy" are two RegEx proof of concepts as defined below:

- _**Greedy:**_ consumes as much as possible and will match the longest possible string.
    - EX. `h.+l` matches `'hell'` in `'hello'`
- _**Lazy:**_ uses as little as possible and will match the shortest possible string.
    - EX. `h.+?l` matches `'hel'`


## Author

Name: Samuel Pettyjohn <br>
Title: Developer <br>
Email: <sammpj47@gmail.com> <br>
GitHub: <https://github.com/sam-pettyjohn/> <br>