# Frontier Chain Testnet: Black Mamba 0

This will be the first public testnet for Frontier Chain, a public blockchain for managing DeFi positions across various protocols without compromising safety or security. Read the introduction [here](https://blog.frontierwallet.com/frontier-chain-testnet-is-now-live/).

Please put gentxs in the `gentxs` folder within this directory.


## TLDR to submit a gentx:

```
chain-id: frontier-chain-testnet-0-black-mamba
gentx-amount: 1000000000000front
front version: v0.1.0
genesis-time: 2021-04-14T15:00:00Z
```

## Instructions to install Frontier Chain and submit a gentx:

__Note__: Requires golang 1.15+ (https://golang.org/doc/install)

```
# clone the frontier chain repo
git clone git@github.com:frontierdotxyz/frontier-chain.git
# install
cd frontier && git checkout v0.1.0 && make install

# initialize chain
frontd init my_node --chain-id frontier-chain-testnet-0-black-mamba

# Add validator key
frontcli config keyring-backend test
frontcli keys add validator

# Create gentx
frontd add-genesis-account $(frontcli keys show validator -a) 1000000000000front
frontd gentx --name validator --amount 1000000000000front --keyring-backend test
```

## Genesis Details

```
genesis hash: 01b86a2e401ea1519644bff059c7a937496003fb7a61554d3dff7ecfcfdfa7e1
seeds: PLACEHOLDER
persistent peers: a6b554f55b619ec07e8ecbb0abc36cce39dcea39@34.239.152.196:26656
```

## Troubleshooting

```
#1 Do you have
export PATH=$PATH:/usr/local/go/bin
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
in your bashrc/zshrc?

#2 Make sure go version installed in your system meets the minimum requirement of 1.15+

you can check that by running the following command

go version

#3 Restart your terminal and try again
```
