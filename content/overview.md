---
title: "Overview"
date: 2023-06-01T00:00:00Z
draft: false
---

![cover](/images/cover.svg)

[Vendee](https://github.com/kokkekpek/vendee) is a [TVM-blockhain](https://docs.venom.foundation/learn/tvm/) contract development framework that aims to save development time and investor money

## From author

I tried to do the same things that everyone else does, but a little better.
Imagine that developers can save 5% of their efforts thanks to this.
Ask yourself if you would like the network to grow 5% faster.

## Requirements

![requirements](/images/requirements.svg)

* [Docker](https://www.docker.com) to run [node Simple Emulator](https://github.com/tonlabs/evernode-se)
* [Nodejs](https://nodejs.org)
* [yarn](https://yarnpkg.com) to initialize project

## Features

* Contract compilation
* Testing with [Mocha](https://mochajs.org) and [Chai](https://www.chaijs.com)
* Running deployment scripts
* Giver deployment and using
* Wrapper to manage [Simple Emulator](https://github.com/tonlabs/evernode-se)
* Ability to use contracts without changes on server side and in browser
* Interactive console

## Key differences from alternative solutions

* Contracts compiled into TypeScript files. You can use power of types and auto compilation in any IDE
  ![](/images/overview/autocomplition.png)
  
  ![](/images/overview/autocomplition2.png)
* You can use TypeScript contract files in React without changes
  ![](/images/overview/react.png)
* Recompile only changed files. It's safe 30min/day on big project
* Integration with [everdev](https://github.com/tonlabs/everdev) allows you to automatically run a local node for testing
* Do not store any private data in main config. Project after initialization ready to `git commit`
* You do not need to deploy giver outside framework. Framework already have giver deployment script
* Interactive console. You do not need Remember commands or script names
* Laconic syntax
