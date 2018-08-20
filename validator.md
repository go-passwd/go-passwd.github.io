# package validator

~~~go
import "github.com/go-passwd/validator"
~~~

## Installation

~~~sh
go get -u github.com/go-passwd/validator
~~~

## Overview

Password validation library for Go

Validate password:

~~~go
import "github.com/go-passwd/passwd/validator"

passwordValidator := validator.New(validator.MinLength(5), validator.MaxLength(10))
err := passwordValidator.Validate(form.Password)
if err != nil {
  panic(err)
}
~~~

## API

* [type ValidateFunc](validator.md#type-validatefunc)
  * [func CommonPassword](validator.md#func-commonpassword)
  * [func ContainsAtLeast](validator.md#func-containsatleast)
  * [func MaxLength](validator.md#func-maxlength)
  * [func MinLength](validator.md#func-minlength)
  * [func Noop](validator.md#func-noop)
  * [func Regex](validator.md#func-regex)
  * [func Similarity](validator.md#func-similarity)
* [type Validator](validator.md#type-validator)
  * [func New](validator.md#func-new)
  * [func (*Validator) Validate](validator.md#func-validator-validate)

### type ValidateFunc

~~~go
type ValidateFunc func(password string) error
~~~

ValidateFunc defines a function to validate 

### func CommonPassword

~~~go
func CommonPassword(customError error) ValidateFunc
~~~

CommonPassword returns ValidateFunc that validate whether the password is a common password.

The password is rejected if it occurs in a provided list created by Mark Burnett: https://xato.net/passwords/more-top-worst-passwords/ 

### func ContainsAtLeast

~~~go
func ContainsAtLeast(chars string, occurrences int, customError error) ValidateFunc
~~~

ContainsAtLeast returns a ValidateFunc that count occurrences of a chars and compares it with required value 
 
### func MaxLength

~~~go
func MaxLength(length int, customError error) ValidateFunc
~~~

MaxLength returns a ValidateFunc that check if password length is not greater that "length"

### func MinLength

~~~go
func MinLength(length int, customError error) ValidateFunc
~~~

MinLength returns a ValidateFunc that check if password length is not lower that "length" 

### func Noop

~~~go
func Noop(customError error) ValidateFunc
~~~

Noop returns a ValidateFunc that always return custom error

### func Regex

~~~go
func Regex(pattern string, customError error) ValidateFunc
~~~

Regex returns ValidateFunc that check if password match regexp pattern 

### func Similarity

~~~go
func Similarity(attributes []string, maxSimilarity *float64, customError error) ValidateFunc
~~~

Similarity returns ValidateFunc that validate whether the password is sufficiently different from the attributes

Attributes can be: user login, email, first name, last name, …

### type Validator

~~~go
type Validator []ValidateFunc
~~~

Validator represents set of password validators

### func New

~~~go
func New(vfunc ...ValidateFunc) *Validator
~~~

New return new instance of Validator

### func (*Validator) Validate

~~~go
func (v *Validator) Validate(password string) error
~~~

Validate the password
