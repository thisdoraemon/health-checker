# Health Checker

## Overview

Healthchecker is a simple command-line tool designed to check whether a website is running or down. It uses the net package in Go to establish a TCP connection to the specified domain and port. The result of the check includes information about the status of the website and, if applicable, details about the connection.

## Installation

Make sure you have Go installed on your system. You can install Healthchecker using the following steps:
```bash
git clone https://github.com/thisdoraemon/health-checker
```

## Usage
```bash
go run . --domain <website_domain> [--port <port_number>]
```
- `--domain or -d`: Specifies the domain name of the website to check (required).

- `--port or -p`: Specifies the port number to check. If not provided, the default is set to port 80.

### Example Usage
```bash
go run . --domain google.com
```

```bash
go run . --domain amazon.com --port 80
```

## Code Structure
### Main Program (main.go)

The main program sets up a command-line interface using the [urfave/cli](https://github.com/urfave/cli/tree/main/docs/v2) package. It defines flags for the domain and port and executes the Check function based on the provided inputs.
```go
package main

import (
	"fmt"
	"github.com/urfave/cli/v2"
	"log"
	"os"
)

// ... (main function and CLI setup)
```
### Health Checking Logic (check.go)

The Check function in check.go is responsible for establishing a TCP connection to the specified domain and port. It returns a status message indicating whether the website is up or down.
```go
package main

import (
	"fmt"
	"net"
	"time"
)

// Check establishes a TCP connection to the specified destination and port
func Check(destination string, port string) string {
	// ... (connection setup and status determination)
}
```

## Notes

- The connection timeout is set to 5 seconds.
- The connection timeout is set to 5 seconds.

## Error Handling

The tool provides informative error messages if the website is unreachable or if an error occurs during the connection attempt.

## License

This tool is open-source and distributed under the [MIT License](https://github.com/thisdoraemon/health-checker/blob/main/LICENSE).
