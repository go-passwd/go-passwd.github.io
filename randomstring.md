# Go random string generator

## Generate random string

Generating a random 20-character string with lower letters, upper letters and digits:

~~~go
import "gopkg.in/randomstring.v1"

s := randomstring.Generate(20)
~~~

Generating a random 20-character string with lower letters:

~~~go
import "gopkg.in/randomstring.v1"

s := randomstring.Generate(20, randomstring.LowerLetters)
~~~

## Predefined character sets

* ``randomstring.LowerLetters`` - lowercase latin letters
* ``randomstring.UpperLetters`` - uppercase latin letters
* ``randomstring.Digits`` - digits
* ``randomstring.Symbols`` - symbols
