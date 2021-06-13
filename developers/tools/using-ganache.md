# Using Ganache

Install Ganache CLI

```text
npm install -g ganache-cli
```

Load Harmony networks \(local, testnet, mainnet\) to ganache-cli. The command below loads 

```text
ganache-cli -f http://localhost:9500 --networkId 1666700000
or for testnet
ganache-cli -f https://api.s0.b.hmny.io --networkId 1666700000
or for mainnet
ganache-cli -f https://api.s0.t.hmny.io --networkId 1666600000
```

Use web3.js to interact with the ganache binded harmony network 

```text
const web3 = new Web3("http://127.0.0.1:8545");
web3.eth.getBlockNumber().then(console.log)
```

{% hint style="info" %}
Currently there is a known [issue](https://github.com/harmony-one/sdk/issues/95) that is preventing from complete integration of ganache to harmony networks. This bug should be fixed soon. 
{% endhint %}

