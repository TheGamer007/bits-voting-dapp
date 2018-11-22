---
title: Quick Start
weight: 2
---

The following instructions assume you have setup the [NodeJS](https://nodejs.org/en/) development environment, including the `npm` package manager. While originally written for Ubuntu, they should be able to work without changes on any Linux / Mac, and with only minor changes on Windows.

#### Setup

Install the [Truffle](https://github.com/trufflesuite/truffle) framework globally:

```shell
npm install -g truffle
```

Then install [Ganache](http://truffleframework.com/ganache/) by following the instructions in [the quickstart](https://truffleframework.com/docs/ganache/quickstart). We now have the resources necessary to generate a local blockchain network with ease.

Finally, clone this repo and install the necessary node modules:

```shell
git clone https://github.com/TheGamer007/bits-voting-dapp.git
cd bits-voting-dapp
npm install
```

To get the application running, open up a new terminal tab (navigate to the same directory):

```shell
truffle develop
> compile
> migrate
```

This creates a new local blockchain network, pre-loaded with 10 accounts, each with 100 ETH. Then it compiles and loads our contracts onto this network.

Next, go back to your previous tab and run:

```shell
npm run dev
```
This hosts our web application locally on port `8080`. So our Voter Dashboard can be accessed at `localhost:8080/`, while the Admin Dashboard is at `localhost:8080/admin.html`.

The application will not have any candidates or posts populated by default, so you will first have to add some via the Admin Dashboard before being able to vote.
