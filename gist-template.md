<!-- @format -->

# Matching an Email using regex

Below, I will be going in depth into the different components that make this regex functional to search for valid email addresses. The purpose of this tutorial is to go in depth as to how this specific regex works.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary. This regex validates a user's email by checking that it only contains letters, numbers, and certain special characters, as well as checking for the domain used such as 'gmail' or 'yahoo'.

## Table of Contents


  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
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
  - [Author](#author)

## Regex Components
## Anchors
Anchors are used to signify a search for a string with the following characters or numbers in it. This is done using "^" and "$".  

Using "^" will match any strings that start with that word while using "$" will match any string that ends with the word or query put right before it.  

- Example : "The cute dog ran around the yard"  
- Regex Search : ^The  
- Return : "The"  
- Explanation : Because the T was capitalized in the regex search, it will only return the first "the" in the sentence because the second one has no capitalization. Using this direct method of searching for specific characters makes it case-sensitive.  
- Regex Search : yard$   
- Return : yard  

## Quantifiers
Quantifiers are used to specify how long the match should be, they typically include a minimum and maximum number. There are different quantifiers that will go into even more specifications such as the following :   
- "*" - means that it matches the pattern 0+ times    
- "+" - means that it matches the pattern 1+ times    
- "?" - means that it matches the pattern 0 or 1 time  
- "{}" - Can provide 3 different ways to set specifications for the match :    
- "{n}" - matches the pattern exactly n amount of times  
- "{n,}" - matches the pattern at least n amount of times  
- "{n, x}" - matches the pattern a minimum of n amount of times, and a maximum of x amount of times  

## OR Operator
The OR operator is used to add a function that allows the regex to search for a given number OR a different given number. This is done by adding "|" between the specified letters or numbers in the expression.

- "(a|b|c):(l|m|o)" - This would hit a match even if the string was "acb:lmo" because it's searching for the second letter to be a, b OR, c.

## Character Classes
A character class defines a set of numbers, letters, or special characters. They are sort of shortcuts to represent groups of certain types of character's so the user doesn't have to type out each one individually.
- "." - This will match to any character except \n.
- "\d" - This will match to any number.
- "\w" - This will match to any alphanumeric character in the Latin alphabet. This includes underscores, numbers, and letters.
- "\s" - Will match to any whitespace, line breaks, or tabs.

## Flags
A regex must be wrapped in slash characters unless a flag is used. Flags are put at the end of a regex and they help outline the limits for the regex. There are six flags in total, however, three of them are the most commonly used.
- "g" - Is a global search meaning it should be tested against every match in the string.
- "i" - Is a case-sensitive search meaning it should be ignored when trying to match.
- "m" - Is a multiline search, is treated as multiple lines.
## Grouping and Capturing
As regular expressions grow more complicated, it's important to understand grouping constructs. Grouping constructs are used to break sections of the expression up by using parentheses or colons.

- "(abc):(xyz)" - This is how to represent two grouping constructs  
- "abc:xyz" - This would look for a string that's an exact match

There are two main categories for grouping constructs, caputring and non-capturing. Capturing groups catch the matched character sequence so that it can be re-used whereas non-capturing groups do not. Adding "?:" will make the construct non-capturing.

## Bracket Expressions
In a regex, the brackets are used to represent a range of characters or numbers that the user needs to match to. This is what bracket expressions are, these expressions can be used to specify specific characters to be included in the search or a range can be used.

- "[a-z]" - This will search for any lowercase letters between and including a and z in the alphabet. The same can be done for capital letters.
- "[0-9]" - This will search for a string containing any number
- "[_-]" - This will search for a string containing an underscore or a hyphen.

## Greedy and Lazy Match
Typically a regex finds a match by matching the pattern to the string it's searching through. With a greedy search, it will match to anything it can whereas a lazy match will function by telling it to repeat as few times as possible.

For example, "+" is used as a quantifier will function as many times as possible but if a question mark is added it will only repeat once.

## Boundaries
Boundaries are very similar to anchors. However, anchors use ^ and $ while boundaries use \b. Boundaries are used to make assertions about what is allowed to be matched to the left and right. There are two different types of boundaries, word boundaries and non-word boundaries.

- Word boundaries match the positions where one side is a word character and the other side is not.
"\bcat\b" - This would match "cat" in the phrase "black cat" because as long as "cat" is in the phrase the other letters don't matter.

- Non-word boundaries uses "\B" instead and will match when neither side is a letter or when both sides are words.

## Back-references
If using a capture group, this is an ideal method to use. Backreferencing is used to backreference that previously captured match.

- For example, if the capture group only caught one match, you would reference in the regex by adding a "\1".

## Look-ahead and Look-behind
These are zero-length assertions similar to the start and end of a line. Look-ahead and look-behinds matches characters but will return match or no match rather than listing the actual matches themselves. It simply searches the data and returns whether or not there is a match possible, similar to a boolean.
### Author

I am a student in University of Denver's Coding Bootcamp and I am diversifying and furthering my studies by exploring the topic of regular expressions and the components that allow them to function properly. You can find my GitHub profile at https://github.com/SThevenot
