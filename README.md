# Password library for Go

## TOC

* [random string generator](randomstring.md)
* [password validation library](validator.md)
* [password hasher library](hasher.md)

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
