# MetaMuse

## Overview
The **MetaMuse** is a decentralized application that allows artists to collaboratively create digital artwork in real-time, mint it as a non-fungible token (NFT) on Lisk, and distribute fractional ownership using Arbitrum. This platform ensures transparent royalty distribution and shared ownership, empowering artists to collaborate creatively and securely.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Setup and Installation](#setup-and-installation)
- [Smart Contract Development](#smart-contract-development)
- [Project Structure](#project-structure)
- [License](#license)

## Features
- **Real-time Collaborative Canvas**: Multiple artists can create and edit artwork in real-time.
- **NFT Minting on Lisk**: The completed artwork is minted as an NFT on the Lisk blockchain.
- **Fractional Ownership on Arbitrum**: Ownership shares and royalties are distributed among collaborators via Arbitrum smart contracts.
- **Decentralized Storage**: Artwork and metadata are stored on IPFS for decentralized, secure storage.

## Tech Stack
- **Blockchain**: Lisk, Arbitrum
- **Smart Contracts**: Solidity, Forge
- **Backend**: Lisk SDK, IPFS (Pinata or Infura)

## Getting Started

### Prerequisites
Make sure you have the following installed:
- [Node.js](https://nodejs.org/) and npm
- [Lisk SDK](https://lisk.io/)
- [Arbitrum Development Environment](https://developer.offchainlabs.com/)
- [IPFS CLI](https://docs.ipfs.io/install/)
- [Foundry & Forge](https://book.getfoundry.sh/)


### Key Features

- **Contributor Shares Assignment**: The owner can assign shares to multiple contributors.
- **NFT Purchase**: The contract allows anyone to buy the NFT by paying to the contract.
- **Automatic Payment Distribution**: Upon purchase, the payment is distributed to all contributors based on their shares.
- **Events**: Emits events for tracking NFT purchases and payments made to contributors.

### Events

- `NFTPurchased(address indexed buyer, uint256 totalPaid, uint256 tokenId)`: Emitted when an NFT is purchased.
- `SharesAssigned(address indexed contributor, uint256 shares)`: Emitted when shares are assigned to a contributor.
- `PaymentDistributed(address indexed contributor, uint256 amount)`: Emitted when payments are distributed to contributors.

### Functions

- `assignShares(address[] memory _contributors, uint256[] memory _shares)`: Allows the owner to assign shares to contributors.
- `buyNFT(uint256 tokenId)`: Allows users to buy the NFT and triggers payment distribution to contributors.

## Setup and Installation
 **Clone the Repository**:
   ```bash
   git clone git@github.com:georgegoldman/metamuse.git
   cd metamuse

### Installation
1. Clone the repository:
   ```
   git clone https://github.com/yourusername/collaborative-nft-art-platform.git
   cd collaborative-nft-art-platform
   ```
Install dependencies:
```
npm install
```
Set up IPFS:

Use Pinata or Infura for IPFS API keys to store artwork and metadata.
### Running the Application
Start the local development server:

```
npm start
```
**Launch Lisk and Arbitrum nodes:**

Follow setup instructions for Lisk SDK and Arbitrum.
Deploy the Arbitrum smart contracts with Forge:

Ensure Forge is installed and set up by following the Foundry book.

**Deploy contracts from the contracts folder:**
```
forge create --rpc-url <ARBITRUM_RPC_URL> --private-key <YOUR_PRIVATE_KEY> src/YourContract.sol:YourContract
```
### Smart Contract Development
Smart contracts in this project handle:

Fractional Ownership: Distributing shares among contributors.
Royalty Distribution: Automatically redistributing royalties to collaborators on resale.
Smart contracts are located in the contracts/ directory. Forge scripts for testing and deployment can be added in script/.

### Project Structure
```
bash
Copy code
collaborative-nft-art-platform/
├── contracts/             
├── src/                   
│   ├── components/        
│   └── services/          
├── script/                
├── README.md
└── package.json
```
### License
This project is licensed under the MIT License - see the LICENSE file for details.


