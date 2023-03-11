---
label: ApproveAndCall (sol)
---


# Approve And Call (sol)

```

   
    function receiveApproval(address from, uint256 tokens, address token, bytes memory data) public returns (bool success) {
        

        //example code
        //require( token == _originalToken );
        //_callInternalMethod()...



        return true;

     }


 
```

 

:::info
By including a 'receiveApproval()' method on your smart contract, you can support single-transaction interaction with 0xbitcoin instead of requiring a separate approval and direct call.
:::

+++
