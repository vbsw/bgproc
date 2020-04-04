# bgproc

[![GoDoc](https://godoc.org/github.com/vbsw/bgproc?status.svg)](https://godoc.org/github.com/vbsw/bgproc) [![Go Report Card](https://goreportcard.com/badge/github.com/vbsw/bgproc)](https://goreportcard.com/report/github.com/vbsw/bgproc) [![Stability: Experimental](https://masterminds.github.io/stability/experimental.svg)](https://masterminds.github.io/stability/experimental.html)

## About
bgproc is a package for Go. bgproc starts a process in "background", i.e. a from command line detached process. bgproc is published on <https://github.com/vbsw/bgproc>.

## Copyright
Copyright 2020, Vitali Baumtrok (vbsw@mailbox.org).

bgproc is distributed under the Boost Software License, version 1.0. (See accompanying file LICENSE or copy at http://www.boost.org/LICENSE_1_0.txt)

bgproc is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the Boost Software License for more details.

## Example

	import (
		"fmt"
		"github.com/vbsw/bgproc"
		"os"
		"path/filepath"
	)

	func main() {
		if len(os.Args) > 1 && os.Args == "--background" {
			progName, err := filepath.Abs(os.Args[0])

			if err == nil {
				proc := bgproc.New(progName)
				err = proc.Start()
			}
			if err != nil {
				fmt.Println(err.Error())
			}
		}
	}

## References

- https://golang.org/doc/install
- https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
