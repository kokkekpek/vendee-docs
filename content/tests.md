---
title: "Tests"
date: 2023-06-01T00:00:05Z
draft: false
---

## Run

### Interactive

```shell
npx vendee test
npx vendee test <network>
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

### Non-interactive

```shell
npx vendee test -n <network> [-c] [patterns...]
```

* `patterns` - Optional. Relative paths from tests directory in [glob](https://github.com/isaacs/node-glob) format
  e.g. `**/*deploy.test.ts`
* `-n, --network [network]` - Optional. Network from `vendee.config.ts` e.g `venom testnet`
* `-c, --no-compile` - Optional. Don't compile

[TODO VIDEO]

## From the box

* Use `se` if no network is specified
* Starts [SE](https://github.com/tonlabs/evernode-se) if network `se` is used
* Compile all contracts if `-c` or `--no-compile` is not set

This allows you to run tests immediately after downloading the project from the repository
