# Portfolio NFT Marketplace end to end
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

* Marketplace.js
* Navbar.js
* NFTpage.js
* NFTTile.js
* Profile.js
* SellNFT.js

-------------------------------------------------------------------------------------------------------------

3. Make test and work on better fuctions of bottons and interactions on IFPS and Alchemy SDK conenctions, .env .

Errors to fix and possible solutions:

* GetIpfsUrlFromPinata: where does it come from?
* updateDataFetched : NTFpage.js line 40
* deploy.js : where the Process line 25 comes from
* testing.js import ethers
* navbar.js : Opens 3 times, use effects without dependency array, change to empty array.
* Connect wallets button
-------------------------------------------------------------------------------------------------------------

4. Fix the issues and continue with the integrations.

* SellNFT.js
* Navbar.js
* Marketplace.js
* NFTpage.js

-------------------------------------------------------------------------------------------------------------
# Github Desktop
![image](https://user-images.githubusercontent.com/42863568/236356959-f7cf6de8-1266-4706-bf26-92479c0d15d4.png)


-------------------------------------------------------------------------------------------------------------
# MetaMask Transaccions
![image](https://user-images.githubusercontent.com/42863568/236356772-cd9a511c-c93b-4e7a-923a-75cbabc23cc3.png)

-------------------------------------------------------------------------------------------------------------
# Test

![image](https://user-images.githubusercontent.com/42863568/236356382-cdca43fc-3c18-4eb5-a740-5c21972f4cae.png)

![image](https://user-images.githubusercontent.com/42863568/236356537-ea83f0bb-da49-42fd-bd04-ebe28e112ac1.png)

-------------------------------------------------------------------------------------------------------------

![CV DEV Gonzalo Daniel Aguilar 2023 v1 0-2-1_page-0001](https://github.com/gonzalolater/gonzalolater.github.io/assets/42863568/c893d1d8-77cb-4a22-add4-af8a91d83f87)

# Finish Challenge !
