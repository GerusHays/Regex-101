# What is a Regular Expression (regex)? 

The purpose of this file is to introduce users to regex by breaking down an example of the regular expression. 

## Summary
We will be breaking down the regex for "Matching a URL" utilizing the following expression: </br>
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```
You may select through the Table of Contents below detailing the different sections of the above regex!

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

## Regex Components
Every regex is considered a literal, the pattern MUST be wrapped with "/" characters as you can see depicted in our example above by beginning and ending with a "/". </br>
Below we will be diving deeper by deconstructing the regex between the slashes!
### Anchors
The anchors will be identified by two characters seen throughout regular expressions. </br>
With the carrot symbol ^ signifying the beginning of the Regular expression and the dollar sign $ signifying the end of an expression.

### Quantifiers
Quantifiers are the unqiue characters you will see in regex strings. </br>
They set the limit of the string that your regex will match. They often include the minimum and maximum number of characters that the regex is looking for. </br>
Some examples of regex symbols you may encounter are 
```
*        +          ?
```
The Quantifers within our regex are ? and * symbols. </br>
The question mark is used to idenify optional characters within the regex. </br>
For example within our regex we have. 
```
(https?:\/\/)?
```
The first question mark in the above example just tells the expression that the "s" in https is optional. Due to some url's being written as https or http. Then the question mark at the end of the example means that https in general is optional so you can just go to a website via google.com without the http entirely. </br>
We also have an asterisk within our regex in the below example. 
```
([\/\w \.-]*)*\/?$/
```
The \w allows any alphanumerical character. The * is depicting that the group can happen any number of times and may be followed by the same characters or group any number of times. </br>

The last quantifier is the {2,6}. </br>
What this is saying in our regex is that this portion of our URL may only contain 2-6 characters. Due to this being the tail end of the url like .com or .net
### OR Operator
Our regex does not contain any OR operators but if you are to see this symbol: | 
That is what refers to as an OR operator. For example </br>
```
^I like (dogs|penguins), but not (lions|tigers).$
```
This will pop out any of the following strings. 
```
I like dogs, but not lions.
I like dogs, but not tigers.
I like penguins, but not lions.
I like penguins, but not tigers.
```
### Character Classes
A character class in a regex defines sets of characters. Some common character classes you may encounter within a regex are: 
- . (period or dot) - Matches any character except the newline character (\n)
- \d - Matches any numeralical digit. and a capital \D matches a non-digit character
- \w — Matches any alphanumeric character from the alphabet, including the underscore
- \s — Matches a single whitespace character, including tabs and line breaks
Our regex contains the following character classes: \d and \w with the following examples below.
```
[\da-z\.-]
[\/\w \.-]
```
The entire expression of \d is looking for the entire url name. With it looking for any numerical digit, any letter and any periods or dashes. </br>
The \w is looking for everything after the .com or .net like http://www.google.com/mail it will find the /mail.
### Flags
Our regex does not contain flags but below is describing what a regex flag is. </br>
Flags are placed at the end of a regex after the second slash, and they define additional functionality or limits for the regex.</br>
There are 6 separate flags that may be used but below are the 3 most common ones. </br>
- g - Global Search: tested against all possible matches in the regex string
- i - Case insensitive: case is ignored when attempting to match the regex string
- m - multi line: multi line input string is treated as multiple lines

### Grouping and Capturing
For grouping and capturing you can break up any regex into multiple parts and read it as such. </br>
For our regex we can break it up into 4 parts as depicted below. 
```
/^(https?:\/\/)?
([\da-z\.-]+)\.
([a-z\.]{2,6})
([\/\w \.-]*)*\/?$/
```
- The first line is the http portion as we discussed earlier that is optional. 
- The second line is the website name followed by a period.
- The third line is the last part of the url basically the .com or .net as discussed earlier. 
- The fourth line is the file path after the .com that can be repeated multiple times. 
### Bracket Expressions
Bracket expressions are the part of the regex that has square brackets around it []. </br>
Bracket expressions are looking for similarities in our case our regex has the following bracket expressions: 
```
[\da-z\.-]
[a-z\.]
[\/\w \.-]
```
We mostly went over the functionality of the regex already above but for example the first bracket expression is looking for any character and period or dash.

### Greedy and Lazy Match
Quantifiers are also referred to as "Greedy Operators" and are able to match as much as possible through the provided text. </br>
We make them lazy by adding in the question mark quantifier. </br>
In our regex the {2,6} limits how many letters it will look for in the URL making it greedy (no more than 6 but no less than 2). Making it lazy would just be adding a question mark at the end. 
### Boundaries
Our regex has no boundaries. However, if you were to add a \b (which is an anchor) this is called a word boundary with a match of zero-length. 

## Author

This Regex tutorial was created by Gerus Hays and can be found on Github at [GerusHays](https://github.com/GerusHays).
