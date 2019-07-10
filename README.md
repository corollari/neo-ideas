## Possible contributions
- Improve docs
- Improve NEO Link (NEO metamask)
- Tutorial like cryptozombies for neo
- Proposal for private NEP token (anonymous transfers)
- Develop compiler for Obsidian or Solidity

## Private domain name system
> ENS with zero knowledge proofs to preserve privacy
- Domains are registered through vickrey auctions (see our paper on asset distribution systems for another system that would allow combinatorial auctions)
- Renewal system that punishes name swatting
- Ownership is encoded using ZKP
- Name resolution could be direct or delegated to a smart contract, classic DNS resolver or a file hosted somewhere (IPFS, NeoFS, some blockchain or a normal web server)

## DEX ideas
- ERC20 DEX
- ETH/NEO as a Sidechain (use smart contracts from the BTC network)
- Cross-chain Uniswap
- Cross-chain DEX
- Decentralized BTC token on ETH


### ERC20 DEX
Use the NEO blockchain as a sidechain:
1. Lock ERC20 tokens on the ETH chain
2. The locked tokens are unlocked on the NEO blockchain as NEP5 tokens
3. Transact on the NEO blockchain
4. Destroy NEP5 tokens
5. The previously locked ERC20 tokens get unlocked upon destruction of the NEP5 tokens

### ETH/NEO as a Sidechain
1. A send BTC transaction
2. BTC transaction gets relayed to the ETH network by nodes that will get rewarded for doing so
3. ETH contract is activated by node and mints ERC20 tokens representing BTC to be used by the smart contract associated with A (which will be called S_A), hands over control to S_A
4. S_A performs the transaction that has been relayed
If the S_A receives any money (from other transactions or from the transaction discussed before):
1. Random nodes can trigger transactions (and be rewarded for doing so) on the BTC ERC20 wallet
2. BTC ERC20 wallet will remove the tokens from S_A and force one of the BTC holders to send BTC to A
3. BTC holder must prove that he sent the transaction and that it's been accepted. If he doesn't his collateral gets slashed

### Cross-chain Uniswap
Once liquidity pools are set up, the following swaps can be performed:
BTC->ETH:
1. Send money to one of the addresses of the people that have ETH locked up
2. BTC transaction gets relayed to the ETH network by nodes that will get rewarded for doing so
3. Smart contract automatically sends the ETH to the specified address
ETH->BTC:
1. Send ETH transaction, locking the funds in a smart contract
2. One of the players that have BTC in the liquidity pool will have to send the BTC to the address given by you (How to pick which player?)
3. Player that sent the BTC has to prove that the transaction has been accepted in a timeframe, if not his collateral in ETH is slashed

### Cross-chain DEX
Use XClaim to transform cryptocurrencies from other blockchains to NEP5 tokens in the NEO blockchain the trade these tokens on the NEo blockchain for free.

### Decentralized BTC token on ETH
Implement XClaim.



## Current
- Create a proposal for NNS (NEO Name System)
- Create a public testnet with reduced gas cost and a system to give out neo/gas.


## NEO Research
- IntelSGX (TownCrier) for validators
- Solidity to NEO compiler
  - Compatibility shim between EVM and NVM
- Portis for NEO
- Cryptozombies tutorial
- Port AZTEC protocol

## Ideas with @vang1ong7ang
- Smart contract that stores other contracts and allows calling to them
  - Makes deployment of new SC really cheap
- Improve toolchain for new SC programmers
- WebAssembly for NEO
- Dynamic GAS fees based on execution cost
