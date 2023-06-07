---
title: "Examples"
date: 2023-06-01T00:00:09Z
draft: false
---

# Using examples

* [vendee-example](https://github.com/kokkekpek/vendee-example) - simple example of using Vendee for contract compilation, testing and deployment published as [npm package](https://www.npmjs.com/package/vendee-example)
* [vendee-example-web](https://github.com/kokkekpek/vendee-example-web) - simple React example of using [vendee-example](https://github.com/kokkekpek/vendee-example) published at [example.vendee.top](https://example.vendee.top)

## Tools
* [vendee-keys](https://github.com/kokkekpek/vendee-keys) - methods of working with key pair

## Basic code examples

### Deploy

```typescript
await (new Counter())
  .deploy(0.1 * B, { number: INITIAL_VALUE })
```

### Run method

```typescript
// Contract initialization and deploy
const counter = new Counter()
await counter.deploy(0.1 * B, { number: INITIAL_VALUE })

// Run
const getCountOut = await counter.run.getCount()
```

### Call method

```typescript
// Contract initialization and deploy
const counter = new Counter()
await counter.deploy(0.1 * B, { number: INITIAL_VALUE })

// Call
await counter.call.selfAdd({ number: 1 })
```

### Call method from wallet

```typescript
// Contract initialization and deploy
const counter = new Counter()
await counter.deploy(B, { number: INITIAL_VALUE })
const wallet = new SafeMultisigWallet()
const keys = await generateRandomKeyPair()
await wallet.deploy(0.2 * B, { owners: [x0(keys.public)], reqConfirms: 1 })

// Call
await wallet.call.sendTransaction({
  dest: await counter.address(),
  value: 0.1 * B,
  bounce: true,
  flags: 0,
  payload: await counter.payload.add({
    number: INITIAL_VALUE
  })
}, keys)
await counter.wait()
```
