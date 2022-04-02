# URL Regex Tutorial

You may be asking yourself...what is Regex 🤔  
Regex or Regular Expressions are a sequence of characters that specifies a search pattern in text, they are a way to describe patterns in a string data. You can use regular expressions to check a string of characters for an email address, password, URL, Hex Value, Phone Numbers, Addresses and the list goes on.  
___

## Summary

For this Regex Tutorial, I will be explaining how to search for and match a valid URL.   

Here is a snippet of the code we will be following  
`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

    The Breakdown
    1. Starts with https or http 
    2. Special Character string ://
    3. Subdomain www
    4. Full Character Stop
    5. Second Level Domain
    6. Full Character Stop
    7. Top Level Domain
    8. Subdirectory
___

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

The expression begins and ends with an anchor. Anchors do not match any specific character, they match a position before or after the charcters. Our expression uses **^** and **$**.  
    - ^ - The caret anchor will match the beginning of the text/string    
    - $ - The dollar anchor will match the end of the text/string  

### Quantifiers

Quantifiers will match a number of instances of a character, group or character class in a string.  
They can be defined as *, +, ?, and {}. Our express uses *, **+**, **?** and **{}**. The * and + are greedy quantifiers, meaning they will try to match as much of the string as possible. If the ? quantifer is used after any quantifier, it will make the that quantifer non-greedy, so it will stop after if finds a match.  
    - * - The asterisk quantifier means zero or more, matches the preceding item zero or more times  
    - + - The plus quantifier means one or more, matches the preceding item one or more times  
    - ? - The question quanitfier mean zeor or one, matches the preceding item zero or one time  
    - {} - The curly braces quantifier specify the number of times the characters in front of the braces are found in the search  
        - ([a-z\.]{2,6}) -> This code states that the minimum amount of permitted matches of the characters a-z will be 2 and the maximum amount of permitted matches will be 6

### OR Operator

The OR Operator **|** is used to match the characters or expressions of either the left side or the right side of the operator.  
This code does not have any OR Operators.

### Character Classes

Character classes are used to distinguish characters. They can match different characters in a single position present inside of brackets[] .  

The most common character classes are:  
    | Character | Description                                                             |
    |---|---|
    | \d        | digit -> a character from 0 to 9                                        |
    | \s        | white space                                                             |
    | \w        | word -> it can be a letter of the alphabet, a digit or an underscore    |
    | .         | this will match any single character except a new line (\n)             |

Our expression has the following code block `[\da-z\.-]` with a character class.  
The \da-z will remove any character that is not a digit (\d) or a lower case letter (a-z).  

### Flags

Flags are optional parameters to modify the search pattern. This tutorial does not include the use of Flags.  
Here are some commong Flags and their meanings.  

    |Flag    | Description                                                                                                |
    |--------|:----------------------------------------------------------------------------------------------------------:|
    | g      | Global -> does not return after the first match, restarting from the end of the previous match             |
    | m      | Multi-Line -> when used with the ^ and $ it will match the start and end of the line, not the whole string |
    | i      | Insensitive -> turns the whole expression case-insensitive                                                 |  


### Grouping and Capturing

Grouping in regular expressions uses (). They are used to create blocks of patterns to apply reppetitions or processing parts of a match, this allows the expression to grab part of the match as a seperate item in the result array. Adding a quantifier after the () applies to the parentheses as a whole. Captured groups are read from left to right and assigned a group number. 
This tutorial has four sets of captured groupings `(https?:\/\/)` `([\da-z\.-]+)` `([a-z\.]{2,6})` `([\/\w \.-]*)`  

### Bracket Expressions

A Bracket Expression [] is a list of characters enclosed in [square brackets] and will match any single character in that list.
This tutorial has three sets of the Bracket Expression  
    `[\da-z\.-]`  -> searches for any digit from 0-9, any lower case letter from a-z and ends with a literal period  
    `[a-z\.]`     -> searches all lower case letters from a-z and ends with a literal period  
    `[\/\w \.-]`  -> searches for all word characters uppercase, lowercase letters, digits from 0-9 and underscores  
                    \/\w is creating a word boundary  

### Greedy and Lazy Match

Greedy Match = longest possible string -> for every position in the string, try to match the pattern in that position, no match go to the next position.  
Lazy Match = shortest possible string -> to make the expression lazy you add a ? after the quantifier i.e. *?, +?, ??.  
In this tutorial there are no lazy matches.  

### Boundaries

There are no boundaries in this code block `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`  
/b presents as an anchor and matches positions where one side is a word (digits, letters, underscore) and the other side is a non word (space character or beginning of the string). They are used when you would like to catch and match a sequence of letters or digits on their own or have them at the beginning or the end of the sequence of characters.  

### Back-references

This tutorial does not use and back-references.  
Back-References looks for a previously matched group and then looks for the exact same text again later in the expression.  
`[0-9][-/ ][a-z][-/ ][0-9]`  

### Look-ahead and Look-behind

Look-Aheads and Look-Behinds are also known as Lookarounds, they allow for the user to find only the matches for pattern that are followed or preceded by another pattern.  
Look-Aheads allows for adding a codition for what follows the expression  
Look-Behinds allows for adding a codition to match a pattern only if there is something before it  
There are no Lookarounds in this tutorial.  

## Author

Kelly Dingman - wife, mother 🦄 🦖 🐾 , someone looking to better their career and learn all about coding.  

[GitHub Profile](https://github.com/kdingman)
