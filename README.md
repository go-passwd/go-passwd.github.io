# Password library for Go

## TOC

* [go-passwd/randomstring](randomstring.md) random string generator
* [go-passwd/validator](validator.md) password validation library
* [go-passwd/hasher](hasher.md) password hasher library

## Installation

~~~sh
go get -u github.com/go-passwd/passwd
~~~

## Usage

~~~go
import "github.com/go-passwd/passwd"
~~~

### Check password

~~~go
correct, err := passwd.Check(form.Password, db.Password)
~~~

where

* ``form.Password`` is a password from form
* ``db.Password`` is a password from DB
