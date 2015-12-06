# Coding style

As this program is related to Plan 9, its code follows similar style guidelines. So, this document try to recall _"style"_ on _"man, section 6"_ deliberately, gathering some guidelines.

* Don't use "//" making commentaries. Use "/\*" and "\*/" instead. The first one can be used to comment-out code sometimes.
* No tabs expanded to spaces.
* Tabs width is intended to be 8 characters.
* Don't include in headers (nor in a file candidate to be included).
* Don't include files twice for the same translation unit.
* Surround a binary operator with spaces, particularly a low precedence one. Readable better than compact.
* No white spaces before opening braces nor after the keywords "if", "for", "while", etc.
* Variable and function names are all lowercase and with no underscores.
* "Enums" and defined constants should be Uppercase or UPPERCASE.
* "Struct" tags are Uppercase, and "typedefs" must match (if any).
* Automatic local variables in a function are never initialized at declaration.
* Always compare the result of a string OR memory comparison with zero using a relational operator. Avoid "!strcmp(...)", "!memcmp(...)" and such.
* To check if a pointer is enabled or disabled, comparisons must be explicit (e.g., avoid "!p", use "p != nil" instead).

## Comments

A readable code does not need many comments. A line or two above a function explaining what it does is always welcome.

Comment any code you find yourself wondering about for more than two seconds, even if it's to say that you don't understand what's going on. Explain why.

Commenting is *not* for excuse your unreadable code. Rewrite it to make it clear.

## See also
man 6 style (on Plan 9, /sys/man/6/style)

"Notes on Programming in C", Rob Pike.
http://www.literateprogramming.com/pikestyle.pdf
