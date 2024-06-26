# Regex Tutorial

Welcome to this comprehensive tutorial on matching email regular expressions (regex) using JavaScript in the field of Computer Science. Upon completing the tutorial, both newcomers and academics alike will have a clear comprehension and understanding of regex components, achieved through detailed explanations and example analysis. In this tutorial, we will delve into email regex, breaking down the components of a regex pattern designed to validate email addresses and explaining how each part contributes to ensuring accurate and reliable email validation.

## Summary

Throughout this tutorial, the featured regular expression (regex) as seen below, will be referenced for analysis in regards to each regex component to ensure new-comers and academics alike are able to understand and grasp material with absolute clarity. The regex components discussed in this document include: anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes.

Regex Featured in This Tutorial:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents:
- [Overview](#overview)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Email Validation Conclusion](#email-validation-conclusion)
- [Author](#author)

## Regex Components

### Anchors

Regular expressions are powerful tools for matching patterns in text. Anchors, which are special characters in regular expressions, play an essential role in defining the position of the pattern within the input string. In the context of email validation, like in the regex featured in this tutorial /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, it is crucial to ensure that the entire input string matches the specified pattern, rather than just a part of it.

Anchors Come in (2) Main Types:

Start Anchor ^: This asserts that the pattern must match the start of the string.
End Anchor $: This asserts that the pattern must match the end of the string.
Anchors essentially define the boundaries of the text that the regular expression should match.
Example One: the regex ^hello$ matches only the string "hello" and nothing else. It won't match "hello world" or "say hello" because the pattern is not at the start or end of the string, respectively.
Example Two: the regex ^hello matches any string where "hello" is at the start of the string. It will match "hello" in "hello world", but it will not match "hello" in "world hello" because the string does not start with "hello".
Example Three: the regular expression hello$ matches any string where "hello" is at the end of the string. It will match "hello" in "world hello" but it will not match "hello" in "hello world" because the string does not end with "hello".

In the context of email validation, anchors are invaluable because they help ensure that the entire email address adheres to the specified pattern. This is essential for accurate validation, as it prevents partial matches or unwanted results. By setting boundaries at the start and end of the string, anchors guarantee that the pattern matches only the intended text. They are critical components of pattern matching in text processing, particularly when validating email addresses using a regex like /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. In conclusion, anchors play a vital role in defining the position of the pattern within the input string and ensure accurate and reliable validation.

### Quantifiers

In regular expressions(regex), quantifiers are used to specify how many times a pattern should match. Quantifiers are placed after a character, character class, or group, in order to determine the minimum and maximum number of times preceding pattern occur.

The + quantifier means "one or more," and used after the pattern [a-z0-9_\.-] in the first capturing group ([a-z0-9_\.-]+). This indicates that the pattern [a-z0-9_\.-] should occur at least once, but it can also occur multiple times consecutively. Thus, the group will match one or more lowercase letters, digits, underscores, dots, or hyphens.

Similarly, the + quantifier is used after the pattern [\da-z\.-] in the second capturing group ([\da-z\.-]+). This group matches one or more digits, lowercase letters, dots, or hyphens.

The {2,6} quantifier is used after the character class [a-z\.] in the third capturing group ([a-z\.]{2,6}). This group matches a sequence of 2 to 6 lowercase letters or dots. This means that the email address must end with a two to six letter top-level domain, such as .com, .edu, or .co.uk.

Putting it all together, the regular expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ matches a valid email address that starts with one or more lowercase letters, digits, underscores, dots, or hyphens, followed by the @ symbol, followed by one or more digits, lowercase letters, dots, or hyphens, followed by a period and a two to six letter top-level domain.

### Grouping Constructs

Grouping constructs in regular expressions(regex) are used to group together one or more characters or sub-expressions, and treat them as a single unit within the expression. They are enclosed among the parentheses () and serve the following purposes:

Applying quantifiers to a group of characters.
Capturing a the designated part part of the match for later use.
Creating backreference for previously matched group.
Applying alternation to a group of characters
Our regex featured in this tutorial: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ contains three (3) Grouping Constructs enlcosed among the parentheses (). Each group captures a different part of the email address: the 1. Local-Part, 2. Domain, and 3. Top-level Domain.

Firstly, the 'Local-Part' ([a-z0-9_\.-]+) matches the username of the email address. Secondly, the 'Domain' ([\da-z\.-]+) corresponds and matches the domian name. Thirdly, the 'Top-Level Domain' ([a-z\.]{2,6}) aligns and matches the top-level domain. Furthering our distinction of the three (3) Grouping Constructs, a comprehensive breakdown of the following has been provdided below for your review:

1. Local-Part:
Firstly, the ([a-z0-9_\.-]+) matches the username of the email address.

The group represents the local-part of the email address which helps to ensure that the username follows a valid format (the part before the @ symbol) and matches one or more characters that can be:

Lowercase letters: a-z
Numbers: 0-9
Underscores: _
Dots: .
Hyphens: -
2. Domain:
Secondly, ([\da-z\.-]+) corresponds and matches the 'Domain' name.

The group represents the domain of the email address (the part between the @ symbol and the final period .). This helps to ensure that the domain name follows a valid format and matches one or more characters that can be:

Numbers: \d
Lowercase letters: a-z
Dots: .
Hyphens: -
3. Top-Level Domain:
Thirdly, ([a-z\.]{2,6}) aligns and matches the 'Top-Level Domain'.

The group represents the 'Top-Level Domain' of the email address (the part after the final period .). This helps to ensure that only the valid top-level domains are accepted and matches between 2 to 6 characters that can be:

Lowercase letters: a-z
Dots: .
Conclusion: The above Grouping Constructs are useful for capturing specific parts of the matched email address, which can then be accessed or manipulated separately. Example: regular expression(regex) validates email addresses, username and domain name can then be independently obtained and assessed for accuracy, the top-level domain can then be used to ensure only accuractly sourced domain extensions are accepted.

In conclusion, Grouping Constructs effectively group characters and sub-expressions together, in order to perform operations on them collectively as a single unit. Thus, allowing the use of complex and flexibly adapted regular expressions(regex).

### Bracket Expressions

Bracket expressions are a fundamental concept in regular expressions(regex), used to define a set of characters that can be matched within a single position in a text string. They are denoted by square brackets [...], and any character enclosed within these brackets will become a part of the allowed set. Bracket expressions can contain individual characters, and even define character ranges using a hyphen -, such as a-z for all lowercase letters or 0-9 for digits. But, what's the purpose? Simply, the bracket expressions, creates flexible patterns that match various combinations of characters in your target text.

In our regex featured in this tutorial: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ there are three (3) main bracket expressions:

Bracket Expression: One (1)
The bracket expression [a-z0-9_\.-] matches any single character in the range a-z, 0-9, or one of the characters _, ., or -. Thus the expression is used to match the Grouping Constructs: local part the username part of the email address. Here's the breakdown of this expression:

a-z: Matches lowercase letter from a to z.
0-9: Matches digit from 0 to 9.
_: Matches underscore character.
\.: Matches literal period (dot) character. The backslash is used to escape the dot since it has a special meaning in regex.
-: Matces the hyphen character.
Bracket Expression: Two (2)
The bracket expression \da-z\.- matches any single character in the range 0-9, a-z, or one of the characters ., or -. Thus the expression is used to match the Grouping Constructs: domain part of the email address. Here's the breakdown of this expression:

\d: Matches digit from 0 to 9. This is a shorthand for [0-9].
a-z: Matches lowercase letter from a to z.
\.: Matches the literal period (dot) character.
-: Matches hyphen character.
Bracket Expression: Three (3)
The bracket expression [a-z\.]{2,6} matches any single character in the range a-z or the literal period (dot) character. The expression is then followed by a quantifier {2,6}, which specifies that the matched characters must occur between 2 and 6 times, inclusive. Thus used to match the Grouping Constructs: top-level domain of the email address. Here's the breakdown of this expression:

a-z: Matches lowercase letter from 'a' to 'z'.
\.: Matches literal period (dot) character.
{2,6}: Matches quantifier that specifies the number of times the preceding expression (i.e., [a-z\.]) must be matched, which is between 2 and 6 times, inclusive.
In brief, our featured regex /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ efficiently matches valid email addresses by utilizing bracket expressions to define character sets for the username, domain, and top-level domain parts of the email as we discussed earlier. These bracket expressions combined with other regex components, ensures proper structure and formality for email addresses, making it a valuable tool in a variety of applications.

### Character Classes

Character classes, known as character sets, are a short and more concise regular expressions(regex) that represent specific sets of characters. Through the use of character classes, you can simplify and shorten regex patterns, thereby making them readable and easier to understand.

In our regex featured in this tutorial: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ uses various regex elements, including character classes, character sets, metacharacters, and repeating character classes. These elements ensure the regex are assesed and sourced accurately to match the email addresses.

Character Classes and Character Sets:
The featured email regex uses two primary character classes: \d and .. Character sets are defined within square brackets, such as [a-z], [0-9], and [.-]. These sets represent multiple characters, allowing a single character match from the specified range.

Negated Character Classes:
The negated character classes are not something which are present throughout this email regex. However, they are denoted by a caret (^) symbol inside square brackets, for example, [^a-z]. Remember, for future use this negation would match any character that is not a lowercase letter from a to z.

Metacharacters Inside Character Classes:
The metacharacters are characters with special meanings in regex, such as the dot (.). Inside character classes, some metacharacters lose their special meaning and are treated as literals. In our featured email regex, the hyphen (-) and the dot (.) are metacharacters placed inside character classes [a-z0-9_.-] and [\da-z.-]. The dot is escaped with a backslash (.), and the hyphen is used as a literal character without escaping, as it is placed at the beginning or end of the character set.

Repeating Character Classes:
The email regex uses the + and {2,6} quantifiers to indicate repeating character classes as discussed before. The plus sign (+) matches one or more occurrences of the preceding character class or set, as in [a-z0-9_.-]+ and [\da-z.-]+. Therefore the curly braces ({2,6}) define a specific range of repetitions for the preceding character class or set, as in [a-z.]{2,6}, which matches 2 to 6 occurrences of lowercase letters or the literal period (dot) characters found.

Thereby, the combination of these elements among our featured regex allows the email to accurately be sources and validated to ensure it matches email addresses using a clear and organized representation of the compulsory character sets.

### The OR Operator

The OR operator, also known as alternation, is a crucial concept in regular expressions for defining alternative patterns. It's represented by the | symbol, allowing the regex to match either one pattern or another. Among our regex featured in this tutorial: ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, there is no OR-Operator that exists nor explicitly used. Though it is not used, it is important to note for future use, as it is essential to understand its function for more complex patterns to come in your academic and professional career.

OR-Operator Usage Purpose:
Used to specify alternative patterns among regex, enhancing its flexibility and matching capabilities.
Syntax: | used to separate alternative patterns in the regex.
E.g: The regex ^(Flying Birds| Non-Flying Birds)$ matches either the string Flying Birds or Non-Flying Birds, but cannot match both or other strings.
Crucial for functioning with regular expressions, the OR operator allows the creation of flexible and adaptable patterns. Although it is not explicitly used in our featured email regex, the OR-Operator remains a key concept for those learning and utilizing regular expressions in various applications among their studies.

### Flags

Flags are modifiers which affect the behavior of regular expressions(regex) by enabling or disabling certain features and are appended to the end of the regex pattern, outside the slashes /.

Though our regex featured in this tutorial: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ does not use flags, it's important to understand its purpose in regex patterns. Flags are used to control case sensitivity, multiline matching, and global matching. I would advise for any new-comer to learn more about flags, so you are able to enhance your regex knowledge.

Flag tpes you may find in future use:
g (global): Enables global matching, regex engine will find all matches in the input string.
i (ignore case): Enables the regex case-insensitive, matching both uppercase and lowercase characters.
m (multiline): Enables start (^) and end ($) anchors to match at the beginning and end of each line in a multiline string, rather than just the beginning and end of the entire string.
s (dotAll): Enables dot . metacharacter match any character, including newline characters.
u (unicode): Treats input string as Unicode, enables correct processes of Unicode surrogate pairs.
y (sticky): Mandates regex engine ro iniate searching for a match at the exact position specified by the lastIndex property.
We're able to conclude this section by saying are essential in modifying the behavioir of patterns found among regex. Although it is not utilized in our regex featured in this tutorial /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, understanding the use of flags will enhance your use regex patterns to accommodate varrying requirements and situations.

### Character Escapes

Character escapes are an essential aspect of regex, allowing for accurate pattern matching by suppressing the special meaning of metacharacters and representing characters that cannot be directly typed. In our regex featured in this tutorial /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ we can identify the use of character escapes and their purposes:

Backslash (\):
The backslash is a common escape character used to treat metacharacters as literals in regex. Throughout our featured regex, the dot (.) is escaped with a backslash, exactly like this \.. Thus ensuring the dot is treated as a literal period instead of a metaphorical wildcard.

Metacharacters:
Metacharacters have siginifcant meaning in regex, such as the dot (.), plus sign (+), and caret (^). When placed among character classes, they often lose their special meanings and behave as though they are regular characters... In our featured email regex, the hyphen (-) is used as a literal character inside the character classes [a-z0-9_\.-] and [\da-z\.-] without needing to be escaped.

Escape sequences:
Escape sequences, are characters that can not be directly typed or represented in a string, so escape sequences are the implemented, then used. These sequences start with a backslash (\) followed by a letter or combination of letters. In the email regex, \d is an escape sequence that represents any digit from 0 to 9, serving as a shorthand for the use of [0-9].

Character escapes serve a crucial role for ensuring accurately matching text patterns by interpreting special characters as literals. They help suppress the special meanings of metacharacters and represent characters that can't be directly typed. Thereby, ensuring the proper functioning of regex expressions that contribute to reliable email validation.

## Author

Follow me on Github at JacksonByrd7.  Until we meet again.

Deployed link: 

Repository link: 
