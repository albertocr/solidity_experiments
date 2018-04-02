# Solidity Experiments

Ethereum contract development and deployment using solidity as a language and Proof of existence as a use case

## Getting Started

### Prerequisites

What things you need to install the software and how to install them
    
#### Mac OSX

``` $ npm install -g ethereumjs-testrpc
```
*testrpc* has to be run in a new terminal and leave it running while develop
``` $ testrpc
```

### Creating a new contract:

```$ truffle create contract *ContractName*
```
When a new contract is developed, a new migrations file has to be generated and after that it has to be run the following for deploying the contract.
```
$ truffle migrate --reset
```

To interact with the contract:
```
$ truffle console
```

Then in truffle console:

Get the new version of the contract
```
var poe = ProofOfExistence2.at(ProofOfExistence2.address)
```
let's check for some new document, and it shouldn't be there.
```
poe.checkDocument('hello')
```
let's now add that document to the proof store
```
poe.notarize('hello')
```
let's now check again if the document has been notarized!
```
poe.checkDocument('hello')
```
we can also store other documents and they are recorded too
```
poe.notarize('some other document');
poe.checkDocument('some other document')
```


### Developing and testing a contract
testrpc

### Installing Geth

After developing a contract, it can be tested in a testnet or deployed to the eth net.

For deploying to a testnet:

1. Install a client. i.e. [Geth](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum)
2. Run geth in a testnet mode.
```
geth --testnet --rpc console 2>> geth.log
```
Create a new account
```
personal.newAccount()
```
- Get few testnet ethers from (http://faucet.ropsten.be:3001)
- Copy and paste the address you get when creating new accounts
- Check the transactions in a [testnet block explorer](ropsten.etherscan.io)
- When your node is completely synced with the testnet, you can check your balance
```
> eth.getBalance(eth.accounts[0])
``
