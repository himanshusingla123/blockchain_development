## Querying State
Once you have a Provider, you have a read-only connection to the data on the blockchain. This can be used to query the current account state, fetch historic logs, look up contract code and so on.
```
// Look up the current block number (i.e. height)
await provider.getBlockNumber()
// 19145711

// Get the current balance of an account (by address or ENS name)
balance = await provider.getBalance("ethers.eth")
// 4085267032476673080n

// Since the balance is in wei, you may wish to display it
// in ether instead.
formatEther(balance)
// '4.08526703247667308'

// Get the next nonce required to send a transaction
await provider.getTransactionCount("ethers.eth")
// 2
```
## Sending Transactions
To write to the blockchain you require access to a private key which controls some account. In most cases, those private keys are not accessible directly to your code, and instead you make requests via a Signer, which dispatches the request to a service (such as MetaMask) which provides strictly gated access and requires feedback to the user to approve or reject operations.
```js
// When sending a transaction, the value is in wei, so parseEther
// converts ether to wei.
tx = await signer.sendTransaction({
  to: "ethers.eth",
  value: parseEther("1.0")
});

// Often you may wish to wait until the transaction is mined
receipt = await tx.wait();
```
