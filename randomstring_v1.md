# package randomstring (v1)

~~~go
import "gopkg.in/randomstring.v1"
~~~

[Installation](randomstring_v1.md#installation) | [Overview](randomstring_v1.md#overview) | [API](randomstring_v1.md#api)

## Installation

~~~sh
go get -u gopkg.in/randomstring.v1
~~~

## Overview

Generating a random 20-character string with lower letters, upper letters and digits:

~~~go
s := randomstring.Generate(20)
~~~

Generating a random 20-character string with lower letters:

~~~go
s := randomstring.Generate(20, randomstring.LowerLetters)
~~~

## API

* [Constants](randomstring.md#constants)
* [func Generate](randomstring.md#func-generate)

### Constants

~~~go
// Character sets allowed in a password
const (
	// LowerLetters is a sets of lowercase latin letters
	LowerLetters = "abcdefghijklmnopqrstuvwxyz"

	// UpperLetters is a set of uppercase latin letters
	UpperLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

	// Digits is a set of digits
	Digits = "1234567890"

	// Symbols is a set of symbols
	Symbols = "!\";#$%&'()*+,-./:;<=>?@[]^_`{|}~"
)
~~~

### func Generate

~~~go
func Generate(n uint, baseChars ...string) (*string, error)
~~~

Generate returns a random string of length n consisting of lower letters, upper letters and digitis
