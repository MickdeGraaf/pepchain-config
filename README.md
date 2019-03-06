# PepChain config and setup scripts

## Churchill setup instructions

### Connecting metamask

From the networks dropdown select custom rpc.
In the rpcUrl field enter the following url:
```
https://churchill-rpc.pepchain.io/
```

Enter "PEP" under symbol and click save

### Running a Churchill testnet node

Install the latest stable version of parity on your system.
On Mac and most Linux systems it can be installed with the following command.

```
bash <(curl https://get.parity.io -L) -r stable
```

Clone this repo

```
git clone https://github.com/mickdegraaf/pepchain-config
```

Go the the right directory

```
cd pepchain-config/churchill
```

Run parity with the right config

```
parity --config full-archive.toml
```

### Running a validator node on the Churchill testnet

#### Setting up a Locker contract

- 1 Get some testnet PEP from the [Telegram Channel](https://t.me/PepChain)
- 2 Setup a new Locker contract [here](https://churchill-voting.pepchain.io/my-lockers)
- 3 Lock some tokens in the contract via the UI

#### Setting up your node

- 1 Do the above steps for running a node and close the parity process
- 2 Edit the password in the node.pwds file. (Keep it somewhere)
- 3 run the following command

```
    parity account new --config full-archive-validator.toml
```

- 4 Copy the outputted address
- 5 From the account you deployed the locker contract from set the validator as the copied address
- 6 Export the generated key from pepchain-config/churchill/keys and import it in metamask. (the password is the one you enterred in node.pwds)
- 7 On the locker contract page in the voting dashboard click the "SET AS LOCKER" Button and approve the transaction
- 8 Edit the validator signer value the correnspond with the outputted address on step 4 in full-archive-validator.toml
- 9 run the following command: 
```
    parity --config full-archive-validator.toml
```

Happy Validating