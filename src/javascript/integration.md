---
label: Integration (JS)
---


# Integration (Javascript)

```
let tokenContractABI = require(0xBTC_ABI.json)
let contractAddress = 0x...
const Web3 = require('web3')
let web3 = new Web3( jsonRPCProviderURI )
var tokenContract = new web3.eth.Contract(tokenContractABI,contractAddress)
```