---
title: " Giver"
date: 2023-06-01T00:00:04Z
draft: false
---

## View

### Interactive

```shell
npx vendee giver
npx vendee giver <network>
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

### Non-interactive

```shell
npx vendee giver <network> info
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

## Send

### Interactive

```shell
npx vendee giver
npx vendee giver <network>
npx vendee giver <network> send
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

### Non-interactive

```shell
vendee giver -t <to> -v <value> <network> send
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`
* `-t, --to <to>` - address to send coins e.g. `0:0000000000000000000000000000000000000000000000000000000000000000`
* `-v, --value <value>` - coins value e.g. `0.1`

[TODO VIDEO]

## Deploy

### Interactive

```shell
npx vendee giver
npx vendee giver <network>
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

### Non-interactive

```shell
vendee giver <network> deploy
```

* `network` - network from `vendee.config.ts` e.g `venom testnet`

[TODO VIDEO]

## Configuration

### vendee.config.ts

You can set up giver in `vendee.config.ts`

**Example**

```typescript
const config = {
  networks: {
    'venom testnet': {
      endpoints: process.env.VENOM_TESTNET_ENDPOINTS ? process.env.VENOM_TESTNET_ENDPOINTS.split(',') : [''],
      giver: 'safeMultiSigWallet',
      keys: {
        name: 'myGiver',
        file: ''
      }
    }
  }
}
```

* `giver` - Optional. Type of giver e.g. `safeMultiSigWallet`. Available
  values: `v2.se`, `v3.se`, `safeMultiSigWallet.se`, `v2`, `v3`, `safeMultiSigWallet`.
  It is recommended to use `safeMultiSigWallet` for all networks except `se`. Default is `v3.se`
* `keys.name` - Optional. Generate `<keys directory>/<name>.json` if file doesn't exist and is used for the
  giver e.g. `myGiver`. Default is `''`
* `keys.file` - Optional. Read key pair from file e.g. `/home/user/keys/giver.json`. Default is `''`

### SE givers

`v2.se`, `v3.se`, `safeMultiSigWallet.se` don't require `keys`. It
used [hardcoded keys](https://github.com/tonlabs/evernode-se/tree/master/contracts)

### Keys

* Set `keys.name` if you want to generate and read key pair from `<keys directory>/<name>.json`
* Set `keys.file` if you want to read key pair by absolute path
* Make `keys.name` and `keys.file` empty if you want to generate and read key pair
  from `<keys directory>/<network name>.giver.json`
