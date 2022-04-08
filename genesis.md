# Genesis file
Both the mainnet and testnet genesis information of `Cube` chain have been hardcoded in blockchain, and the corresponding genesis files are listed below for verification.

## Glossary 
- chainId The unique identification of the chain.
- `homesteadBlock` `eip150Block` `eip150Hash` `eip155Block` `eip158Block` `byzantiumBlock` `constantinopleBlock` `petersburgBlock` `istanbulBlock` `muirGlacierBlock` Hard fork height configuration.
- `chaos` Consensus parameters.
    - `period` is time interval of blocks. 
    - `epoch` is set for a period in `block`, and at the end of each `epoch`, the validators are adjusted accordingly.
- `number` `gasUsed` `parentHash` `nonce` `timestamp` `extraData` `gasLimit` `difficulty` are all parameters for genesis block.
- `extraData` The initial validators is set up here.
- `alloc` Configured initial account information that can be used for asset pre-allocation and pre-initialization of system contracts.
    - [TBD]
    -  
    - 
    - 

  System contracts are under the directory `contracts/builtin/` in the `Cube` repo.

## mainnet
``` JSON

```
## testnet
``` JSON

```