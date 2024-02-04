Sure, let's go through each type, class, and interface along with their properties and methods in detail:

### Types

1. **ContractEventName**
   - Represents the name for an event used for subscribing to Contract events.
   - It can be a string, a ContractEvent, a TopicFilter, or a DeferredTopicFilter.

### Classes and Interfaces

1. **BaseContract**
   - Inherits from Addressable.
   - **Properties:**
     - fallback: Represents the fallback or receive function if any.
     - filters: An object containing all the Events available on this contract.
     - interface: The contract Interface.
     - runner: The connected runner, generally a Provider or a Signer.
     - target: The target to connect to, which can be an address, ENS name, or any Addressable.
   - **Methods:**
     - addListener(event, listener)
     - attach(target)
     - connect(runner)
     - deploymentTransaction()
     - emit(event, args)
     - getAddress()
     - getDeployedCode()
     - getEvent(key)
     - getFunction(key)
     - listenerCount(event)
     - listeners(event)
     - off(event, listener)
     - on(event, listener)
     - once(event, listener)
     - queryFilter(event, fromBlock, toBlock)
     - removeAllListeners(event)
     - removeListener(event, listener)
     - waitForDeployment()
   - **Static Methods:**
     - buildClass(abi)
     - from(target, abi, runner)

2. **BaseContractMethod**
   - Represents a Contract method.
   - **Properties:**
     - fragment: The fragment of the Contract method.
     - name: The name of the Contract method.
   - **Methods:**
     - estimateGas(args)
     - getFragment(args)
     - populateTransaction(args)
     - send(args)
     - staticCall(args)
     - staticCallResult(args)

3. **ConstantContractMethod**
   - Inherits from ContractMethod, BaseContractMethod.
   - Represents a pure or view method on a Contract.

4. **Contract**
   - Represents a BaseContract with no type guards on its methods or events.

5. **ContractDeployTransaction**
   - Represents a deployment transaction for a contract.

6. **ContractEvent**
   - Represents a Contract event.
   - **Properties:**
     - fragment: The fragment of the Contract event.
     - name: The name of the Contract event.
   - **Methods:**
     - getFragment(args)

7. **ContractEventPayload**
   - Inherits from ContractUnknownEventPayload, EventPayload.
   - Represents a ContractEventPayload included as the last parameter to Contract Events when the event is known.
   - **Properties:**
     - args: The parsed arguments passed to the event by emit.
     - eventName: The event name.
     - eventSignature: The event signature.
     - fragment: The matching event.
     - log: The log, with parsed properties.

8. **ContractFactory**
   - Represents a ContractFactory used to deploy a Contract to the blockchain.
   - **Properties:**
     - bytecode: The Contract deployment bytecode.
     - interface: The Contract Interface.
     - runner: The ContractRunner to deploy the Contract as.
   - **Methods:**
     - attach(target)
     - connect(runner)
     - deploy(args)
     - getDeployTransaction(args)
   - **Static Methods:**
     - fromSolidity(output, runner)

9. **ContractInterface**
   - Represents a Contract with no method constraints.

10. **ContractMethod**
    - Inherits from BaseContractMethod.
    - Represents a contract method on a Contract.

11. **ContractTransaction**
    - Inherits from PreparedTransactionRequest.
    - Represents a transaction when populating a transaction.

12. **ContractTransactionReceipt**
    - Inherits from TransactionReceipt, TransactionReceiptParams.
    - Represents a ContractTransactionReceipt including the parsed logs from a TransactionReceipt.
    - **Properties:**
      - logs: The parsed logs for any Log which has a matching event in the Contract ABI.

13. **ContractTransactionResponse**
    - Inherits from TransactionResponse, TransactionResponseParams.
    - Represents a ContractTransactionResponse which will return a ContractTransactionReceipt when waited on.
    - **Methods:**
      - wait(confirms, timeout)

14. **ContractUnknownEventPayload**
    - Inherits from EventPayload.
    - Represents a ContractUnknownEventPayload included as the last parameter to Contract Events when the event does not match any events in the ABI.
    - **Properties:**
      - log: The log with no matching events.
    - **Methods:**
      - getBlock()
      - getTransaction()
      - getTransactionReceipt()

15. **DeferredTopicFilter**
    - Represents a filter when creating a filter using the contract.filters.
    - **Properties:**
      - fragment
    - **Methods:**
      - getTopicFilter()

16. **EventLog**
    - Inherits from Log, LogParams.
    - Represents an EventLog containing additional properties parsed from the Log.
    - **Properties:**
      - args: The parsed arguments passed to the event by emit.
      - eventName: The name of the event.
      - eventSignature: The signature of the event.
      - fragment: The matching event.
      - interface: The Contract Interface.

17. **Overrides**
    - Represents the overrides for a contract transaction.

18. **WrappedFallback**
    - Represents a Fallback or Receive function on a Contract.
    - **Methods:**
      - estimateGas(overrides)
      - populateTransaction(overrides)
      - send(overrides)
      - staticCall(overrides)

These are the detailed descriptions of each type, class, and interface along with their properties and methods in the provided JavaScript interface for interacting with smart contracts on the blockchain.
