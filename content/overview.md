---
title: "Overview"
date: 2023-06-01T00:00:00Z
draft: false
---

![cover](/images/overview/cover.svg)

[Vendee](https://github.com/kokkekpek/vendee) is a [TVM-blockhain](https://docs.venom.foundation/learn/tvm/) contract development framework that aims to save development time and investor money

## From author

I tried to do the same things that everyone else does, but a little better.
Imagine that developers can save 5% of their efforts thanks to this.
Ask yourself if you would like the network to grow 5% faster.

## Requirements

![requirements](/images/overview/requirements.svg)

* [Docker](https://www.docker.com) to run [node Simple Emulator](https://github.com/tonlabs/evernode-se)
* [Nodejs](https://nodejs.org)
* [yarn](https://yarnpkg.com) to initialize project

## Features

* Contract compilation
* Testing with [Mocha](https://mochajs.org) and [Chai](https://www.chaijs.com)
* Running scripts
* Giver deployment and using
* Wrapper to manage [Simple Emulator](https://github.com/tonlabs/evernode-se)
* Ability to use contracts without changes on server side and in browser

## Key differences from alternative solutions

* Contracts compiled into TypeScript files. You can use power of types and auto compilation in any IDE
  ![](/images/overview/autocomplition.png)
  
  ![](/images/overview/autocomplition2.png)
* Use contracts in React without changes
  ![](/images/overview/react.png)
* Recompile only changed files. It's safe a lot of time on big project
  ![](/images/overview/recompile.png)
* Giver tools. You do not need to deploy giver outside framework
  ![](/images/overview/giver-deploy.png)
* Interactive console
  ![](/images/overview/menu.gif)
* Integration with [everdev](https://github.com/tonlabs/everdev) allows you to automatically run a local node for testing
* Do not store any private data in main config. Project after initialization ready to `git commit`
* Laconic syntax
