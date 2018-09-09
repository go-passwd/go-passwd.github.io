# package randomstring

~~~go
import "github.com/go-passwd/randomstring"
~~~

[Installation](randomstring.md#installation) | [Overview](randomstring.md#overview) | [API](randomstring.md#api)

## Installation

~~~sh
go get -u github.com/go-passwd/randomstring
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
* [type CharsetRuleFunc](randomstring.md#type-charsetrulefunc)
  * [func NewExcludeCharset](randomstring.md#func-newexcludecharset)
  * [func NewIncludeCharset](randomstring.md#func-newincludecharset)
* [type GenerateRuleFunc](randomstring.md#type-generaterulefunc)
  * [func NewSimpleGenerate](randomstring.md#func-newsimplegenerate)
* [type Generator](randomstring.md#type-generator)
  * [func New](randomstring.md#func-new)
  * [func (*Generator) Generate](randomstring.md#func-generator-generate)
* [type LengthRuleFunc](randomstring.md#type-lengthrulefunc)
  * [func NewLength](randomstring.md#func-newlength)
  * [func NewLengthRange](randomstring.md#func-newlengthrange)
* [type OutputRuleFunc](randomstring.md#type-outputrulefunc)
  * [func NewBeginWith](randomstring.md#func-newbeginwith)
  * [func NewNoDuplicateCharacters](randomstring.md#func-newnoduplicatecharacters)
  * [func NewNoSequentialCharacters](randomstring.md#func-newnosequentialcharacters)

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

// Character sets disallowed
const (
	// Similar is a set of letters, digits and symbols which are looks similar
	Similar = "il1Lo0O"

	// Ambigous is a set of sumbols which are ambigous
	Ambigous = "{}[]()/\\'\"`~,;:.<>"
)
~~~

### func Generate

~~~go
func Generate(n uint, baseChars ...string) (*string, error)
~~~

Generate returns a random string of length n consisting of lower letters, upper letters and digitis

### type CharsetRuleFunc

CharsetRuleFunc modify a charset and returns it

~~~go
type CharsetRuleFunc func(charset string) string
~~~

### func NewExcludeCharset

~~~go
func NewExcludeCharset(chars string) CharsetRuleFunc
~~~

NewExcludeCharset returns a new charset rule func which removes chars from charset

### func NewIncludeCharset

~~~go
func NewIncludeCharset(chars string) CharsetRuleFunc
~~~

NewIncludeCharset returns a new charset rule func which add chars to charset

### type GenerateRuleFunc

GenerateRuleFunc generates a new string based on: charset, length and output rules

~~~go
type GenerateRuleFunc func(charset string, length uint, outputRules []OutputRuleFunc) *string
~~~

### func NewSimpleGenerate

~~~go
func NewSimpleGenerate() GenerateRuleFunc
~~~

NewSimpleGenerate returns a new generate rule func with simple random string generator

### type Generator

Generator is a advanced random string generator based on rules

~~~go
type Generator struct {
    // contains filtered or unexported fields
}
~~~

### func New

~~~go
func New(rules ...interface{}) (*Generator, error)
~~~

New creates a new Generator generator

### func (*Generator) Generate

~~~go
func (g *Generator) Generate() (*string, error)
~~~

Generate generates a new random string based of rules

### type LengthRuleFunc

LengthRuleFunc returns a length of a string to generate

~~~go
type LengthRuleFunc func() uint
~~~

### func NewLength

~~~go
func NewLength(n uint) LengthRuleFunc
~~~

NewLength returns a new length rule func which sets string length to n

### func NewLengthRange

~~~go
func NewLengthRange(min, max uint) LengthRuleFunc
~~~

NewLengthRange returns a new length rule func which sets string length to length between min and max

### type OutputRuleFunc

OutputRuleFunc checks if the string meets the rule

~~~go
type OutputRuleFunc func(str []byte, c byte) bool
~~~

### func NewBeginWith

~~~go
func NewBeginWith(letters string) OutputRuleFunc
~~~

NewBeginWith returns a new output rule func that checks if str does start with a one of letters

### func NewNoDuplicateCharacters

~~~go
func NewNoDuplicateCharacters() OutputRuleFunc
~~~

NewNoDuplicateCharacters returns a new output rule func that checks if str doesn't have c

### func NewNoSequentialCharacters

~~~go
func NewNoSequentialCharacters(n uint) OutputRuleFunc
~~~

NewNoSequentialCharacters returns new output rule func that checks if str doesn't have n sequentials characters
