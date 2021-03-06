# bcrypt-tool

bcrypt-tool is a dandy CLI tool for generating and matching bcrypt hashes

[![Go Report Card](https://goreportcard.com/badge/github.com/shoenig/bcrypt-tool)](https://goreportcard.com/report/github.com/shoenig/bcrypt-tool) [![Build Status](https://travis-ci.org/shoenig/bcrypt-tool.svg?branch=master)](https://travis-ci.org/shoenig/bcrypt-tool) [![GoDoc](https://godoc.org/github.com/shoenig/bcrypt-tool?status.svg)](https://godoc.org/github.com/shoenig/bcrypt-tool) [![License](https://img.shields.io/github/license/shoenig/bcrypt-tool.svg?style=flat-square)](LICENSE)

### Installation
    `go get "github.com/shoenig/bcrypt-tool"`

### Examples

#### Generate Hash from a Password
    `bcrypt-tool hash p4ssw0rd`
    
#### Generate Hash from a Password with Cost
    `bcrypt-tool hash p4ssw0rd 31`
    
#### Determine if Password matches Hash
    `bcrypt-tool match p4ssw0rd $2a$10$nWFwjoFo4zhyVosdYMb6XOxZqlVB9Bk0TzOvmuo16oIwMZJXkpanW`
    
    note: depending on your shell, you may need to escape the $ characters

#### Determine Cost of Hash
    `bcrypt-tool cost $2a$10$nWFwjoFo4zhyVosdYMb6XOxZqlVB9Bk0TzOvmuo16oIwMZJXkpanW`
    
    note: depending on your shell, you may need to escape the $ characters

### Usage
    `bcrypt-tool [action] parameter ...`

#### Actions

- `hash  [password] <cost>` Use bcrypt to generate a hash given password and optional cost (4-31)

- `match [password] [hash]` Use bcrypt to check if a password matches a hash

- `cost  [hash]` Use bcrypt to determine the cost of a hash (4-31)
