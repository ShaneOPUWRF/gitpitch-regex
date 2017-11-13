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

'.\d\w' matches 'a2b', 'b23' but not 'a', '222' 'a2 '

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


Presentation by Shane O'Malley-Potting
