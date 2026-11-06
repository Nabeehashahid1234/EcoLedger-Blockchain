# EchoLedger — Decentralized Web3 Guestbook Application
---

## 📌 1. Project Overview & Business Value

**EchoLedger** is a full-stack decentralized guestbook application (dApp) deployed on the **Ethereum Sepolia Testnet**. It demonstrates how immutable smart contracts interact with a responsive web-based frontend interface and browser-based Web3 wallet providers like MetaMask.

### Key Features
* **Immutable Message Storage:** Every note submitted by a user is recorded permanently on the Sepolia blockchain along with the author's public Ethereum address and a block timestamp.
* **MetaMask Integration:** Smooth account detection, connection authorization, and automatic network checking/switching to Sepolia (`chainId: 0xaa36a7`).
* **Real-time On-Chain Data Fetching:** Reads the global note count, user-specific note counts, and paginated historic messages directly from the deployed contract.
* **Modern Web3 Interface:** Fully styled using a dark-emerald glassmorphic theme with real-time character counting, transaction status banners, and visual feedback.

---

## 📁 2. Repository & Folder Structure

Per assignment requirements, the project is structured as follows:

```text
EchoLedger_Assignment2/
├── SmartContract.sol          # Solidity contract source code (v0.8.20)
├── index.html                 # Single-page Web3 HTML frontend
├── style.css                  # External CSS styling (Dark Emerald Glassmorphic)
├── README.md                  # Detailed project documentation and setup guide
└── screenshots/               # Submission visual proof
    ├── 01-contract-deployment.png   # Deployed contract & Sepolia address in Remix IDE
    ├── 02-wallet-connection.png     # Web UI with active MetaMask connection & Sepolia status
    └── 03-transaction-success.png  # Web UI showing confirmed write transaction & note feed
```

---

## 📜 3. Smart Contract Architecture (`SmartContract.sol`)

The smart contract `DecentralizedGuestbook` was written in Solidity `^0.8.20` and compiled with default optimization settings.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract DecentralizedGuestbook {
    struct Note {
        address author;
        string message;
        uint256 timestamp;
    }

    Note[] private notes;
    ...
}
```

### Function Breakdown

| Function Signature | Type | Visibility | Description |
|---|---|---|---|
| `postNote(string calldata _message)` | **Write** | `external` | Stores a message string on-chain. Validates that the input is non-empty and does not exceed 280 bytes. Attaches `msg.sender` and `block.timestamp`. |
| `getNoteCount()` | **Read** | `external view` | Returns the total length of the `notes` array (`uint256`). |
| `getNote(uint256 _index)` | **Read** | `external view` | Returns `(address author, string message, uint256 timestamp)` for a given note index. Validates array bounds. |
| `getMyNoteCount()` | **Read** | `external view` | Iterates through the stored notes to count how many were posted specifically by `msg.sender`. |

---

## 🔗 4. Deployed Smart Contract Details

- **Blockchain Network:** Ethereum Sepolia Testnet
- **Contract Name:** `DecentralizedGuestbook`
- **Deployed Contract Address:** `0x41ec5a70Eb6Cc642F0Af86633f5B9cf7fCbeAa0D`
- **Compiler Version:** Solidity v0.8.20
- **Etherscan Block Explorer:** [https://sepolia.etherscan.io/address/0x41ec5a70Eb6Cc642F0Af86633f5B9cf7fCbeAa0D](https://sepolia.etherscan.io/address/0x41ec5a70Eb6Cc642F0Af86633f5B9cf7fCbeAa0D)

---

## 🎨 5. Frontend & HTML Requirements Verification

The single-page web interface (`index.html`) fulfills all technical HTML element requirements specified in the rubric:

1. **Headings (`<h1>` – `<h3>`):** Included for page title, hero section, statistics, form panels, and instructions.
2. **Paragraphs (`<p>`):** Used for descriptive text, status updates, character counters, and message card content.
3. **Lists (`<ol>` / `<li>`):** Step-by-step ordered list explaining how the dApp operates under the "How EchoLedger Works" section.
4. **Links (`<a>`):** Hyperlink pointing to the Sepolia Etherscan contract verification page.
5. **Buttons (`<button>`):** Connect Wallet, Post Message, and Refresh Feed buttons linked to JavaScript event handlers.
6. **Images (`<img>`):** Hero section workspace image with rounded borders and responsive sizing.
7. **Script Tag (`<script>`):** CDN script importing Ethers.js v5 (`ethers@5.7.2`) and an internal script block handling Web3 interaction logic.

---

## 🛠️ 6. Setup & Execution Guide

### Step 1: Prerequisites
- **Web Browser:** Google Chrome, Brave, Microsoft Edge, or Firefox.
- **Wallet Extension:** [MetaMask Installed](https://metamask.io/) and unlocked.
- **Test Funds:** Sepolia Test ETH in your MetaMask wallet (obtainable for free via Google Cloud Sepolia Faucet or Alchemy Sepolia Faucet).
- **Code Editor:** Visual Studio Code with the **Live Server** extension installed.

### Step 2: Running the dApp
1. Extract the project ZIP folder onto your local system.
2. Open the project folder in **VS Code**.
3. Right-click `index.html` in VS Code's file tree and select **Open with Live Server**.
   > ⚠️ **Important:** Browser extensions like MetaMask restrict access on raw file paths (`file:///`). Running the application via Live Server hosts it over a local development server (`http://127.0.0.1:5500`), enabling Web3 provider access.
4. Click **Connect Wallet** in the top navigation bar.
5. Approve the MetaMask connection prompt. If your wallet is connected to a different network, approve the prompt to switch to **Sepolia**.
6. Enter a test message (up to 280 characters) into the textarea and click **Post Message**.
7. Confirm the transaction gas fee in MetaMask.
8. Wait for block confirmation (~10–15 seconds). The page status will display a green success notification, increment the note counters, and display your message at the top of the feed.

---

## 📸 7. Screenshots Summary

All required screenshot evidence is saved inside the `/screenshots` directory:
- `01-contract-deployment.png`: Proves contract deployment address and transaction receipt in Remix IDE.
- `02-wallet-connection.png`: Captures the EchoLedger webpage with an active MetaMask connection showing the connected wallet address and Sepolia network badge.
- `03-transaction-success.png`: Shows a confirmed write transaction with the updated total count and message feed card rendered on-screen.

---
