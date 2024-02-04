# Connection to ethereum
The quickest and easiest way to experiment and begin developing on Ethereum is to use MetaMask, which is a browser extension that injects objects into the window, providing:
> read-only access to the Ethereum network (a Provider)
> authenticated write access backed by a private key (a Signer)
When requesting access to the authenticated methods, such as sending a transaction or even requesting the private key address, MetaMask will show a pop-up to the user asking for permission.
```js
  let signer = null;

let provider;
if (window.ethereum == null) {

    // If MetaMask is not installed, we use the default provider,
    // which is backed by a variety of third-party services (such
    // as INFURA). They do not have private keys installed,
    // so they only have read-only access
    console.log("MetaMask not installed; using read-only defaults")
    provider = ethers.getDefaultProvider()

} else {

    // Connect to the MetaMask EIP-1193 object. This is a standard
    // protocol that allows Ethers access to make all read-only
    // requests through MetaMask.
    provider = new ethers.BrowserProvider(window.ethereum)

    // It also provides an opportunity to request access to write
    // operations, which will be performed by the private key
    // that MetaMask manages for the user.
    signer = await provider.getSigner();
}
```
# Custom RPC Backend
If you are running your own Ethereum node (e.g. Geth) or using a custom third-party service (e.g. INFURA), you can use the JsonRpcProvider directly, which communicates using the link-jsonrpc protocol.
When using your own Ethereum node or a developer-base blockchain, such as Hardhat or Ganache, you can get access to the accounts with JsonRpcProvider-getSigner.
```js
// If no %%url%% is provided, it connects to the default
// http://localhost:8545, which most nodes use.
provider = new ethers.JsonRpcProvider(url)

// Get write access as an account by getting the signer
signer = await provider.getSigner()
```
