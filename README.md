# Basic NFT Marketplace end to end

# Challenge-Loty.io
* Building a MarketPlace 
Here is the technical exercise. This challenger, let me know if you have any questions, you can also add me by WhatsApp without problem +1 111 111 1111:

# Build an NFTS marketplace

* The objective of this project is to create a marketplace that allows users to buy, sell NFTs as well as view their own NFTs using blockchain technology. The application must be built using Next.js and integrate with a smart contract deployed on the Base test network.

# The requirements are:
- The user must be able to connect their wallet based on testnet
- User should be able to see available nfts
- The user must be able to sell their own nfts at X price
- The user must be able to buy nfts at the price provided.
- As for the visual part, any framework that is simple can be used, it doesn't matter if it is a very MVP version, more attention will be paid to the coordination of the features than to the form.
- You can use any tool, but we will talk in detail about the solution.

-------------------------------------------------------------------------------------------------------------

1. Making The Smart Contract

Functions in the smart contract NFTMarketplace.sol

* createToken()       - Top level function when creating a token for the first time.
* createListedToken() - Helps create the object of type ListedToken for the NFT and Update the idToListedToken mapping.
* getAllNFTs()        - get all the NFTs from the current user on the marketplace.
* getMyNFTs()         - get all the NFTs from the current user on the marketplace.
* executeSale()       - the function that executes the sale on the marketplace.

![image](https://user-images.githubusercontent.com/42863568/235653253-d4014c7d-2bc0-49c5-a102-fd7967269482.png)


-------------------------------------------------------------------------------------------------------------

2. Work on components

Marketplace.js
Navbar.js
NFTpage.js
NFTTile.js
Profile.js
SellNFT.js

-------------------------------------------------------------------------------------------------------------

3. Tomorrow
Make test and work on better fuctions of bottons and interactions on IFPS and Alchemy SDK conenctions, .env .