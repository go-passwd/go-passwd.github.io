# Go random string generator

## Installation

~~~sh
go get -u github.com/go-passwd/randomstring
~~~

## Usage

~~~go
import "github.com/go-passwd/randomstring"
~~~

### Generate random string

Generating a random 20-character string with lower letters, upper letters and digits:

~~~go
s := randomstring.Generate(20)
~~~

Generating a random 20-character string with lower letters:

~~~go
s := randomstring.Generate(20, randomstring.LowerLetters)
~~~

## Predefined character sets

* ``randomstring.LowerLetters`` - lowercase latin letters
* ``randomstring.UpperLetters`` - uppercase latin letters
* ``randomstring.Digits`` - digits
* ``randomstring.Symbols`` - symbols
