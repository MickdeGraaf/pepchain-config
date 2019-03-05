# PepChain config and setup scripts

## Running a Churchill testnet node

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