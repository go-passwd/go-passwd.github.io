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

passwordValidator := validator.New(validator.MinLength(5), validator.MaxLength(10))
err := passwordValidator.Validate(form.Password)
if err != nil {
  panic(err)
}
~~~

## Validators

### MinLength

Check if password length is not lower that defined length.

~~~go
passwordValidator := validator.New(validator.MinLength(5))
~~~

### MaxLength

Check if password length is not greater that defined length.

~~~go
passwordValidator := validator.New(validator.MaxLength(10))
~~~

### ContainsAtLeast

Count occurrences of a chars and compares it with required value.

~~~go
passwordValidator := validator.New(validator.ContainsAtLeast("abcdefghijklmnopqrstuvwxyz", 5)
~~~

### CommonPassword

Check if password is a common password.

Common password list is based on list created by Mark Burnett: https://xato.net/passwords/more-top-worst-passwords/

~~~go
passwordValidator := validator.New(validator.CommonPassword(nil))
~~~

### Regex

Check if password match regexp pattern.

~~~go
passwordValidator := validator.New(validator.Regex("^\\w+$", nil))
~~~

### Similarity

Check if password is sufficiently different from the attributes.

Attributes can be: user login, email, first name, last name, …

~~~go
passwordValidator := validator.New(validator.Similarity([]string{"username", "username@example.com"}], nil, nil))
~~~
