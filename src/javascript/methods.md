---
label: Methods (JS)
---


# Methods (JS)

```
var tokenContract = new web3.eth.Contract(tokenContractABI,contractAddress)
let challenge = await tokenContract.methods.getChallengeNumber().call()
```


+++ Read Contract

### ERC20 Methods 

**name()**  
returns the name of the token

**symbol()**
returns the symbol of the token

**totalSupply()**  
returns the maximum diluted supply for the token

**decimals()**  
returns '8'

**balanceOf(address tokenOwner)**  
returns the number of tokens owned by 'tokenOwner'

**allowance(address tokenOwner, address spender)**  
returns the number of tokens that 'tokenOwner' allows 'spender' to 'transferFrom' on their behalf

### EIP918 Methods 

**tokensMinted()**  
returns the amount of tokens in active circulation

**getChallengeNumber()**  
returns the current 'challenge number' used for the PoW mint method.  This is a recent Ethereum blockhash, established during the previous PoW mint.

**getMiningReward()**  
returns the number of tokens awarded for the PoW mint method

**getMiningDifficulty()**  
returns the current difficulty multiplier for the PoW mint method

**getMiningTarget()**  
returns the current difficulty target for the PoW mint method

**epochCount()**  
returns the number of times that the mint method has been called

**rewardEra()**  
returns the number of halvenings that have occured

**maxSupplyForEra()**  
returns the next tokensMinted amount at which the rewardEra will increment

 

+++ Write Contract

### ERC20 Methods 

**approve(address spender, uint256 amount)**  
Approve 'amount' tokens for 'spender' to spend on your behalf using 'transferFrom'

**transfer(address to, uint256, amount)**  
Transfer 'amount' tokens from msg.sender to 'to'

**transferFrom(address from, address to, uint256 amount)**  
Transfer 'amount' tokens from 'from' to 'to'. Requires pre-approval using 'approve'.

**approveAndCall(address spender, uint256 amount, bytes data)**  
Approve 'amount' tokens for 'spender' to spend on your behalf and remote execute the 'ApproveAndCallFallback(address from, uint256 amount, bytes data)' method of the contract at address 'spender'


### EIP918 Methods 

**mint(uint256 nonce, bytes32 challengeDigest)**  
Submit a nonce and challengeDigest in order to mint 'getMiningReward' new tokens.  The new tokens are automatically sent to msg.sender.
The nonce is a number that is non-trivial to find for a machine.  Classical computers must use brute force, or guess-and-check, to find the nonce.  The nonce is valid if and only if:

```
bytes32 challengeDigest = keccak256(challengeNumber, msg.sender, nonce );
```

**AND**  

```
uint256(challengeDigest) < difficultyTarget;
```


:::info
Since msg.sender is part of the hashing function, solution-nonces are scoped for a particular address.  Only that address will be allowed to submit the solution to the contract. This prevents frontrunning/interception.
:::

+++
