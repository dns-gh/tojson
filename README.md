## tojson package

[![Go Report Card](https://goreportcard.com/badge/github.com/dns-gh/tojson)](https://goreportcard.com/report/github.com/dns-gh/tojson)

[![GoDoc](https://godoc.org/github.com/dns-gh/tojson?status.png)]
(https://godoc.org/github.com/dns-gh/tojson)

Simple wrapper over the encoding/json package to save and load data into a file in json format

## Motivation

Simplify a little bit the code for other projects.

## Installation

- It requires Go language of course. You can set it up by downloading it here: https://golang.org/dl/
- Install it here C:/Go.
- Set your GOPATH, GOROOT and PATH environment variables:

```
export GOROOT=C:/Go
export GOPATH=WORKING_DIR
export PATH=C:/Go/bin:${PATH}
```

- Download and install the package:

```
@working_dir $ go get github.com/dns-gh/tojson/...
@working_dir $ go install github.com/dns-gh/tojson
```

## Usage

```
package main

import "github.com/dns-gh/tojson"

type equipment struct {
	Weapon string `json:"weapon"`
	Shield string `json:"shield"`
}

func main() {
	oldEquipment := &equipment{
		Weapon: "sword",
		Shield: "wooden",
	}
	file := "equipment.json"
	tojson.Save(file, oldEquipment)
	newEquipement := &equipment{}
	tojson.Load(file, newEquipement)
}

```

## Tests

```
@working_dir $ go test -v github.com/dns-gh/tojson
=== RUN   TestSaveLoadJSON
--- PASS: TestSaveLoadJSON (0.00s)
PASS
ok      tojson  0.055s
```

## LICENSE

See included LICENSE file.