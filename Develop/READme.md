# Title (coles gist guide)

Introductory paragraph (replace this with your text)

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

### Anchors
In regex, anchors are special characters that allow you to match specific positions within a string. Anchors do not match any actual characters but rather represent spots in a string.
EX. const string = "Hello, World!";
const regex = /^Hello/;
const match = regex.test(string);

console.log(match); // Output: true

the regex pattern /^Hello/ matches the beginning of the string and looks for the exact sequence "Hello". Since the string starts with "Hello", the test() method returns true.
similarly, EX.const string = "Hello, World!";
const regex = /World!$/;
const match = regex.test(string);

console.log(match); // Output: true
In this case, the regex pattern /World!$/ matches the end of the string and looks for the exact sequence "World!". Since the string ends with "World!", the test() method returns true.
### Quantifiers
Quantifiers are used to specify the number of occurrences or repetitions of a character, group, or pattern in a string. They allow you to define the quantity or range of matches you want to find.
EX.const string = "aaabbbccc";
const regex = /a{2,3}b{2,3}c{2,3}/;
const match = regex.test(string);

console.log(match); // Output: true
Quantifiers allow you to express different repetition scenarios and provide more flexibility in defining your regex patterns.
### OR Operator
the OR operator is denoted by the pipe symbol |. It allows you to specify alternative patterns to match within a regex pattern. It acts as a logical OR, allowing you to match either one pattern or another.
EX.const string = "cat";
const regex = /cat|dog/;
const match = regex.test(string);

console.log(match); // Output: true
The regex pattern /cat|dog/ matches either "cat" or "dog". The OR operator | separates the two alternative patterns, and the regex engine will try to match the input string against both options.
### Character Classes
character classes are used to specify a set of characters that can be matched at a particular position in a string. They allow you to define a range or group of characters and match any single character from that set.
EX.const string = "a1b2c3";
const regex = /[a-z]\d/g;
const matches = string.match(regex);

console.log(matches); // Output: ['a1', 'b2', 'c3']
 the regex pattern [a-z]\d matches any lowercase letter followed by a digit. The g flag is used to find all matches in the input string. As a result, the match() method returns an array containing all the matches found in the string.
### Flags
 flags are optional parameters that modify the behavior of the pattern matching. They are added after the closing delimiter of the regex pattern and change how the pattern is interpreted and applied to the input string.
 EX.const string = "Hello, hello, hello!";
const regex = /hello/gi;

const matches = string.match(regex);

console.log(matches); // Output: [ 'Hello', 'hello', 'hello' ]
In the example, we have a string that contains the word "hello" multiple times, with different letter casing. The regex pattern /hello/gi uses the g flag for global matching and the i flag for case-insensitive matching.
### Grouping and Capturing
Grouping and capturing are terms commonly used in regular expressions (regex), which is a pattern matching language used to search, manipulate, and validate strings. In the context of regex, grouping and capturing refer to the ability to create subgroups within a larger regex pattern and capture the matched content within those subgroups.
EX.const string = "Hello, World!";

// Grouping and capturing using parentheses
const regex = /(Hello), (World)!/;
const match = string.match(regex);

if (match) {
  const fullMatch = match[0];     // Full match
  const greeting = match[1];      // Captured group 1: "Hello"
  const target = match[2];        // Captured group 2: "World"

  console.log(fullMatch);        // Output: "Hello, World!"
  console.log(greeting);         // Output: "Hello"
  console.log(target);           // Output: "World"
}

### Bracket Expressions

### Greedy and Lazy Match
Greedy matching: By default, regex matching is greedy. It means that the regex engine tries to match as much of the input string as possible. For example, the regex pattern a.*b will match the longest possible substring starting with "a" and ending with "b". If the input string is "aabcdb", the match will be "aabcdb".

Lazy (or non-greedy) matching: Lazy matching is the opposite of greedy matching. It makes the regex engine match as little as possible to fulfill the pattern. It is denoted by the ? quantifier. For example, the regex pattern a.*?b will match the shortest possible substring starting with "a" and ending with "b". If the input string is "aabcdb", the match will be "aab".
EX. const string = "aabcdb";
const greedyRegex = /a.*b/;
const lazyRegex = /a.*?b/;

const greedyMatch = string.match(greedyRegex);
const lazyMatch = string.match(lazyRegex);

console.log(greedyMatch); // Output: [ 'aabcdb' ]
console.log(lazyMatch);   // Output: [ 'aab' ]

### Boundaries
Boundaries are used to match specific positions in a string rather than matching actual characters. They allow you to define conditions or constraints on where a match should occur within the input string.
EX.const string = "Hello world, how are you?";
const regex = /\bhow\b/;

const matches = string.match(regex);

console.log(matches); // Output: [ 'how' ]

### Back-references
Selectors are functions that know how to extract specific pieces of information from a store state value. As an application grows bigger, this can help avoid repeating logic as different parts of the app need to read the same data:

const selectCounterValue = state => state.value

const currentValue = selectCounterValue(store.getState())
console.log(currentValue)
// 2
### Look-ahead and Look-behind
Look-ahead: Look-ahead assertions allow you to match a pattern only if it is followed by another pattern. It provides a way to define a condition that must be satisfied without including it in the actual match. Look-ahead is denoted by a pair of parentheses ( ) with a question mark and an equal sign (?= ).
Look-behind: Look-behind assertions allow you to match a pattern only if it is preceded by another pattern. It provides a way to define a condition that must be satisfied without including it in the actual match. Look-behind is denoted by a pair of parentheses ( ) with a question mark and a less-than sign (?<= ).
## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
