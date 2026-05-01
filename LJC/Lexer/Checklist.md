- [ ] Unicode character with ascii escapes (p. 21)
	- [ ] needs to happen before any other reduction
- [ ] Line terminators ^546875
	- [x] LF
	- [x] CR
	- [x] CR LF
		- [ ] one line terminator (p. 24)

## Input
`{InputElement} [Sub]`
- [ ] Input element
- [ ] Sub (p. 25)
	WTF is this shit?
	I think we just need to ignore a `Sub` character (`ctrl-Z`) if it appears at the end of the file
### Whitespace
- [x] Space
- [ ] Horizontal tab
- [ ] Form feed
- [ ] [[#^546875|Line terminators]]
### Comment
- [x] Comments do not nest
- [x] `/*` and `*/` have no special meaning in comments that begin with `//`.
- [x] `//` has no special meaning in comments that begin with `/*` or `/**`.
- [ ] Comments do not occur within character literals, string literals, or text blocks
### Token
- [ ] Literal token always takes precedence over identifier (p. 25)
- [x] Reserved keyword (not contextual) always takes precedence over an identifier (p. 25)
- [ ] `>` when appears in a type context, always reduced to `>` and not `>>` (p. 25)
	- This is to avid `List<List<String>>` ending with a right shift operator
	- Probably requires having a single token "right angle", because I don't think we can distinguish this at the lexer stage.
#### Identifiers
Unlimited length sequence of *Java letters* and *Java digits* (p. 28)
- *Java letter*: `Character.isJavaIdentifierStart(int)`
- *Java letter-or-digit*: `Character.isJavaIdentifierPart(int)`
- [ ] Has to start with a *Java letter*
- [ ] Can include *Java letter-or-digit*s
- [ ] Cannot be a reserved keyword or a boolean literal or a null literal
- [ ] *Java letter* includes `$` and `_`
	- [ ] `$` should only be used in mechanically generated code (probably should issue a warning) (p. 28)
	- [ ] `_` cannot be used as a one-character identifier (p.28)
- [ ] Should allow also characters from other languages
- [ ] Some characters in identifiers are ignorable (`Character.isIdentifierIgnorable`) (p. 29)
- [ ] A type identifier cannot be `permits`, `record`, `sealed`, `var`, or `yield`
- [ ] An unqualified method identifier cannot be `yield`
- [ ] Contextual key words are identifiers if followed by a `letter-or-digit` (with no whitespace.) (p. 32)
#### Literals
##### Integer Literals
- [x] base 16 denoted by `0x` or `0X` (p. 36)
- [x] base 2 denoted by `0b` or `0B` (p.  38)
- [x] base 8 denoted by leading 0 in a non 0 integer (p. 37)
- [x] `l` or `L` suffix turns it to a long (p. 34)
- [ ] `_` between digits (p. 34)
	- [ ] Not immediately after `0x` or `0b`
	- [ ] not after the last digit
	- [x] in octal number can be after leading `0`
	- [x] can have multiple consecutive `_`
- [ ] 2147483648 (2^31) can only appear as the operand of the unary `-` operator (p. 39 - p. 40)
- [ ] 9223372036854775808L (2^63) can only appear as the operand of the unary `-` operator (p. 39 - p. 40)
- [ ] Must have at least one digit (can't have `0x`)
##### Floating point literals
- [ ] for decimal literals, at least one digit (in whole number or fraction) and either: decimal point, exponent, or float type suffix (p. 41)
	- [ ] exponent indicated by `'e'` or `'E'`
- [ ] for hexadecimal literals, at least one digit (in whole number or fraction), and the exponent. (p. 41)
	- [ ] float type suffix optional
	- [ ] exponent indicated by `'p'` or `'P'`
- [ ] underscores only allowed between digits of the same part (p. 41)
- [ ] of type float if signified by `'f'` or `'F'` suffix
	- [ ] otherwise double, and can have `'d'` or `'D'` suffix
- [ ] constant expressions such as `1f/0f` or `-1d/0d`, `POSITIVE_INFINITY`, `NEGATIVE_INFINITY` represent infinities.
- [ ] Exponent can be negative
- [ ] Make sure to check other restrictions (p. 42 - p. 43)
##### Boolean literals
- [x] `true` or `false`
##### Character literals
- [x] Can be a single character
- [ ] Can be a valid escape sequence
	- [ ] limited to `U+0000`-`U+ffff` (p. 44)
	- [ ] Cannot be `\u00a` (LF) or `\u000d` (CR) or `\u0027` (apostrophe, `'`) because they are translated as an actual escape sequence (p. 45)
- [ ] Cannot have line terminators

CharacterLiteral:
	' SingleCharacter '
	' EscapeSequence ' 
	
SingleCharacter: 
	InputCharacter but not ' or \
	
InputCharacter: 
	UnicodeInputCharacter but not CR or LF

UnicodeInputCharacter: 
	%% UnicodeEscape %% 
	RawInputCharacter 
	
RawInputCharacter: 
	any Unicode character representable in UTF-16
	
%% UnicodeEscape: 
	\ UnicodeMarker HexDigit HexDigit HexDigit HexDigit  %%

%% UnicodeMarker:
	u {u} %%

%%HexDigit: 
	(one of) 0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F%%
	
EscapeSequence: 
	\ b (backspace BS, Unicode \u0008) 
	\ s (space SP, Unicode \u0020) 
	\ t (horizontal tab HT, Unicode \u0009) 
	\ n (linefeed LF, Unicode \u000a) 
	\ f (form feed FF, Unicode \u000c) 
	\ r (carriage return CR, Unicode \u000d) 
	\ LineTerminator (line continuation, no Unicode representation) 
	\ " (double quote ", Unicode \u0022) 
	\ ' (single quote ', Unicode \u0027) 
	\ \ (backslash \, Unicode \u005c) 
	OctalEscape (octal value, Unicode \u0000 to \u00ff)
	
OctalEscape: 
	\ OctalDigit 
	\ OctalDigit OctalDigit 
	\ ZeroToThree OctalDigit OctalDigit 

OctalDigit: 
	(one of) 0 1 2 3 4 5 6 7
	
ZeroToThree: 
	(one of) 0 1 2 3


##### String literals
- [ ] Cannot have line terminators
- [ ] Can include valid escape sequences
- [ ] String literals in the same class and package represent references to the same `String` object (p. 47)
- [ ] String literals in different classes in the same package represent references to the same String object (p. 47)
- [ ] String literals in different classes in different packages likewise represent references to the same String object. (p. 47)
- [ ] Strings concatenated from constant expressions (§15.29) are computed at compile time and then treated as if they were literals. (p. 47)
- [ ] The result of explicitly interning a computed string is the same String object as any pre-existing string literal with the same contents.
##### Text blocks
- [ ] Can have escape sequences
- [ ] Can have new lines etc directly in the text blocks
- [ ] Other restrictions (p. 48)
##### Escape sequences
- [ ] `\b` (backspace BS, Unicode \u0008) 
- [ ] `\s `(space SP, Unicode \u0020) 
- [ ] `\t`(horizontal tab HT, Unicode \u0009) 
- [ ] `\n` (linefeed LF, Unicode \u000a) 
- [ ] `\f` (form feed FF, Unicode \u000c) 
- [ ] `\r` (carriage return CR, Unicode \u000d) 
- [ ] \ LineTerminator (line continuation, no Unicode representation) 
- [ ] `\"` (double quote ", Unicode \u0022) 
- [ ] `\'` (single quote ', Unicode \u0027) 
- [ ] `\\` (backslash \\, Unicode \u005c)
- [ ] Octal escape
	- [ ] 1-3 octal digits (if 3 digits, first one is `0`, `1`, `2`, or `3`) (p. 53)
##### Null literal
- [x] `null`
##### Separators
- [x] `(` `)` `{` `}` `[` `]` `;` `,` `.` `...` `@` `::`
##### Operators
- [x] `=` `>` `<` `!` `~` `?` `:` `->` `==` `>=` `<=` `!=` `&&` `||` `++` `--` `+` `-` `*` `/` `&` `|` `^` `%` `<<` `>>` `>>>` `+=` `-=` `*=` `/=` `&=` `|=` `^=` `%=` `<<=` `>>=` `>>>=`