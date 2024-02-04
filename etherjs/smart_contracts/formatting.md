The provided interface definitions describe various parameters and properties related to formatted blocks, logs, transaction receipts, and transaction responses in the context of Ethereum blockchain transactions. Let's break down each interface and its properties:

### BlockParams
- **Purpose**: Encodes the minimal required properties for a formatted block.
- **Properties**:
  - `baseFeePerGas`: The protocol-defined base fee per gas in an EIP-1559 block.
  - `blobGasUsed`: The total amount of BLOb gas consumed by transactions within the block.
  - `difficulty`: Difficulty target used to adjust mining difficulty in proof-of-work networks.
  - `excessBlobGas`: Running total of BLOb gas consumed in excess of the target prior to the block.
  - `extraData`: Additional data included by the miner.
  - `gasLimit`: Maximum amount of gas a block can consume.
  - `gasUsed`: Amount of gas consumed by the block.
  - `hash`: Block hash.
  - `miner`: Miner (or author) of the block.
  - `nonce`: Random sequence provided during the mining process for proof-of-work networks.
  - `number`: Block number.
  - `parentHash`: Hash of the previous block in the blockchain.
  - `timestamp`: Timestamp for the block.
  - `transactions`: List of transactions in the block.

### LogParams
- **Purpose**: Encodes the minimal required properties for a formatted log.
- **Properties**:
  - `address`: Address of the contract that emitted the log.
  - `blockHash`: Block hash of the block containing the transaction for this log.
  - `blockNumber`: Block number of the block containing the transaction for this log.
  - `data`: Data emitted with the log.
  - `index`: Index of the log.
  - `removed`: Indicates if the log was removed due to an orphaned block.
  - `topics`: Topics emitted with the log.
  - `transactionHash`: Transaction hash for the transaction containing the log.
  - `transactionIndex`: Transaction index of the log.

### TransactionReceiptParams
- **Purpose**: Encodes the minimal required properties for a formatted transaction receipt.
- **Properties** (subset):
  - `blockHash`: Block hash of the block containing the transaction.
  - `blockNumber`: Block number of the block containing the transaction.
  - `contractAddress`: Address of the deployed contract (if applicable).
  - `cumulativeGasUsed`: Total gas consumed during the entire block.
  - `gasUsed`: Gas consumed by the transaction.
  - `logs`: Logs emitted during the execution of the transaction.
  - `status`: Status of the transaction execution (success or revert).
  - `to`: Target of the transaction (for deployment transactions).
  - `type`: EIP-2718 envelope type.

### TransactionResponseParams
- **Purpose**: Encodes the minimal required properties for a formatted transaction response.
- **Properties** (subset):
  - `chainId`: Chain ID the transaction is valid on.
  - `data`: Transaction data.
  - `from`: Sender of the transaction.
  - `gasLimit`: Maximum gas authorized for the transaction.
  - `hash`: Transaction hash.
  - `nonce`: Nonce of the transaction.
  - `to`: Target of the transaction.
  - `value`: Transaction value (in wei).

These interfaces provide structured representations of essential parameters and properties associated with blocks, logs, transaction receipts, and transaction responses in Ethereum blockchain transactions, enabling standardized formatting and manipulation of transaction data in Ethereum-based applications.
