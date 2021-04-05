# regexp
Some regexp examples from learning/courses

Regepx:
"|" = OR , example "baboons|gorillas"
"[ab]" = "a" or "b" character, example "con[sc]en[sc]us" will match all of these: consensus, concensus, consencus, concencus
"[^ab]" = not "a" and not "b", example "[^cat]" will not match any of these: c,a,t
"." = single character wildcard
"/." = matching an actual "." character
"[a-z]" = range of characters from a to z, example "I adopted [2-9] [b-h]ats"
"[A-Za-z]" = range of any alphabetical character A-Z or a-z

Shorthand character classes:
"\w" - "word character", same as "[A-Za-z0-9_]", matches a single uppercase character, lowercase character, digit or underscore
"\d" - "digit character", same as "[0-9]", matches a single digit character
"\s" - "whitespace character", same as "[ \t\r\n\f\v]", matching a single space, tab, carriage return, line break, form feed, or vertical tab
Example "\d\s\w\w\w\w\w\w\w" matches a digit character, followed by a whitespace character, followed by 7 word characters, like "3 monkeys".

Negated shorthand classes:
"\W" , "\D" and "\S"

Grouping:
Grouping to the rescue! Grouping, denoted with the open parenthesis ( and the closing parenthesis ), 
lets us group parts of a regular expression together, and allows us to limit alternation to part of the regex
Example "I love (baboons|gorillas)" will match the text "I love" and then match either "baboons" or "gorillas".

Fixed quantifier:
Fixed quantifiers, denoted with curly braces {}, let us indicate the exact quantity of a character we wish to match, or allow us to provide a quantity range to match on.
Examples:
"\w{3}" will match exactly 3 word characters.
"\w{4,7}" will match at minimum 4 word characters and at maximum 7 word characters.
"roa{3}r" will match the characters "ro" followed by 3 "a"s, and then the character "r".

Optional quantifiers:
Optional quantifiers, indicated by the question mark ?, allow us to indicate a character in a regex is optional, or can appear either 0 times or 1 time.
Note the "?" only applies to the character directly before it.
Examples:
"humou?r" matches the characters "humo", then either 0 occurrences or 1 occurrence of the letter "u", and finally the letter "r".
"The monkey ate a (rotten )?banana" will completely match both "The monkey ate a rotten banana" and "The monkey ate a banana".
"Aren't owl monkeys beautiful\?", with the escaped "?" will match "Aren't owl monkeys beautiful?".

Kleene star and Kleene plus:
The Kleene star, denoted with the asterisk *, is also a quantifier, and matches the preceding character 0 or more times.
Kleene plus, denoted by the plus +, which matches the preceding character 1 or more times.
Examples:
"meo*w" will match "mew", "meow", "meooow", and "meoooooooooooow".
"meo+w" will match "meow", "meooow", and "meoooooooooooow", but not "mew".
The regex "My cat is a \*" will completely match the text "My cat is a *".

Anchors:
The anchors hat "^" and dollar sign "$" are used to match text at the start and the end of a string, respectively.
Example:
"^Monkeys: my mortal enemy$" will completely match the text "Monkeys: my mortal enemy", but not "Spider Monkeys: my mortal enemy in the wild" or "Squirrel Monkeys: my mortal enemy in the wild".
The ^ ensures that the matched text begins with Monkeys, and the $ ensures the matched text ends with enemy
"My spider monkey has \$10\^6 in the bank" will completely match the text "My spider monkey has $10^6 in the bank"

