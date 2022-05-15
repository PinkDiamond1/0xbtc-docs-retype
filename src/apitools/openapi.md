---
label: Open 0xBTC API
---


# Open 0xBTC API 




 [Find it on Github](https://github.com/OpenSourceMfers/open-0xbtc-api)



The 'Open 0xBTC API' is an initiative to create a standardized decentralized api node for mining data.  This is a self-hosted trustless API where data for 0xBTC is computed independently from a Web3 Data Provider such as a Full Ethereum Node.  

This API uses a local mongoDB to cache and compute on historical 0xBitcoin mint data.


### Using the API 
 

**POST /api/mints/**  
Returns data about recent 0xBTC mints.  Returns all mint data in time Descending order.  

*Input Fields*

`
contractAddress
`
The contract address of the 0xBitcoin smart contract.  

`
size
`
The amount of results to return. Maximum of 500. Defaault is 1.

`
spacing
`
The miningEpoch gap between each of the results to return. Default is 1.

`
startEpoch
`
The starting epoch of mint. Default is the latest mint epoch (closest to present time).

 