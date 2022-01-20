# Dastardly Ducks (DASDUK) Smart Contract

This repository contains the non-OpenZeppelin Solidity code used for the minting of Dastardly Ducks NFTs.

The entire 10k minted out in less than 6 hours, and the contract was praised for being ⛽️ low gas, particularly on the 
batch mints.

## Alternate ERC-721A

The reality is the current ERC-721 implementation is poorly suited for batch mintings. The ERC-721 token standard is simply a 
standardized way of defining how tokens interact with the blockchain. It is one of a handful of standards that can be used for 
NFTs on Ethereum and EVM-compatible blockchains.

The typical ``_safeMint()`` method exposed by the ERC-721 implementation that people are used to takes both an address for the 
NFT and an ID for it. The ``ERC721A.sol`` implementation simplifies what is exposed to our top level contract by asking for a quantity instead, which enables more low-level batching.

This is based on the MIT-licensed work done by the fine sers here: https://www.azuki.com/erc721a

## Deployed Contract

* EtherScan: https://etherscan.io/address/0x5472896e283ebcb13924c659c9db594aa9dc05a4

## Author

* Twitter: https://twitter.com/ExistentialEnso