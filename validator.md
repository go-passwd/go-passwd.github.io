# Password validation library for Go

## Installation

~~~sh
go get -u github.com/go-passwd/validator
~~~

## Usage

~~~go
import "github.com/go-passwd/validator"
~~~

### Validate password

~~~go
import "github.com/go-passwd/passwd/validator"

passwordValidator := passwd.NewValidator(validator.MinLength(5), validator.MaxLength(10))
err := passwordValidator.Validate(form.Password)
if err != nil {
  panic(err)
}
~~~

## Validators

### MinLength

Check if password length is not lower that defined length.

~~~go
passwordValidator := passwd.NewValidator(validator.MinLength(5))
~~~

### MaxLength

Check if password length is not greater that defined length.

~~~go
passwordValidator := passwd.NewValidator(validator.MaxLength(10))
~~~

### ContainsAtLeast

Count occurrences of a chars and compares it with required value.

~~~go
passwordValidator := passwd.NewValidator(validator.ContainsAtLeast("abcdefghijklmnopqrstuvwxyz", 5)
~~~
