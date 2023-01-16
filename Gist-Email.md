# Challenge 14 Email Regex

This Gist will explain the process and use of regular expressions that takes in a string which then verifies it as a valid 'Email' which uses appropiate email formatting.
This is done by taking the string and processing it through a Regex, also known as a "regular expression", which then takes the different characters and checks if it matches the correct
email format.

## Summary

This Regex is often used when verifying a users input is has correct email format. The Regex is shown below:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

The Regex will be broken down into components below.

---

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

---

### Anchors

This Regex' anchors are characters which match a position within a string.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

In this Email Regex, the anchors used are the:

```md
"^" and "$"
```

In our case the **_^_** is put at the very beginning to start the check at the start of the email and the **_$_** is put at the end to indicate the check will stop at the end of the email.

---

### Quantifiers

Quantifiers are used the specify how many character or set limits, groups or character classes that needs to be used in the Regex, in our case an email.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

In this Email Regex, the quantifiers used are:

```md
{2-6} and +
```

The **_+_** is used between every character class to ensure that each class must be used to validate an email.

The **_{2-6}_** was used after the **_`[a-z\.]`_** which ensures that this set of characters must be between 2 characters and 6 of the previous character set.

---

### Grouping Constructs

Regex Grouping is used to group a specific string which will then be checked over as a group instead of individual characters.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

The groups in our Regex are below:

```md
([a-z0-9_\.-]+) , ([\da-z\.-]+) , ([a-z\.]{2,6})
```

The first group is used to look for any lowercase letters from a-z, any digit from 0-9, an underscore, a hyphen and a period which will be in our case prior to the `@`.

The second group is used to look for any digit, any lowercase letter from a-z, period and hyphen which in our case would be prior to the `\.`.

The third group is used to look for any letter from a-z after a period, however has to be from 2-6 characters.

An example of the groups would be:

- Email: first@second.third

  first group = first

  second group = second

  third group = third

---

### Bracket Expressions

A bracket expression can either be a matching list expression or a non-matching list expression. It usually consists of more than one expression such as: characters, elements, symbols, etc.
Simply it encloses a list of characters between "Square Brackets = []". These are used as contraints for the input email.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

The bracket expressions used in our Email Regex are:

```md
[a-z0-9_\.-] , [\da-z\.-] , [a-z\.]
```

The first expression is looking for lowercase letters from a-z, digits from 0-9, underscore, period and/or hyphen.

The second expression is looking for any digit, lowercase letters from a-z, a period and/or hyphen.

The last expression is looking for any lowercase letter from a-z, period and/or hyphen.

---

### Character Escapes

Character escapes (`\`) are used to make the Regex not interprete the character literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a `\` before the open curly brace `(\{)` means that the regex should look for the open curle brace character instead of beginning to define the quantifer.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

Character Escapes are used multiple times within our Regex:

```md
\.- : this means that the regex should look for a . and a - instead of using them as their usual special meaning.
\d : regex should look for all digits
```

---

### Character Classes

Character Classes in a Regex are used to define a set of characters. Similar to the bracket expressions or grouping constructions, these classes group difference character types which were used in our Email Regex.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

The character classes which were used in this Regex are:

```md
a-z , Which are lowercase letters from a-z
0-9 , which are any digits from 0-9
/d , which is used also to class any digit, which is the same as 0-9
/. , Escape character "."
```

---

### Flags

Flags are used in regex that allows to modify its ways and behaviours of searching within the parameter of a Regex. Flags could make a Regex search in different sorts of ways such as globally, etc.
There are 6 different types of flags that have different jobs in the Regex.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/g`

There is only one flag used in our email regex:

```md
g : this was used at the end of the regex. This is used to make the regex search globally this means that the regex will search for all occurances. Without this flag it will only test for the first.
```

---

## Author

Ryan Zadeh (Web Developer)

GitHub: [RyanZade](https://github.com/RyanZade)
