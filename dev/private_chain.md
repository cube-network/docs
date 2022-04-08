# Private chain construction

## Prepare validator account(s)

According to the number of miner nodes, prepare corresponding validator account(s).

You can create a new account by the command `geth account new`, and then put the password to a text file. For example:

```bash
./geth account new --datadir data
echo {your-password} > password.txt
```

After creating an account, you may see the address of the new account.

Or you can also looking to the `UTC-**`file under the `data/keystore` path to find it, e.g.:
```
8cc5a1a0802db41db826c2fcb72423744338dcb0
```

## genesis.json configuration
```JSON


```
- `chaos`  Consensus-related parameters.
- `period` Block interval time.
- `extraData` Use to set inital validators. Replace `8cc5a1a0802db41db826c2fcb72423744338dcb0` with your own address. If you want multiple validators, you can replace with stitching them together.
- `alloc` [TBD] are system contracts. If you wish to compile it yourself, you can configure `deployedBytecode` to the `code` field after compilation. 

## Create genesis block
After generating the `genesis.json` file, execute the following command to generate the genesis block.
```
geth init genesis.json
```

## Multiple node 
Use the same `genesis.json` file for initializing the node. Then go to the node command line with the `geth attach` command. View the node information via `admin.nodeInfo`. Then add the node on other machines with `addmin.addPeer`.

## Using docker-compose to deploy a private-chain

If you would like to use docker-compose to deploy and run a private-chain, then you can reference to <https://github.com/cube-network/docs/tree/master/docker/multi>.

> Note: should first put the Linux-amd64 version of `geth` under the `multi` directory.