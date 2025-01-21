# AI Creative Workspace – Smart Contracts Guide

This document provides an overview of the smart contract architecture and setup instructions for the AI Creative Workspace platform.

---

## Overview

The smart contracts in AI Creative Workspace manage the blockchain-based operations such as token issuance, ownership verification, and decentralized governance.

### Technologies Used:

- **Solidity** – For writing Ethereum smart contracts.
- **Hardhat** – For compiling, testing, and deploying contracts.
- **OpenZeppelin** – Secure smart contract libraries.
- **Ethers.js** – For interacting with blockchain networks.
- **Base (Ethereum L2)** – The chosen blockchain network for deployment.

---

## Project Structure

The `smart_contracts/` directory is organized as follows:

smart_contracts/
│
├── contracts/            # Solidity smart contracts
│   ├── CREA_Token.sol     # ERC-20 token contract
│   ├── ContentNFT.sol     # ERC-721 contract for tokenized content
│   ├── Governance.sol     # Contract for decentralized governance
│
├── scripts/              # Deployment and automation scripts
│   ├── deploy.js          # Script to deploy contracts to blockchain
│   ├── interact.js        # Example script for contract interaction
│
├── tests/                # Unit tests for smart contracts
│   ├── token.test.js      # Tests for CREA token contract
│   ├── nft.test.js        # Tests for NFT contract
│   ├── governance.test.js # Tests for governance contract
│
├── deployment/           # Deployment configurations
│   ├── config.json        # Network and contract settings
│
├── hardhat.config.js      # Hardhat configuration file
├── package.json          # Dependencies and scripts
├── .env                  # Environment variables for deployment
├── .gitignore             # Files to ignore in version control
└── README.md              # Smart contract documentation

---

## Installation

Follow these steps to set up the smart contract development environment:

1. Navigate to the `smart_contracts/` directory:

   cd smart_contracts

2. Install dependencies:

   npm install

3. Set up environment variables:

   Create a `.env` file and include the following keys:

