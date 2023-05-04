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

* Marketplace.js
* Navbar.js
* NFTpage.js
* NFTTile.js
* Profile.js
* SellNFT.js

-------------------------------------------------------------------------------------------------------------

3. Tomorrow
Make test and work on better fuctions of bottons and interactions on IFPS and Alchemy SDK conenctions, .env .

Errores a solucionar y posibles soluciones:

GetIpfsUrlFromPinata : de donde sale ?
updateDataFetched : NTFpage.js linea 40
deploy.js : de donde sale el Process linea 25
testing.js importar ethers
navbar.js : Se abre 3 veces, use effects sin array de dependecias, cambiar por un array vacio.
Boton connect wallets
-------------------------------------------------

if(!dataFetched) getAllNFTs()
En Maketplace.js
necesita estar dentro de un useEffect
useEffect(() => {
        if(!dataFetched) getAllNFTs()
    }, []);

--------------------------------------------------

NavBar.js

import fullLogo from '../full_logo.png';
import {
  Link,
} from "react-router-dom";
import { useEffect, useState } from 'react';
import { useLocation } from 'react-router';

function Navbar() {

  const [connected, toggleConnect] = useState(false);
  const location = useLocation();
  const [currAddress, updateAddress] = useState('');

  async function getAddress() {
    const ethers = require("ethers");
    const provider = new ethers.providers.Web3Provider(window.ethereum);
    const signer = provider.getSigner();
    let addr
    try {
      addr = await signer.getAddress();
    }
    catch(err) {
      console.log(err);
      return;
    }
    updateAddress(addr);
  }
  async function connectWebsite() {
      const chainId = await window.ethereum.request({ method: 'eth_chainId' });
      if(chainId !== '0x5')
      {
        //alert('Incorrect network! Switch your metamask network to Rinkeby');
        await window.ethereum.request({
          method: 'wallet_switchEthereumChain',
          params: [{ chainId: '0x5' }],
      })
      }
      try{
        await window.ethereum.request({ method: 'eth_requestAccounts' })
          .then(() => {
            getAddress();
            toggleConnect(true);
          });
      } catch(err) {
        window.alert(err)
      }
  }
  useEffect(() => {
    if(currAddress)
      toggleConnect(true);
  }, [currAddress])

  useEffect(() => {
    if(window.ethereum === undefined)
      return;
    let val = window.ethereum.isConnected();
    !val && connectWebsite()
    val && getAddress()

    window.ethereum.on('accountsChanged', function(accounts){
      window.location.replace(location.pathname)
    })
  }, [])


    return (
      <div className="">
        <nav className="w-screen">
          <ul className='flex items-end justify-between py-3 bg-transparent text-white pr-5'>
          <li className='flex items-end ml-5 pb-2'>
            <Link to="/">
            <img src={fullLogo} alt="" width={120} height={120} className="inline-block -mt-2"/>
            <div className='inline-block font-bold text-xl ml-2'>
              NFT Marketplace
            </div>
            </Link>
          </li>
          <li className='w-2/6'>
            <ul className='lg:flex justify-between font-bold mr-10 text-lg'>
              {location.pathname === "/" ? 
              <li className='border-b-2 hover:pb-0 p-2'>
                <Link to="/">Marketplace</Link>
              </li>
              :
              <li className='hover:border-b-2 hover:pb-0 p-2'>
                <Link to="/">Marketplace</Link>
              </li>              
              }
              {location.pathname === "/sellNFT" ? 
              <li className='border-b-2 hover:pb-0 p-2'>
                <Link to="/sellNFT">List My NFT</Link>
              </li>
              :
              <li className='hover:border-b-2 hover:pb-0 p-2'>
                <Link to="/sellNFT">List My NFT</Link>
              </li>              
              }              
              {location.pathname === "/profile" ? 
              <li className='border-b-2 hover:pb-0 p-2'>
                <Link to="/profile">Profile</Link>
              </li>
              :
              <li className='hover:border-b-2 hover:pb-0 p-2'>
                <Link to="/profile">Profile</Link>
              </li>              
              }  
              <li>
                <button 
                onClick={connectWebsite}
                className={`${connected?   "hover:bg-green-70 bg-green-500" : "bg-blue-500 hover:bg-blue-700" } enableEthereumButton text-white font-bold py-2 px-4 rounded text-sm`}>
                  {connected? "Connected":"Connect Wallet"}
                </button>
              </li>
            </ul>
          </li>
          </ul>
        </nav>
        <div className='text-white text-bold text-right mr-10 text-sm'>
          {currAddress !== "0x" ? "Connected to":"Not Connected. Please login to view NFTs"} {currAddress !== "0x" ? (currAddress.substring(0,15)+'...'):""}
        </div>
      </div>
    );
  }

  export default Navbar;

-------------------------------------------------------------------------------

export const GetIpfsUrlFromPinata = (url) => {
    const pinataUrl = "https://gateway.pinata.cloud/ipfs/";
    const ipfsUrl = "ipfs://";
    return url.replace(pinataUrl, ipfsUrl);
}

maketplace y NFTPage.js 
import { GetIpfsUrlFromPinata } from "../pinata";

Revisar esta funcion.

-------------------------------------------------------------------------------
