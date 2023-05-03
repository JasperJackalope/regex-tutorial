# Regex Tutorial: Matching a URL using Regex

A "regex" (which is short for "regular expression") is a sequence of characters that define a search pattern. It is commonly used in computer programming to search, manipulate, and validate strings of text. 

URLs, more familiarly known as links, are an every-day data type and a regex can be a useful tool for validating and parsing them.


## Table of Contents

- [Introduction](#introduction)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Practial Use Example](#practice-use-example)
- [About the Author](#about-the-author)


## Introduction

In this article, we will look at how to use a regex to match URLs that begin with either "http", "https", or "ftp" protocols. We will examine the individual components of the regex pattern, such as anchors, quantifiers, and character classes, and discuss how they work together to match URLs. By the end of this article, you will have a better understanding of how to use regexes to match URLs in your own applications.

The following regex can be used to match URLs in a string:

```regex
^(https?|ftp):\/\/[^\s/$.?#].[^\s]*$
```

Breaking down this regex:

- ^ matches the beginning of the string
- (https?|ftp) matches either "http", "https", or "ftp" protocols
- :\/\/ matches the characters "://"
- [^\s/$.?#] matches any character that is not a whitespace, forward slash, question mark, period, or hash character
- . matches a single period
- [^\s]* matches any number of characters that are not whitespace

This pattern will match URLs in the following format:

- http://example.com
- https://www.example.com/path
- ftp://example.com/file.zip


## Regex Components

In this section, we will go further into the details of how to match URLs using this regex.

```regex
^(https?|ftp):\/\/[^\s/$.?#].[^\s]*$
```

Breaking down this regex, we will look at:

- ^ matches the beginning of the string
- (https?|ftp) matches either "http", "https", or "ftp" protocols
- :\/\/ matches the characters "://"
- [^\s/$.?#] matches any character that is not a whitespace, forward slash, question mark, period, or hash character
- . matches a single period
- [^\s]* matches any number of characters that are not whitespace

This pattern will match URLs in the following format:

- http://example.com
- https://www.example.com/path
- ftp://example.com/file.zip


### Anchors

```regex
^(https?|ftp)...
```

Anchors are used to match patterns at the beginning or end of a string. In the URL regex pattern, the ^ anchor is used to match the beginning of the string.


### Quantifiers

```regex
...*$
```

Quantifiers are used to match patterns that occur a certain number of times. In this URL regex pattern, the * quantifier is used to match any number of non-whitespace characters after the first period.


### Grouping Constructs

```regex
(https?|ftp)
```

Grouping constructs are used to group parts of a pattern together. Here, ()-parentheses group the "http", "https", and "ftp" protocols together.


### Bracket Expressions

```regex
[^\s/$.?#]
```

Bracket expressions are used to match a specific set of characters. In this example, a bracket expression [^\s/$.?#] to matches any character that is not a whitespace, forward slash, question mark, period, or hash character.


### Character Classes

Character classes are used to match specific types of characters, such as digits or letters. In this URL regex pattern, they are not used.


### The OR Operator

```regex
(https?|ftp)
```

The OR operator is used to match one pattern or another. The OR operator (|) is used here to match either "http", "https", or "ftp" protocols.

### Flags

Flags are used to modify how a regex pattern is matched. In this URL regex pattern, they are not used.


### Character Escapes

```regex
^(https?|ftp):\/\/
```

Character escapes are used to match special characters that have a specific meaning in regexes. Here, the backslash character-\ is used to match any the forward slashes and colons in the protocol and domain sections of the URL.


### Practial Use Example

Here is an example of the regex patter in use in JavaScript.

```javascript
// Define the regex pattern
var url_regex = /^(https?|ftp):\/\/[^\s/$.?#].[^\s]*$/;

// Test a string to see if it matches the regex
var test_url = "https://www.example.com";
if (url_regex.test(test_url)) {
    console.log("The URL is valid.");
} else {
    console.log("The URL is not valid.");
}
```

Above, the regex pattern is assigned to the variable url_regex, and the string "https://www.example.com" is assigned to the variable test_url. The test() method is then used to test whether the test_url string matches the url_regex pattern. If the URL is valid, the program will log "The URL is valid." If the URL is not valid, the program will log "The URL is not valid."

## About the Author

Daniel Boddicker (JasperJackalope) is a full-stack developer and amateur baker based in Los Angeles. 

His GitHub can be found at: https://github.com/JasperJackalope