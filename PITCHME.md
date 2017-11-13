Regular Expressions

---

What is a regular expression?

+++

* A way of identifying/codifying a series of characters

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

* * matches any or none
  * a* matches '', 'a', or 'aaaaaaaaaa'
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

* * ? matches the fewest number of characters to make it true
  * .* on 'Hello, World' matches 'Hello, World'
  * .* ? on 'Hello, World' matches 'H'
* +? is the same as * ? except with a minimum of 1
* ?? returns the string less the quantified bit
  * humans? matches to "humans"
  * humans?? matches to "human"
* {}? quantifiers with the same as * and +  
 
---

Positions

---

* The most commonly used are ^ to indicate the beginning of a line, and $ to indicate the end
  * ^a means the line must start with an 'a'
  * ^a.* b$ means the line must start with an 'a' and end with a 'b'

+++

Other weird ones:

* \A - Begining of a string
* \Z - End of a string OR before \n at the end of the string
* \z - same as above without the or
* \G - Must be where the previous match ended
* \b - must occur at a boundry between a \w and a not \w
* \B - Not \b

---

Presentation by Shane O'Malley-Potting
