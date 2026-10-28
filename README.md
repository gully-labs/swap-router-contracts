<!-- gully-header:start -->
<p align="center">
  <a href="https://gullychain.xyz">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset=".github/assets/gullychain-wordmark-for-dark-bg.png">
      <img alt="Gully Chain" src=".github/assets/gullychain-wordmark-for-light-bg.png" width="360">
    </picture>
  </a>
</p>

<p align="center"><b>The social chain where your profile is your wallet. Arbitrum Orbit L3, testnet chain 485590.</b></p>

<p align="center">Swap router contracts for Gully Swap.</p>

<p align="center">
  <a href="https://gullychain.xyz"><img src="https://img.shields.io/badge/gullychain.xyz-01D9FA?style=for-the-badge&labelColor=000000&logo=googlechrome&logoColor=000000" alt="Website"></a>
  <a href="https://docs.gullychain.xyz"><img src="https://img.shields.io/badge/Docs-0A0F1A?style=for-the-badge&labelColor=000000&logo=readthedocs&logoColor=01D9FA" alt="Docs"></a>
  <a href="https://t.me/GullyChain"><img src="https://img.shields.io/badge/Telegram-0A0F1A?style=for-the-badge&labelColor=000000&logo=telegram&logoColor=26A5E4" alt="Telegram"></a>
  <a href="https://discord.com/invite/tY2ErsNNBp"><img src="https://img.shields.io/badge/Discord-0A0F1A?style=for-the-badge&labelColor=000000&logo=discord&logoColor=5865F2" alt="Discord"></a>
  <a href="https://x.com/Gully_Labs"><img src="https://img.shields.io/badge/@Gully__Labs-0A0F1A?style=for-the-badge&labelColor=000000&logo=x&logoColor=white" alt="X"></a>
</p>

<p align="center"><sub>A Gully Chain fork of <a href="https://github.com/Uniswap/swap-router-contracts">Uniswap/swap-router-contracts</a>, maintained by <a href="https://gullylabs.xyz">Gully Labs</a>. It is used under its GPL-2.0 licence; the upstream LICENSE, copyright and attribution notices are kept unchanged. The upstream README follows below as published. Not affiliated with or endorsed by Uniswap.</sub></p>

---
<!-- gully-header:end -->

# Uniswap Swap Router

[![Tests](https://github.com/Uniswap/swap-router-contracts/workflows/Tests/badge.svg)](https://github.com/Uniswap/swap-router-contracts/actions?query=workflow%3ATests)
[![Lint](https://github.com/Uniswap/swap-router-contracts/workflows/Lint/badge.svg)](https://github.com/Uniswap/swap-router-contracts/actions?query=workflow%3ALint)

This repository contains smart contracts for swapping on the Uniswap V2 and V3 protocols.

## Bug bounty

This repository is subject to the Uniswap V3 bug bounty program,
per the terms defined [here](./bug-bounty.md).

## Local deployment

In order to deploy this code to a local testnet, you should install the npm package
`@uniswap/swap-router-contracts`
and import bytecode imported from artifacts located at
`@uniswap/swap-router-contracts/artifacts/contracts/*/*.json`.
For example:

```typescript
import {
  abi as SWAP_ROUTER_ABI,
  bytecode as SWAP_ROUTER_BYTECODE,
} from '@uniswap/swap-router-contracts/artifacts/contracts/SwapRouter02.sol/SwapRouter02.json'

// deploy the bytecode
```

This will ensure that you are testing against the same bytecode that is deployed to
mainnet and public testnets, and all Uniswap code will correctly interoperate with
your local deployment.

## Using solidity interfaces

The swap router contract interfaces are available for import into solidity smart contracts
via the npm artifact `@uniswap/swap-router-contracts`, e.g.:

```solidity
import '@uniswap/swap-router-contracts/contracts/interfaces/ISwapRouter02.sol';

contract MyContract {
  ISwapRouter02 router;

  function doSomethingWithSwapRouter() {
    // router.exactInput(...);
  }
}

```

## Tests

Some tests use Hardhat mainnet forking and therefore require an archive node.
Either create a `.env` file in the workspace root containing:

```
ARCHIVE_RPC_URL='...'
```

Or set the variable when running tests:

```
export ARCHIVE_RPC_URL='...' && npm run test
```


<!-- gully-footer:start -->
---

<p align="center">
  <a href="https://gullylabs.xyz">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset=".github/assets/powered-by-gully-labs-dark-2x.png">
      <img alt="Powered by Gully Labs" src=".github/assets/powered-by-gully-labs-light-2x.png" width="254" height="64">
    </picture>
  </a>
</p>
<!-- gully-footer:end -->
