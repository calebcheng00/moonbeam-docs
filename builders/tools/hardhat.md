---
title: Hardhat
description: Learn how to configure Hardhat to add a local Moonbeam development node and the Moonbase Alpha TestNet as networks for testing and deploying Solidity smart contracts.
---

# Hardhat

![Hardhat Create Project](/images/hardhat/hardhat-banner.png)

## Introduction

[Hardhat](https://hardhat.org/) is a popular development framework for compiling, testing, and deploying Solidity smart contracts. Since Moonbeam is Ethereum compatible, with a few lines of extra configuration, you can use Hardhat as you normally would to develop on Moonbeam.

## Configure Hardhat to Connect to Moonbeam

To get started with Hardhat you must have an npm project. If you do not yet have one, to create one you can run:

```
npm init
```

Once you have a npm project, install Hardhat:

```
npm install hardhat
```

Then to create a Hardhat config file in your project, run:

```
npx hardhat
```

In your `hardhat.config.js` file, add network configurations for a Moonbeam development node and the Moonbase Alpha TestNet:

```javascript
// Moonbeam Development Node Private Key
const privateKeyDev =
   '99B3C12287537E38C90A9219D4CB074A89A16E9CDB20BF85728EBD97C343E342';
// Moonbase Alpha Private Key
const privateKeyMoonbase = "YOUR-PRIVATE-KEY-HERE";

module.exports = {
   networks: {
      // Moonbeam Development Node
      dev: {
        url: 'http://localhost:9933/',
        chainId: 1281,
        accounts: [privateKeyDev]
      },
      // Moonbase Alpha TestNet
      moonbase: {
        url: `https://rpc.testnet.moonbeam.network`,
        chainId: 1287,
        accounts: [privateKeyMoonbase]
      },
   },
};
```

## Step-by-step Tutorials

If you are interested in a more detailed step-by-step guide, check out our specific tutorial about using Hardhat with Moonbeam:

- [Building with Hardhat](/tutorials/moonbase-alpha/hardhat/) on the Moonbase Alpha TestNet