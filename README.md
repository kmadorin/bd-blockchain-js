# bd-blockchain-js
Simple js-blockchain with wallet, mempool and other staff 

To run the project:
``` 
npm i
npm run dev
```

# Bd-blockchain in action:

1. Run the first node
  ``` npm run dev ```
2. Run the second node
  ``` HTTP_PORT=3002 P2P_PORT=5002 PEERS=ws://localhost:5001 npm run dev ```
3. Use API methods

To send some coins to the second node
`GET localhost:3002/public-key' - get the address of the second node
`POST localhost:3001/transact` - make a new transaction(s). Request body:

``` 
  {
    "recipient": "public key of the second node",
    "amount": 50 (any value, default balance is 500)
  }
```
`GET localhost:3001(2)/transactions` - view all uncommited transactions
`GET localhost:3001(2)/mine-transactions` - mine a new block with all uncommited transactions in Mempool. 
In response you can see the JSON with all blocks in blockchain

Tests:
``` npm run test ```
