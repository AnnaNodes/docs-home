---
description: >-
  This page lists well-known contracts that are deployed on harmony including
  dapps, Stablecoins, bridged tokens, etc.
---

# List of Deployed Contracts

## Overview

Development on the Harmony Platform is evolving rapidly, with many new projects being added. This page is designed for developers thinking of building new projects on Harmony or building on top of existing protocols that have been deployed on Harmony it gives an overview of some of the common projects and contract addresses for developers.

{% hint style="info" %}
If you want a better overview of all the Harmony Stack and the Projects deployed on Harmony and ideas for new projects, please see the [Harmony Stack and Projects](https://docs.harmony.one/home/developers/harmony-stack) page.
{% endhint %}

## Contract address format

Harmony uses it's own contract address starting with a one prefix 

e.g. `one1l8n75pj8zmka0nxtqjneexf3p8l442g8xrxplx` 

There is a one to one mapping of these addresses to the traditional  0x prefix

e.g. `0xcf664087a5bb0237a0bad6742852ec6c8d69a27a`

{% hint style="info" %}
The [Harmony explorer](https://explorer.harmony.one/address/0xcf664087a5bb0237a0bad6742852ec6c8d69a27a) provides the ability to search using either format and also can be used to find the associated 0x or one prefixed address. When viewing a contract in the explorer the one format will be listed as the Address on the page  and the 0x format will be listed in the URL for [example](https://explorer.harmony.one/address/0xcf664087a5bb0237a0bad6742852ec6c8d69a27a) `https://explorer.harmony.one/address/0xcf664087a5bb0237a0bad6742852ec6c8d69a27a`
{% endhint %}

## Token address references

There are a number of places developers can look to find more information about tokens deployed on the Harmony Network such as token lists and using the explorer, here are a few useful references.

| Reference | Description |
| :--- | :--- |
| [HRC20 Tokens on Harmony Explorer](https://explorer.harmony.one/hrc20) | Gives a list of all HRC20 tokens deployed including name, symbol, address, circulating supply,  Total Supply and number of holders. |
| [HRC721 Tokens on Harmony Explorer](https://explorer.harmony.one/hrc721) | Gives a list of all HRC721 tokens deployed including name, symbol, address  and number of holders. |
| [HRC1155 Tokens on Harmony Explorer](https://explorer.harmony.one/hrc1155) | Gives a list of all HRC1155 tokens deployed including name, symbol, address  and number of holders. |
| [Swoop Default Token List](https://github.com/harmony-one/swoop-default-token-list) | Provides a default token list for [swoop.exchange](https://swoop.exchange/) for both [testnet](https://github.com/harmony-one/swoop-default-token-list/blob/master/src/tokens/testnet.json) and [mainnet](https://github.com/harmony-one/swoop-default-token-list/blob/master/src/tokens/mainnet.json). |
| [ViperSwap Default Token List](https://github.com/VenomProtocol/venomswap-community-token-list) | Provides a default token list for [viperswap.one](https://viperswap.one/#/swap)  including both [testnet](https://github.com/VenomProtocol/venomswap-community-token-list/blob/main/src/tokens/harmony-testnet.json) and [mainnet](https://github.com/VenomProtocol/venomswap-community-token-list/blob/main/src/tokens/harmony-mainnet.json) |

## Project Contract Addresses

The following is a list of some of the projects on Harmony and their contract addresses

{% hint style="info" %}
Building bridges is one of Harmony's main focus points. So far, three bridges are in production and have tokens bridged over to Harmony. These are: Ethereum \(ETH\), Binance Smart Chain \(BSC\) and Terra.

The same asset may be bridged from different networks. For example, the BUSD token is bridged from ETH and BSC. To separate the two, the BSC version has the prefix 'bsc' applied to it. So there are BUSD tokens \(bridged from ETH\) and bscBUSD tokens \(bridged from BSC\).
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Project Type</th>
      <th style="text-align:left">Project</th>
      <th style="text-align:left">Contract Type and Link</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><a href="https://medium.com/harmony-one/harmonys-new-tokenomics-bcdac0db60d7">Harmony Native Token</a>
      </td>
      <td style="text-align:left"><a href="https://explorer.harmony.one/address/0xcf664087a5bb0237a0bad6742852ec6c8d69a27a">Wrapped ONE</a>
      </td>
      <td style="text-align:left"><a href="https://explorer.harmony.one/address/0xcf664087a5bb0237a0bad6742852ec6c8d69a27a?activeTab=7">Token</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/general/dapps/dexes">Decentralized Exchange</a>
      </td>
      <td style="text-align:left"><a href="https://sushi.com/">Sushi</a> on <a href="https://medium.com/harmony-one/sushiswap-on-harmony-protocol-9e537d01489a">Harmony</a>
      </td>
      <td style="text-align:left"><a href="https://explorer.harmony.one/address/0xbec775cb42abfa4288de81f387a9b1a3c4bc552a?activeTab=7">Token</a>
        <br
        /><a href="https://explorer.harmony.one/address/0xa7a22299918828d791240f9ec310c2e066592053?activeTab=7">SushiBar</a>
        <br
        /><a href="https://explorer.harmony.one/address/0x67da5f2ffaddff067ab9d5f025f8810634d84287?activeTab=7">MiniChefV2</a>
        <br
        /><a href="https://explorer.harmony.one/address/0x25836011bbc0d5b6db96b20361a474cbc5245b45?activeTab=7">ComplexRewarderTime</a>
        <br
        /><a href="https://dev.sushi.com/sushiswap/contracts">Other Contracts</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/general/dapps/dexes">Decentralized Exchange</a>
      </td>
      <td style="text-align:left"><a href="https://viperswap.one/#/swap">Viperswap</a>
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0xea589e93ff18b1a1f1e9bac7ef3e86ab62addc79?activeTab=7">Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x7abc67c8d4b248a38b0dc5756300630108cb48b4?activeTab=7">MasterBreeder</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x08913d353091e24b361f0e519e2f7ad07a78995d?activeTab=7">PitBreeder</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xe064a68994e9380250cfee3e8c0e2ac5c0924548?activeTab=7">ViperPit</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x410ce9879d14919cbc9693406d5950a60d3b0f48?activeTab=7">SmartChef</a>
          <br
          /><a href="https://explorer.harmony.one/address/0x7d02c116b98d0965ba7b642ace0183ad8b8d2196?activeTab=7">UniswapV2Factory</a>
          <br
          /><a href="https://explorer.harmony.one/address/0xf012702a5f0e54015362cbca26a26fc90aa832a3?activeTab=7">UniswapV2Router</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/general/dapps/dexes">Decentralized Exchange</a>
      </td>
      <td style="text-align:left"><a href="https://lootswap.finance/">Lootswap</a>
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0xbda99c8695986b45a0dd3979cc6f3974d9753d30">Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xb96618aebd36f8d83fa03873fda796264597604d?activeTab=7">MasterLooter</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xa15c7828ab22d182383a84f828cd71ac09bb55e8?activeTab=7">AutoLoot</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://explorer.harmony.one/hrc20">HRC20 Tokens</a>
      </td>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/developers/harmony-stack">Harmony Ecosystem</a> 
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0xf315803ba9da293765ab163e7db98e8d6df6d361">Daikiri Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x9b68bf4bf89c115c721105eaf6bd5164afcc51e4">Freyala</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x2f459dd7cbcc9d8323621f6fb430cd0555411e7b">TokenJenny</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x3e018675c0ef63eb361b9ef4bfea3a3294c74c7b">Kuro Shiba</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xbda99c8695986b45a0dd3979cc6f3974d9753d30">Loot</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x8d4f19bec883ba20f4f295706c53f760cd0bc2b0">Moonity</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xc0431ddcc0d213bf27ececa8c2362c0d0208c6dc">OpenSwap Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xcb35e4945c7f463c5ccbe3bf9f0389ab9321248f">OneMoon</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xea589e93ff18b1a1f1e9bac7ef3e86ab62addc79">Viper</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/general/horizon-bridge/bridging-eth-one">Ethereum Bridged Tokens</a>
      </td>
      <td style="text-align:left"><a href="https://bridge.harmony.one/busd">Horizon</a>
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0xcf323aad9e522b93f11c352caa519ad0e14eb40f">Aave Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xe176ebe47d621b984a73036b9da5d834411ef734">Binance USD</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x218532a12a389a4a92fc0c5fb22901d1c19198aa">ChainLink Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xef977d2f931c1978db5f6747666fa1eacb0d0339">Dai Stablecoin</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x6983d1e6def3690c4d616b13597a09e6193ea013">ETH</a>
          <br
          /><a href="https://explorer.harmony.one/address/0x301259f392b551ca8c592c9f676fcd2f9a0a84c5">Matic Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xbec775cb42abfa4288de81f387a9b1a3c4bc552a">SushiToken</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x3c2b8be99c50593081eaa2a724f0b8285f5aba8f">Tether USD</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x90d81749da8867962c760414c1c25ec926e889b6">Uniswap</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x985458e523db3d53125813ed68c274899e9dfab4">USD Coin</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x3095c7557bcb296ccc6e363de01b760ba031f2d9">Wrapped BTC</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://docs.harmony.one/home/general/horizon-bridge/bridging-bsc-one">Binance Bridged Tokens</a>
      </td>
      <td style="text-align:left"><a href="https://bridge.harmony.one/erc20">Horizon</a>
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0x0ab43550a6915f9f67d0c454c2e90385e6497eaa">BUSD Token</a>
          <br
          /><a href="https://explorer.harmony.one/address/0xb1f6e61e1e113625593a22fa6aa94f8052bc39e0">BNB</a>
          <br
          /><a href="https://explorer.harmony.one/address/0x582617bd8ca80d22d4432e63fda52d74dcdcee4c">Cardano Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xd6bad903e550822d51073afb79581bf5aae9243f">Cosmos Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0xf155e1a57db0ca820ae37ab4050e0e4c7cfcecd0">Dogecoin</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x6e7be5b9b4c9953434cd83950d61408f1ccc3bee">Matic Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x3e9d32580b0bf3ae72afcbebc68710d2fd9a18f0">PancakeSwap Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x9a89d0e1b051640c6704dde4df881f73adfef39a">Tether USD</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x44ced87b9f1492bf2dcf5c16004832569f7f6cba">USD Coin</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x0341d02c0fd5439576742750e6f2a2c0993a520b">Zilliqa</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://medium.com/harmony-one/terra-and-harmony-announce-tight-full-stack-partnership-focused-on-users-developers-and-mass-de7bbbe7e5a9">Terra StableCoin Tokens</a>
      </td>
      <td style="text-align:left"><a href="https://www.terra.money/">Terra</a> 
      </td>
      <td style="text-align:left">
        <p><a href="https://explorer.harmony.one/address/0x224e64ec1bdce3870a6a6c777edd450454068fec?activeTab=0">Wrapped UST Token</a>
        </p>
        <p><a href="https://explorer.harmony.one/address/0x95ce547d730519a90def30d647f37d9e5359b6ae">Wrapped Luna Token</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>



