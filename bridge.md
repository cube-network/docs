# Summary

Users can map ETH, BTC, stable coins and other assets to Cube through the asset cross-chain bridge, which is achieved by locking a certain number of assets on the source chain and generating the corresponding number of Tokens in Cube.

Cube encourages community developers to provide more decentralized cross-chain solutions.

This document describes the option for project parties to map Tokens from the source chain to Cube on their own.

The project owner **self** maintains the total balance of Token on the multi-chain including Cube, and endorses the credibility of Token.

The main processes include：

```
1）Initial Preparation
2）Source Chain -> Cube Chain
3）Cube Chain -> Source Chain
```

## Glossary 

Source Chain: The source chain where the Token is located (e.g. Ethereum)

Src_Token: Token on the source chain, possibly a contract, or a native Token

Locked address or contract: the address used to lock the Token

Cube_Token: Token on Cube's chain
## Initial Preparation

1) Deploy the lock address or contract on the source chain `Src_Lock_Addr`

2) Deploy Token on Cube: `Cube_Token`

3) Deploy a lock address or contract on Cube `Cube_Lock_Addr`

If you need multiple sign contracts, you can refer to [gnosis/safe-contracts](https://github.com/gnosis/safe-contracts) or [gnosis/MultiSigWallet](https://github.com/gnosis/MultiSigWallet).

If you need contracts with mint/burn, you can refer to [OpenZeppelin/openzeppelin-contracts](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/) contracts/token/ERC20).

> In order to maintain credibility, the project needs to publicize the above information to the community and invite the community to supervise it. And to monitor the total amount of coins on both chains.

## Source Chain->Cube Chain

1) Source chain locking `Src_Token`

Transfer a certain amount of `Src_Token` to `Src_Lock_Addr` for locking

2) Release `Cube_Token` on the Cube chain

Execute mint operation to give `Cube_Lock_Addr` the corresponding amount of `Cube_Token`

## Cube chain->Source chain

1) Cube chain lock `Cube_Token`

Execute burn operation, destroy `Cube_Token`

2) Release `Src_Token` on the source chain

operation `Src_Lock_Addr` to unlock the corresponding volume