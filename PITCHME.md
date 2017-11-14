Regular Expressions

---

What is a regular expression?

+++

A string of text that allows you to create patterns that help match, locate, and manage text. 
(https://www.computerhope.com/jargon/r/regex.htm)

+++

We'll make /[NPW].\*(?:[sno])(?= ) \d{1,2}/ match

* Nintendo 64
* Playstation 4
* Windows 10

But not 

* Comodore 64
* Xbox 360
* Wii U
* Gameboy 3DS

---

Regular Expression Basics

+++

* A '.' matches any character
* \d only matches digits (0-9)
* \w only matches word characters (letters, numbers, some special characters)
* \s only matches whitespace (space, tabs, sometimes newlines)
* \D, \W, \S match characters that _aren't_ matched by their lowercase brethren
* Some languages do have special strings for these, such as [[:digit:]] for \d

+++

Example

'.\d\w' matches 'a2b', 'b23' but not 'a', '2a2' 'a2 '

+++

Character Groupings

* [a,d] matches only the characters a & d
* [a-z] matches only the letters a-z lowercase
* [a-zA-Z] matches all letters any case
* [0-9] is the same as \d
* [0-9abc] matches all numbers and the letters abc
* (ab|c) matches _either_ ab OR c (not a, not b, ab)

---

Quantifiers

+++

This is where things get... fun.

+++

Greedy Quantifiers

+++

* \* matches any or none
  * a\* matches '', 'a', or 'aaaaaaaaaa'
* + matches 1 or more
  * a+ matches 'a', 'aaaaaaaa', but not ''
* ? matches 1 or less
  * a? matches '', 'a', but not 'aaaaaa'
  * Actually it will, but just the first a

+++

* {n} matches exactly n characters
  * a{3} matches 'aaa', but not 'a'
* {n,} matches a minimum of n characters
  * a{3,} matches 'aaa', 'aaaaa', but not a
* {n,m} matches a minumum of n characters, and a maximum of m
  * a{2,3} matches 'aa' and 'aaa', but not 'a' or 'aaaa'
* {,n} matches a maximum of n characters
  * a{,2} matches '', 'a', 'aa', but not 'aaa'

+++

Lazy Quantifiers

+++

Hold on to your butts.

+++

* \*? matches the fewest number of characters to make it true
  * .\* on 'Hello, World' matches 'Hello, World'
  * .\*? on 'Hello, World' matches 'H'
* +? is the same as \*? except with a minimum of 1
* ?? returns the string less the quantified bit
  * humans? matches to "humans"
  * humans?? matches to "human"
* {}? quantifiers with the same as * and +  
 
---

Positions

+++

* The most commonly used are ^ to indicate the beginning of a line, and $ to indicate the end
  * ^a means the line must start with an 'a'
  * ^a.\*b$ means the line must start with an 'a' and end with a 'b'

+++

Other weird ones:

* \A - Begining of a string
* \Z - End of a string OR before \n at the end of the string
* \z - same as above without the or
* \G - Must be where the previous match ended
* \b - must occur at a boundry between a \w and a not \w
* \B - Not \b

---

Looking Around

+++

Look Aheads

* (?=) matches the _previous_ item if the item in the parenthesis matches the following characters
  * w(?=\d{7}) will match the 'w' ONLY if it is followed by 7 digits
* (?!) Matches the previous item only if the item in the perenthesis doesn't match the following characters
  * w(?!\d{7}) will match the 'w' unless it is followed by 7 digits
  
+++

Look Behinds

* Not supported in many languages
* Performance usually (relatively) sucks

+++

* (?<=) Matches the previous item if the item is not preceeded by the parenthsised item
  * day(?<=good ) will only match the word 'day' if it is preceeded by 'good '
* (?<!) Negates the above

---

Capturing

+++

* () groups the surrouded items in what is called a capture group
* (?:) creates a non-capture group
  * (?:ab){3} matches 'ababab', but doesn't caputure it

+++

What can capture groups do for you?

+++

Capture groups can be used to reference already matched values

* 'Hello (.\*?), your name is \1'

+++

Capture groups may also be used in programming languages and other tools, as you will see.

---

Activities 

[https://alf.nu/RegexGolf]
[https://regexcrossword.com/]

---
Presentation by Shane O'Malley-Potting
