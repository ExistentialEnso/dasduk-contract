# Dastardly Ducks NFT Smart Contract

This repository contains the non-OpenZeppelin Solidity code used for the minting of Dastardly Ducks NFTs.

The entire 10k minted out in less than 6 hours on January 19th, 2021 through the Dastardly Ducks website.

The contract was widely praised for being ⛽️ low gas, particularly on the batch mints!

## Alternate ERC-721 

The reality is the current ERC-721 implementation is poorly suited for batch mintings. The ERC-721 token standard is simply a 
standardized way of defining how tokens interact with the blockchain. It is one of a handful of standards that can be used for 
NFTs (on Ethereum and EVM-compatible blockchains.)

The typical ``_safeMint()`` function exposed by the ERC-721 implementation that people are used to using takes both an address for the 
NFT and an ID for it. The ``ERC721A.sol`` implementation simplifies what is exposed to our top-level contract by asking for a quantity instead of an ID, which enables low-level batching of the mint.

This is based on the MIT-licensed work done by the fine sers here: https://www.azuki.com/erc721a

## "Unchecked" Code Blocks

More recent versions of Solidity support an ``unchecked`` keyword that lets you disable integer overflow checking. If there is no way 
a variable used in this block could **ever** be subject to overflow, it is a secure way to save some on gas. The blockchain defaults 
to very strong protections against integer overflows when running code for financial security.

The ``require`` statements in these blocks still function as expected as long as there is no way an integer overflow exploit is possible. 
Therefore, it can be a risk when using with user-supplied token amounts, but for wholly internally controlled variables like the number of NFTs minted, there is no reason to worry about integer overflow checking. 

## Dastardly Ducks

* Website: https://www.dastardlyducks.com/
* Twitter: https://www.twitter.com/dastardlyducks
* EtherScan: https://etherscan.io/address/0x5472896e283ebcb13924c659c9db594aa9dc05a4
* OpenSea: https://opensea.io/collection/dastardly-ducks
* LooksRare: https://looksrare.org/collections/0x5472896E283eBCB13924C659C9dB594aA9Dc05A4

## Author

* GitHub: https://github.com/ExistentialEnso
* Twitter: https://twitter.com/ExistentialEnso