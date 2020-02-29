---
description: hmy_getValidatorInformation
---

# hmy\_getValidatorInformation

Get staking validator information.

#### Parameters

1. `String` - validator bech32 address.

#### Returns

* `address` - `String` - ECSDA validator address
* `bls-public-keys` - `[]String` - array of validator bls public keys
* `last-epoch-in-committee` - `Number` - big.Int last epoch in committee
* `min-self-delegation` - `Number` - big.Int min self delegation
* `max-total-delegation` - `Number` - big.Int max total delegated to this validator
* `active` - `Bool` - is valdiator currently active
* `commission:`
  * `rate` - `Float` - validator current commission rate
  * `max-rate` - `Float` - max validator commission rate
  * `max-change-rate` - `Float` - max validator commission rate change
  * `update-height`  - `Number` - big.Int last commission update block height
* `description:`
  * `name` - `String` - validator name
  * `identity` - `String` - validator text kyc identity
  * `website` - `String` - validator website
  * `security-contact` - `String` - validator security contact
  * `details` - `String` - additional info
* `creation-height` - `Number` - big.Int block height when validator was created
* `banned` - `Bool` - is validator banned
* `Delegations:`
  * array of validator delegations, check out delegations format in hmy\_getDelegationsBy...
* `Counters:`
  * `num-of-blocks-to-sign` - `Number` - big.Int number of blocks validator should have signed in active mode
  * `num-blocks-signed` - `Number` - big.Int number of blocks validator actually signed

**Sample Curl Request**

```bash
curl -d '{
    "jsonrpc":"2.0",
    "method":"hmy_getValidatorInformation",
    "params":[
      "one103q7qe5t2505lypvltkqtddaef5tzfxwsse4z7"
    ],
    "id":1
}' -H 'Content-Type:application/json' -X POST 'http://api.s0.b.hmny.io'
```

**Sample Curl Response**

```bash
{
    "jsonrpc": "2.0",
    "id": 1,
    "result": []
}
```

