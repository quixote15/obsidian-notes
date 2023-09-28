---
share: true
---


[[GoLang]]

Version:
`go version`

Env:
`go env`

***Most of the time we will be using this command in development***
Run a go file:
`go run file.go`

Build:
`go build file.go`

Build for windows:
`GOOS=windows go build file.go`


What if I want to make my go binary available globally in my machine ?

Just run 
`go install`

Every time we run the go install the binary goes to the /bin folder and is available globally in any CLI.

Ref:
https://www.youtube.com/watch?v=LIcKvaf08to&list=PL5aY_NrL1rjucQqO21QH8KclsLDYu1BIg&index=2
