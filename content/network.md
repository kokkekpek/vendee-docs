---
title: "Network"
date: 2023-06-01T00:00:03Z
draft: false
---

[Vendee](https://github.com/kokkekpek/vendee) using [DApp GraphQL](https://github.com/tonlabs/evernode-ds) endpoints

**Where to get endpoints**

* Copy from [evercloud docs](https://docs.evercloud.dev/products/evercloud/networks-endpoints)
* Use [evercloud.dev](https://www.evercloud.dev)
* Up own server using [evernode-ds](https://github.com/tonlabs/evernode-ds), [everscale-dapp-server](https://github.com/itgoldio/everscale-dapp-server) or [application-server](https://github.com/treeton-org/application-server)

## Configuration

### vendee.config.ts

You can add any network to `vendee.config.ts`

**Example**

```typescript
const config = {
  networks: {
    'se': {
      endpoints: [process.env.SE_ENDPOINT ?? ''],
    },
    'venom testnet': {
      endpoints: process.env.VENOM_TESTNET_ENDPOINTS ? process.env.VENOM_TESTNET_ENDPOINTS.split(',') : ['']
    }
  }
}
```

### .env

You can store your endpoints if `.env` file

**Example**

```env
SE_ENDPOINT="http://localhost:8080"
VENOM_TESTNET_ENDPOINTS="https://gql-testnet.venom.foundation"
```

`.env` under `.gitignone` by default. You can publish your project to git and not be afraid that your personal endpoint will become known to everyone


## SE network

In `vendee.config.ts` you can find `se` network.
This network is used for local testing.
[SE](https://github.com/tonlabs/evernode-se) run and used automatically if you don't set up a network in [tests](/tests) and [scripts](/scripts)
