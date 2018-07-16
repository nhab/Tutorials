
.level-2 {
    padding-left: 5em;
}

## javascript regular expression
The whole idea is to finds a pattern in an _string_

The pattern is introduced in a __regular expression__
### __regular expression__


| __regular expression__  | is an expression that describes a pattern of characters. |
| :------------- |:------------- |
| __syntax__  | /pattern/modifiers;  |
| __Example__ | var n = str.search(/[03]/i); |

 ### The Modifier
| Modifier |  modifies the search | 
| :------------- |:------------- |
| g | 	Find all matches rather than stopping after the first match ( global match ) | 
| i | 	Perform case-insensitive matching| 
| m | 	Perform multiline matching| 

### The pattern

The meaning of Charachters in the pattern is decribed below

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

| char  | Description  |
|:----- |:------------ |
| . 	| Find a single character, except newline or line terminator |
| \w 	| Find a word character |
| \W 	| Find a non-word character |
| \d 	| Find a digit |
| \D 	| Find a non-digit character |
| \s 	| Find a whitespace character |
| \S 	| Find a non-whitespace character |
| \b 	| Find a match at the beginning/end of a word |
| \B 	| Find a match not at the beginning/end of a word |
| \0 	| Find a NUL character |
| \n 	| Find a new line character |
| \f  | Find a form feed character |
| \r 	| Find a carriage return character |
| \t 	| Find a tab character |
| \v  | Find a vertical tab character |
| \xxx  | Find the character specified by an octal number xxx |
| \xdd 	| Find the character specified by a hexadecimal number dd |
| \uxxxx 	| Find the Unicode character specified by a hexadecimal number xxxx |
| \t         |  horizontal tab (0x09)  |
							| \v          | vertical tab   (0x0B) |
							| \n          | newline        (0x0A) |
							| \r          | return         (0x0D) |
							| \b          | back space     (0x08) |
							| \f          | form feed      (0x0C) |
							| \a          | bell           (0x07) |
							| \e          | escape         (0x1B) |
							| \nnn         | octal char            (encoded byte value) |
							| \xHH         | hexadecimal char      (encoded byte value) |
							| \x{7HHHHHHH} | wide hexadecimal char (character code point value) |
							| \cx          | control char          (character code point value) |
							| \C-x         | control char          (character code point value) |
							| \M-x         | meta  (x|0x80)        (character code point value) |
							| \M-\C-x      | meta control char     (character code point value) |
match Control/operations
| char  | Description  |
|:----- |:------------ |
								| ^ 		| Start of line |
								| $ 		| End   of line |
								| \A 		| Start of string |
								| \z 		| End   of string |

 match preceeding character related  :

								a? 		Zero or one   of  a
								a* 		Zero or more of a
								a+ 		One or more of a
								a{3} 	Exactly 3 of a
								a{3,} 	3 or more of a
								a{3,6} 	Between 3 and 6 of a
								options: i case insensitive m make dot match newlines
								x ignore whitespace in regex o perform #{...} substitutions only once
								(...) 	Capture every 3 charachter  enclosed
								(....) 	Capture every 4 charachter  enclosed


