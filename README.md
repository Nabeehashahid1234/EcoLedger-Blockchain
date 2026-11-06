<div align="center">

# ⚡ EchoLedger — Immutable On-Chain Guestbook

> **MG3012 — Blockchain Technology for Business | Assignment 2 (Mini dApp)**  
> *BSFT — 5th Semester*

![Solidity](https://img.shields.io/badge/Solidity-0.8.20-363636?style=for-the-badge&logo=solidity)
![Ethereum](https://img.shields.io/badge/Ethereum-Sepolia_Testnet-3C3C3D?style=for-the-badge&logo=ethereum)
![MetaMask](https://img.shields.io/badge/MetaMask-Connected-F6851B?style=for-the-badge&logo=metamask)
![Ethers.js](https://img.shields.io/badge/Ethers.js-v5.7.2-24292E?style=for-the-badge&logo=javascript)

---

### 🌐 [View Verified Contract on Sepolia Etherscan](https://sepolia.etherscan.io/address/0x41ec5a70Eb6Cc642F0Af86633f5B9cf7fCbeAa0D)

</div>

---

## 📌 Project Overview

**EchoLedger** is a decentralized guestbook application (dApp) deployed on the **Ethereum Sepolia Testnet**. It enables users to securely connect their MetaMask Web3 wallets, store permanent messages directly on the Ethereum blockchain, and fetch stored notes in real time.

### ✨ Key Features
* 🔐 **MetaMask Authentication:** Seamless wallet connection & network validation (`chainId: 0xaa36a7`).
* ✍️ **Immutable Note Publishing:** Permanent state updates on Sepolia via smart contract transaction calls.
* 📊 **Real-Time On-Chain Data:** Reads total global notes and user-specific message counts directly from the blockchain.
* 🎨 **Glassmorphic UI:** Modern dark-emerald interface designed with responsive grids and interactive status feedback.

---

## 🏗️ Architecture & Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Smart Contract** | Solidity `^0.8.20` | On-chain storage logic & data retrieval functions |
| **Blockchain Network** | Ethereum Sepolia | Testnet environment for contract deployment |
| **Web3 Interface** | Ethers.js v5 (`Web3Provider`) | JSON-RPC bridge connecting HTML/JS to MetaMask |
| **Frontend UI** | HTML5 / CSS3 | Responsive glassmorphic visual layout |

---

## 📁 Repository Structure

```text
EcoLedger-Blockchain/
├── SmartContract.sol          # Deployed Solidity smart contract code
├── index.html                 # Single-page Web3 application frontend
├── style.css                  # External dark-emerald stylesheet
├── README.md                  # Project documentation & setup instructions
└── screenshots/               # Application verification evidence
    ├── 01-contract-deployment.png   # Remix deployment proof
    ├── 02-wallet-connection.png     # Frontend UI showing active MetaMask connection
    └── 03-transaction-success.png  # Frontend UI displaying confirmed transaction & note feed
