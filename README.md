# <p align="center" style="font-family:courier;font-size:160%"> GOENV </p>
[![Generic badge](https://img.shields.io/badge/LICENSE-MIT-orange.svg)](LICENSE)
[![Generic badge](https://img.shields.io/badge/TESTS-GO-turquoise.svg)](TESTS)


<p align="center">
<img go align="center" style="padding-left: 10px; padding-right: 10px; padding-bottom: 10px;" width="118px" height="118px" src="https://irongeek.gallerycdn.vsassets.io/extensions/irongeek/vscode-env/0.1.0/1602639667760/Microsoft.VisualStudio.Services.Icons.Default" /> 
<img python align="center" style="padding-left: 10px; padding-right: 10px; padding-bottom: 10px;" width="68px"  height="42px" src="https://thypix.com/wp-content/uploads/2020/04/white-arrow-92.png" />
<img c# align="center" style="padding-left: 10px; padding-right: 10px; padding-bottom: 10px;" width="102px"  height="138px" src="https://www.seekpng.com/png/full/412-4126535_go-gopher-go-programming-language-logo-vector.png" />
</p>


---

Library is made to simplify work with environment variables in go.  Library has following methods:

---

- `Init()` - load environment variables from .env file

```go
package main

import "github.com/dangcheg97/goenv"

func init() {
    goenv.Init()
}

func main() {
    ... do stuff
}
```

- `Load()` - load environment variable, and boolean showing wether that variable exists


```go
package main

import (
    "fmt"

    "github.com/dangcheg97/goenv"
)

func main() {
    envar, exists := goenv.Load()
    if !exists {
        fmt.Println("there is no var")
    }
    fmt.Println("here is var", envar)
}
```

- `LoadP()` - load environment variable, but in case var doesn't exist the method panics. Should be used to load critical configuration data.

```go
package main

import (
    "github.com/dangcheg97/goenv"
)

func main() {
    envar := goenv.LoadP()
    ...
}
```

