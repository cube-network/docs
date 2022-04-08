# Consensus
[TBD]

## Glossary 
- validator. Responsible to be ready for packaging out blocks for on-chain transactions.
- active validator. The current set of validators responsible for packing out blocks, with a maximum of 21.
- epoch. Time interval in blocks, currently 1 epoch = 200 blocks on `Cube`. At the end of each epoch, the blockchain interacts with the system contracts to update active validators.

## System contract

The system contracts are under the `contracts/builtin/` directory of the `Cube` repo.

The management of the current validators are all done by the system contracts.
- `Staking`  It's the only entry of the staking and validators management. Responsible for managing access to validators and managing validator register and staking management, and punishing operations.
- `Validator` Responsible for recording inner staking and delegation information, inner settle staking rewards. Each validator has and only has one `Validator` contract, and the `Validator` contract is created by `Staking` contract when register a new validator, and all functions that invove staking are only accessed by `Staking` contract.

Blockchain call system contracts：
- At the end of each block, the `Staking` contract is called and the fees for all transactions in the block are distributed to active validators.
- The `Staking` contract is called to punish the validator  when the validator is  not  working properly.
- At the end of each epoch, the `Staking` contract is called to update active validators, based on the ranking.

## Staking

[TBD]

## Punishment

1. Whenever a validator is found not to pack block as predefined, the `Staking` contract is automatically called at the end of this block and the validator is counted. When the counter reaches 48, the validator is removed from the list of active validators, be slashing 0.1% of its total staking, and the validator is disqualified.

2. Whenever a validator signs different blocks at a same height, the validator will be `double-sign-punished` through `doubleSignPunish` function of `Staking` contract. The validator will be removed from the list of active validators, be slashing 1% of its total staking, and the validator is disqualified.
