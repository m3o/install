# M3O Install

This repo serves as the location for install guides and scripts for M3O

## Contents

- [cli](cli) install script for the [m3o-cli](https://github.com/m3o/m3o-cli)
- [micro](micro) - install script for [micro](https://github.com/micro/micro) (includes m3o specific setup)

## Usage

Install the m3o cli

```sh
## follow the instructions
curl -fssl https://install.m3o.com/cli | /bin/bash
```

Install the micro cli

```sh
## follow the instructions
curl -fssl https://install.m3o.com/micro | /bin/bash
```

Install the m3o js client

```bash
npm install m3o
```

To use the helloworld service

```js
const { HelloworldService } = require("m3o/helloworld");

const helloworldService = new HelloworldService(process.env.M3O_API_TOKEN);

// Call returns a personalised "Hello $name" response
async function callTheHelloworldService() {
  const rsp = await helloworldService.call({
    name: "Alice",
  });
  console.log(rsp);
}

callTheHelloworldService();
```

Install the m3o go client

```bash
go get go.m3o.com
```

To use the helloworld service

```go
package main

import (
    "fmt"
    "os"

    "go.m3o.com/helloworld"
)

function main() {
    helloworldService := helloworld.NewHelloworldService(os.Getenv("M3O_API_TOKEN"))

    rsp, err := helloworldService.Call(&helloworld.CallRequest{
	      "Name": "Alice",
    })

    fmt.Println(rsp.Message)
}
```
