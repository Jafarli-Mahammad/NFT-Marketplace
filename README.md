# NFT Marketplace

A decentralized application (dApp) and supporting backend infrastructure for minting, listing, buying, and selling Non-Fungible Tokens (NFTs). 

This system splits responsibilities between trustless on-chain execution and a robust off-chain backend designed to index events, serve metadata, and handle user profiles without bloating the blockchain state.

## 🏗 Architecture

The repository separates on-chain protocols from off-chain services. The backend strictly follows **Clean/Onion Architecture** and utilizes **CQRS (Command Query Responsibility Segregation)** to independently scale high-volume read operations (like exploring NFT galleries) from complex write operations (like processing blockchain webhooks).

### System Components

*   **Smart Contracts:** Handles the core ERC-721/ERC-1155 logic, token minting, and marketplace escrow mechanisms.
*   **Off-Chain API:** .NET backend structured with MediatR and EF Core. It listens to blockchain events, caches ownership states, and serves high-performance metadata to the frontend.
*   **Frontend Client:** User interface for wallet connection and marketplace interactions.

## ⚙️ Core Technologies

*   **Backend Engine:** .NET 8, ASP.NET Core Web API
*   **Data & Messaging:** Entity Framework Core (EF Core), MediatR
*   **Identity & Auth:** ASP.NET Core Identity (for off-chain user profiles/sessions)
*   **Smart Contracts:** *(e.g., Solidity, Hardhat, or Foundry)*
*   **Web3 Integration:** *(e.g., Nethereum, ethers.js, or wagmi)*

## 🚀 Getting Started

### Prerequisites

*   [.NET 8.0 SDK](https://dotnet.microsoft.com/download)
*   Node.js (for smart contract tooling)
*   A local blockchain environment (e.g., Anvil or Hardhat Network)

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Jafarli-Mahammad/NFT-Marketplace.git](https://github.com/Jafarli-Mahammad/NFT-Marketplace.git)
   cd NFT-Marketplace
