# Introduction

## Development Environments

[JSON-RPC](https://en.wikipedia.org/wiki/JSON-RPC) is a remote procedure call protocol encoded in JSON. You can use this API to access data from the Harmony nodes. The JSON-RPC API server runs on:

| Chains | URLs |
| :--- | :--- |
| mainnet | TBD |
| betaNet | [http://l0.b.hmny.io:9500](http://l0.b.hmny.io:9500) |
| local | [http://localhost:9500](http://localhost:9500) |

All API calls are POST requests.

All requests follow the standard JSON-RPC format and include 4 variables in the data object:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Request Data Object</th>
      <th style="text-align:left">Example</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">jsonrpc</td>
      <td style="text-align:left">&quot;2.0&quot;</td>
      <td style="text-align:left">Specifies version number</td>
    </tr>
    <tr>
      <td style="text-align:left">method</td>
      <td style="text-align:left">&quot;hmy_getBalance&quot;</td>
      <td style="text-align:left">Method to be called server-side</td>
    </tr>
    <tr>
      <td style="text-align:left">params</td>
      <td style="text-align:left">[&quot;0xD7Ff...24Cf2d&quot;, &quot;latest&quot;]</td>
      <td style="text-align:left">Parameters for method call</td>
    </tr>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">&quot;1&quot;</td>
      <td style="text-align:left">
        <p>Echoed in response, can be used</p>
        <p>to match request to response</p>
        <p>when sending multiple requests</p>
      </td>
    </tr>
  </tbody>
</table>**Sample Request body**`{"jsonrpc":"2.0","method":"hmy_getBalance","params":["0xD7Ff41CA29306122185A07d04293DdB35F24Cf2d", "latest"],"id":1}`

## Key Harmony Repositories

Harmony.one github - [https://github.com/harmony-one](https://github.com/harmony-one)  
Harmony Blockchain Repository - [https://github.com/harmony-one/harmony](https://github.com/harmony-one/harmony)  
Harmony SDK - [https://github.com/harmony-one/sdk](https://github.com/harmony-one/sdk)  
Harmony DApp Examples - [https://github.com/harmony-one/dapp-examples](https://github.com/harmony-one/dapp-examples)  
Harmony Web Wallet \(WIP\) - [https://github.com/harmony-one/dapp-examples/tree/master/web/WebWallet](https://github.com/harmony-one/dapp-examples/tree/master/web/WebWallet)

## Key Differences between Harmony and Ethereum

1. The prefix of RPC calls is different - 'hmy' is used instead of 'eth'.
2. Address format, SDK uses two, the default use checksum, it is recommended to use Bech32. has been defined in the SDK.
3. Transaction uses RLP, but adds two fields, one is shardID and the other is toShardID.
4. There are some RPC Ethereum, there is no Harmony, we will discuss it in detail during the process.

So for the JS project, you can directly modify the existing Ethereum library, or you can use the SDK package to see your engineering needs.

**The best practice is to extend the SDK's Transaction class and then add customization.**

The biggest difference is that Harmony does not use `eth_sendTransaction` and uses `eth_sendRawTransaction` to send the signed bytes, this is called `hmy_sendRawTransaction`.

