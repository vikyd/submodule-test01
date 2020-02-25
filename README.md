# submodule-test01

Example of Golang multiple modules in single repository.

# Usage example

```sh
# get normal module
go get -v github.com/vikyd/submodule01

# get sub module v2
go get -v github.com/vikyd/submodule01/v2

# get sub module `module01`
go get -v github.com/vikyd/submodule01/module01

# get sub module `module01` v2
go get -v github.com/vikyd/submodule01/module01/v2
```

use these modules in go file:

```go
package main

import (
	"fmt"

	"github.com/vikyd/submodule01"
	"github.com/vikyd/submodule01/module01"
	module01v2 "github.com/vikyd/submodule01/module01/v2"
	submodule01v2 "github.com/vikyd/submodule01/v2"
)

func main() {
	fmt.Println("vim-go")
	submodule01.F01()
	submodule01v2.F01()
	module01.F02()
	module01v2.F02()
}
```

prints:

```
F01
F01 v2
F02 in module: github.com/vikyd/submodule01/module01
F02 in module: github.com/vikyd/submodule01/module01/v2 , yeah v2
```

or clone this repository: https://github.com/vikyd/import-submodule , and run the `main.go` file .
