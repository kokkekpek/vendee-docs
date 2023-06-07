---
title: "Compilation"
date: 2023-06-01T00:00:02Z
draft: false
---

## Compile

### Interactive

```shell
npx vendee
```

![recompilation](/images/compile-interactive.gif)

### Non-interactive

```shell
npx vendee compile [options]
```

Options:

* `-a, --all` - compile all contracts
* `-h, --help` - display help for command

![recompilation](/images/compile.gif)

## Recompilation

Recompile only changed files. If you change one file, then only that file, or those that import it, will be recompiled

![recompilation](/images/recompilation.gif)

## Artifacts

* `*.tvc` - assembler code. You can use it with [tonos-cli](https://github.com/tonlabs/tonos-cli)
* `*.abi.json` - contract ABI. You can use it with [Ever SDK](https://github.com/tonlabs/ever-sdk-js)
  and [tonos-cli](https://github.com/tonlabs/tonos-cli)
* `*Contract.ts` - contract abi and code in one TypeScript constant. You can use it
  with [Ever SDK](https://github.com/tonlabs/ever-sdk-js)
* `*.ts` - Vendee TypeScript contract class. You can use it with [Vendee](https://github.com/kokkekpek/vendee) on server
  side or web side

Compilation create `index.ts` in build directory. This file using to publish npm package

## Clean

Remove compilation artifacts and cache directory

### Interactive

```shell
npx vendee
```

![clean-interactive](/images/clean-interactive.gif)

## Non-interactive

```shell
npx vendee clean
```

![clean](/images/clean.gif)

## Configuration

```typescript
const config = {
  compile: {
    compiler: 'latest',
    linker: 'latest',
    include: ['**/*.tsol', '**/*.sol'],
    exclude: ['**/interface/*', '**/interfaces/*']
  }
}
```

* `compiler` - [TON-Solidity-Compiler](https://github.com/tonlabs/TON-Solidity-Compiler) version. To view all available
  versions run in terminal: `npx everdev sol version`. It is recommended to specify the version. Default is `latest`.
* `linker` - [TVM-linker](https://github.com/tonlabs/TVM-linker) version. Default is `latest`. To view all available
  versions run in terminal: `npx everdev sol version`. It is recommended to specify the version. Default is `latest`.
* `include` - list of source files for compilation in contract directory in [glob](https://github.com/isaacs/node-glob)
  format e.g. `['*.tsol']`. Default is `['**/*.tsol', '**/*.sol']`.
* `exclude` - list of source files excluded from compilation in [glob](https://github.com/isaacs/node-glob) format
  e.g. `['**/abstract/*']`. Default is `['**/interface/*', '**/interfaces/*']`.
