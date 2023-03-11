---
label: ApproveAndCall (sol)
---


# Approve And Call (sol)

```   
    function receiveApproval(address from, uint256 tokens, address token, bytes memory data) public returns (bool success) {
        
        /*
        //recommended sample code 

         require( msg.sender == currencyToken , "Invalid receiveApproval origin");
          require( token == currencyToken , "Invalid token type received");
        */  
       
        // _other_internal_calls_here...

        return true;

     }
 
```

 

:::info
By including a 'receiveApproval()' method on your smart contract, you can support single-transaction interaction with 0xbitcoin instead of requiring a separate approval and direct call.
:::
 
