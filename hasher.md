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
hasher := hasher.New(hasher.TypeSHA512)
hasher.SetPassword(plainTextPassword)
hashedPassword := hasher.String()
~~~

## Hashers

### PlainHasher

Stored password as plain text.

~~~go
passwordHasher := hasher.New(hasher.TypePlain)
~~~

### MD5Hasher

Store password as MD5 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeMD5)
~~~

### SHA1Hasher

Store password as SHA-1 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA1)
~~~

### SHA224Hasher

Store password as SHA-224 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA224)
~~~

### SHA256Hasher

Store password as SHA-256 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA256)
~~~

### SHA384Hasher

Store password as SHA-384 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA384()
~~~

### SHA512Hasher

Store password as SHA-512 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA512)
~~~

### SHA512_224Hasher

Store password as SHA-512/224 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA512_224)
~~~

### SHA512_256Hasher

Store password as SHA-512/256 hash.

~~~go
passwordHasher := hasher.New(hasher.TypeSHA512_256)
~~~
