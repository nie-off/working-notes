---
{"publish":true,"cssclasses":""}
---

So the overall goal for me is to get some hands on malware development to understand their working and by this the potential detection steps that can be inferred. I start with ransomware, but should later add a categorization for myself to have a good overview over other malware types (#TODO). To make it a little more interesting for me, I want to write it in a programming language, that I haven't touched before, and I have a good candidate as I heard from multiple people that the one is suppose to make much fun - which is Go.

So, today I started installing the Go compiler on my Windows 11 machine, actually also inside the WSL to see for any difference. So far, the hello world example compiled on both endings. 
Apparently, Go projects and thus Go modules need to be initialized by the command `go mod init <module_path>` where the Go doc encourages one to use the code's repository that is reachable for others to import it as a dependency. As I have no intentions of publishing my short hello world example, I go for "example" as the module path. After this, I started with my first hello world source code file, which I name verbosely "example.go".  
```go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello World!")
}
```
I compiled them with
```
GOOS=linux GOARCH=amd64 go build -o example example.go
GOOS=windows GOARCH=amd64 go build -o example.exe example.go
```

I can run with `go run example.go`, but the sweet VS Code Go plugin makes it easy to hit a keyboard shortcut instead to make presumably the same behind the scenes.

The next step is to get familiar with opening files, later then to copying the content to a new file, but this version encrypted. I am planning for using the old Vigenere chiffre, so that I can later use word statistical analysis to hopefully decrypt it without a key. Let's see if this works out how I imagine it.