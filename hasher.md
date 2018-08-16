# Password hasher library for Go

## Installation

~~~sh
go get -u github.com/go-passwd/hasher
~~~

## Usage

~~~go
import "github.com/go-passwd/hasher"
~~~

### Hash password

~~~go
hasher := passwd.NewSHA512Hasher()
hasher.SetPassword(plainTextPassword)
hashedPassword := hasher.String()
~~~

## Hashers

### PlainHasher

Stored password as plain text.

~~~go
passwordHasher := passwd.NewPlainHasher()
~~~

### MD5Hasher

Store password as MD5 hash.

~~~go
passwordHasher := passwd.NewMD5Hasher()
~~~

### SHA1Hasher

Store password as SHA-1 hash.

~~~go
passwordHasher := passwd.NewSHA1Hasher()
~~~

### SHA224Hasher

Store password as SHA-224 hash.

~~~go
passwordHasher := passwd.NewSHA224Hasher()
~~~

### SHA256Hasher

Store password as SHA-256 hash.

~~~go
passwordHasher := passwd.NewSHA256Hasher()
~~~

### SHA384Hasher

Store password as SHA-384 hash.

~~~go
passwordHasher := passwd.NewSHA384Hasher()
~~~

### SHA512Hasher

Store password as SHA-512 hash.

~~~go
passwordHasher := passwd.NewSHA512Hasher()
~~~

### SHA512_224Hasher

Store password as SHA-512/224 hash.

~~~go
passwordHasher := passwd.NewSHA512_224Hasher()
~~~

### SHA512_256Hasher

Store password as SHA-512/256 hash.

~~~go
passwordHasher := passwd.NewSHA512_256Hasher()
~~~