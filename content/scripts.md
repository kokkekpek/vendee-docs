---
title: "Scripts"
date: 2023-06-01T00:00:06Z
draft: false
---

## Run

### Interactive

```shell
npx vendee run
npx vendee run <network>
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

![run-interactive](/images/scripts/run-interactive.gif)

### Non-interactive

```shell
npx vendee run -n <network> [-c] <script>
```

* `script` - Optional. Relative paths from scripts directory e.g. `deploy/wallet.ts`
* `-n, --network [network]` - Optional. Network from `vendee.config.ts` e.g `venom testnet`
* `-c, --no-compile` - Optional. Don't compile

![run](/images/scripts/run.gif)

## From the box

* You can do not write `./` at start of file and `.ts` at end of file. `npx vendee run deploy`
  and `npx vendee run ./deploy.ts` is same
* Use `se` if no network is specified
* Starts [SE](https://github.com/tonlabs/evernode-se) if network `se` is used
* Compile all contracts if `-c` or `--no-compile` is not set

This allows you to run script immediately after downloading the project from the repository
