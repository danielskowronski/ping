# ping

Ping using ICMP echo - adapted from golang test code

#### Demo
```go
package main

import (
	"log"
	"strconv"
	"github.com/danielskowronski/pingo"
)


func main() {
	targets := []string{"0.0.0.0", "349.156.65.204", "149.156.65.204", "149.156.65.255", "149.156.65.177", "250.156.65.177", "8.8.8.8", "github.com"}
	for _, v := range targets {
		pingable, err := pingo.Ping(v, 100)
		if err!=nil{
			log.Print("ERROR! "+v+" "+err.Error())
		} else {
			log.Print(v+" pingability: "+strconv.FormatBool(pingable))
		}
	}
}
```