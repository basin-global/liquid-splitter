# Liquid Splitter Concept Note

Based on the [0x Splits Liquid Split](https://github.com/basin-global/splits-liquid-template/tree/main) concept but expanded to work with any, and multiple, ERC721 and/or ERC1155 contracts. With Liquid Splitter there no need for each ERC721 or ERC1155 to be the `split` and will be compatible with any NFT Contract regardless of minter orgin or marketplace.

Overall, the Liquid Splitter allows for value, in ERC20, to be sent across any NFT collection to the NFT owners without the need to define % allocations or snapshot of

## Concept

Rather than making the NFT contract (`LS1155.sol`) the `split`, the Liquid Splitter, as the `split`, will sit above the ERC1155 or ERC721 contract(s) (_NFTContract_) and will split ERC20 based across _all_ `accounts` (_unique list of NFT holders_) based on `percentAllocations`. In Liquid Splitter, `accounts` are the total token supply of one or many `NFTContract`. 

The Liquid Splitter can pay one `NFTContract` or pay multiple `NFTContract` in any combination: i.e. `NFTContract` 1 0xERC1155, `NFTContract` 2 0xERC721, `NFTContract` 3 0xERC721, `NFTContract` 4 0xERC1155, ....n. The Liquid Spliter would treat each `NFTContract` equally with no % allocation having to be set at `createSplit`. Split amounts are calculated without change to `percentAllocations` just a change to how `accounts` are calculated.


## TODO
1) solict feedback from Will, Abram, Sweetman, and others
2) Rewrite or Substitute LS1155.sol to be the `split`
3) Changes to LiquidSplit.sol `distributeFunds` to define `accounts` as sum tokens of `NFTContract`. Possibly no change to `percentAllocations` or `updateAndDistributeERC20`, just the `accounts` calculation.
