+++
title = "Go fundamentials"
outputs = ["Reveal"]
+++

# Go fundamentials

---

{{% section %}}

## Overview

* Young
  * started September 2007 at Google
  * first public announced November 2009
  * 1.0 March 2012
* Large [standard library](https://pkg.go.dev/std) + golang.org/x/mod + many open source packages
  * [`http` client and server](https://pkg.go.dev/net/http@go1.18.1), [html/template](https://pkg.go.dev/html/template@go1.18.1), [encoding/json](https://pkg.go.dev/encoding/json@go1.18.1)

---

* Package system
* Strong statically typing
* Compiled
* Statically linked binaries by default
* Build in testing tools

---

* Fewer keywords, e.g. only one loop, `for`
* A `func` can return 0 - n values, common a value and an err
* Every var must be used (expect blank `_`)
* Variables are only available in the scope in which they were declared
* C on steroides

{{% /section %}}

---

## Popular software written in Go

* [Docker](https://www.docker.com/), a set of tools for deploying Linux containers
* [Hugo](https://gohugo.io/), a static site generator<sup>1</sup>
* [InfluxDB](https://www.influxdata.com/), an open source time series database
* [Mattermost](https://mattermost.com/), a teamchat system
* [GitHub CLI](https://cli.github.com/)

{{% fragment %}}
<sup>1</sup> This presentation is build with [Hugo](https://gohugo.io/) and the [reveal.js](https://revealjs.com/) theme [reveal-hugo](https://github.com/dzello/reveal-hugo)
{{% /fragment %}}

---

## Types

Simple types linke `string`, `int`, `bool`, `array`, `slice`  
Complex types and it's functions like [`net.IP`](https://cs.opensource.google/go/go/+/refs/tags/go1.18.1:src/net/ip.go;l=35), [`time.Duration`](https://cs.opensource.google/go/go/+/refs/tags/go1.18.1:src/time/time.go;l=589)  
Collection of fields (`struct`) like [`url.URL`](https://cs.opensource.google/go/go/+/refs/tags/go1.18.1:src/net/url/url.go;l=358-369)

Explicit conversion between types required!  

https://go.dev/tour/moretypes/1

---

## Go command

```shell
# module maintenance
go mod
# initialize new module in current directory
go mod init github.com/t3easy/hello-go
# add missing and remove unused modules
go mod tidy
# add dependencies to current module and install them
go get github.com/spf13/cobra@latest
# test packages
go test ./...
# compile packages and dependencies
go build
```

https://pkg.go.dev/cmd/go

---

## Packages

Every Go program is made up of packages.  
Programs start running in package `main`.  
Standard lib, internal and external packages must be imported.

---

## Go module

Every module has a name, preferable the repo url

```shell
go mod init github.com/t3easy/hello-go
```

* `go.mod` - Module name, Go version and dependencies  
  like `composer.json`  
* `go.sum` - Checksum of direct and indirect dependencies  
  like `composer.lock`  

<small>
As of Go 1.13, the go command by default downloads and authenticates modules
using the Go module mirror and Go checksum database run by Google. 
</small>

---

{{% section %}}

## Setup dev system

### Install Go  
*  As package  
   https://go.dev/dl/
*  With Homebrew
   ```shell
   brew install go
   ```

---

### IDEs
*  [Visual Studio Code](https://code.visualstudio.com/)  
   \+ [Go for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=golang.Go)
*  [GoLand](https://www.jetbrains.com/go/) from JetBrains

{{% /section %}}

---

## Hello go!

https://github.com/t3easy/hello-go

---

## Links

* https://go.dev/tour/list
* https://pkg.go.dev/
* https://github.com/spf13/cobra
* https://github.com/spf13/viper
* https://github.com/golang-standards/project-layout

---

## Thanks for attention
