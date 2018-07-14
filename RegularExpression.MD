## javascript regular expression
The whole idea is to finds a pattern in an string
the pattern is introduced in a __regular expression__
#### __regular expression__
A __regular expression__ is an expression that describes a pattern of characters.

| concept  | code |
| :------------- |:------------- |
| __syntax__  | /pattern/modifiers;  |

| __Example__ | var n = str.search(/[03]/i); |


The meaning of Charachters is decribed below

### To find a range of characters : __Brackets__ []
Examples

| Expression  | Description |
| :------------- |:-------------|
| [abc] | Find any character between the brackets |
| [^abc] | Find any character NOT between the brackets |
| [0-9]  | Find any character between the brackets (any digit) |
| [^0-9] | Find any character NOT between the brackets (any non-digit) |
| (x\|y) | Find any of the alternatives specified |

### To Find a specified single characters
Examples
 char  | Description 
 :----- |:------------
. 	| Find a single character, except newline or line terminator
\w 	| Find a word character
\W 	| Find a non-word character
\d 	| Find a digit
\D 	| Find a non-digit character
\s 	| Find a whitespace character
\S 	| Find a non-whitespace character
\b 	| Find a match at the beginning/end of a word
\B 	| Find a match not at the beginning/end of a word
\0 	| Find a NUL character
\n 	| Find a new line character
\f  | Find a form feed character
\r 	| Find a carriage return character
\t 	| Find a tab character
\v  | Find a vertical tab character
\xxx  | Find the character specified by an octal number xxx
\xdd 	| Find the character specified by a hexadecimal number dd
\uxxxx 	| Find the Unicode character specified by a hexadecimal number xxxx
