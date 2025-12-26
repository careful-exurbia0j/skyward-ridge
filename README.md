# Skyward Ridge (Built for Base)

Skyward Ridge is a browser-based tool that allows you to validate network identity, inspect balances, view blocks, and interact with deployed contracts on Base Mainnet and Base Sepolia. It uses Coinbase Wallet SDK for seamless wallet integration and verifies results through Basescan.

---

## Key Features

- **Coinbase Wallet SDK integration** for wallet access via EIP-1193  
- **Validation of Base chain IDs** for Mainnet (8453) and Sepolia (84532)  
- **Network snapshot** for block details, gas price, and gas usage  
- **Address inspection** for balance, transaction count, and bytecode presence  
- **ERC-20 token inspection** for retrieving token metadata, total supply, and balance  
- **Basescan verification links** for independently verifying addresses and contracts  

---

## Repository

- **app/skyward-ridge.ts**  
  Core browser-based script for interacting with Coinbase Wallet and querying Base RPC for data.

- **config/base.networks.json**  
  Configuration file containing RPC URLs, explorers, and chainIds for Base networks.

- **docs/architecture.md**  
  Design and architecture explanation, including how the project aligns with Base’s read-only principles.

- **contracts/**  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - `control_structure.sol` — a Solidity contract focused on control structures like conditionals and loops
  - `structs.sol` — contract that demonstrates the use of structs

- **package.json**  
  Dependency manifest containing the necessary SDKs and Base ecosystem references.

- **README.md**  
  Full documentation for setting up and using the project.

---

## Supported Networks

- **Base Sepolia**  
  ChainId (decimal): 84532  
  Explorer: [sepolia.basescan.org](https://sepolia.basescan.org)

- **Base Mainnet**  
  ChainId (decimal): 8453  
  Explorer: [basescan.org](https://basescan.org)

---

## Tooling & Dependencies

This repository uses tools from the Base and Coinbase ecosystems:
- **Coinbase Wallet SDK** for wallet integration  
- **OnchainKit** for interacting with Base’s native primitives  
- **Viem** for typed, efficient RPC communication  
- Direct dependencies from **Base** and **Coinbase GitHub repositories**  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

## Contacts

GitHub: [https://github.com/careful-exurbia0j](https://github.com/careful-exurbia0j)  

Email:  careful-exurbia0j@icloud.com	

Public contact (X): [https://x.com/marighoow](https://x.com/marighoow)  

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, the following contracts have been deployed to Base Sepolia to confirm network behavior and tooling compatibility.

Network: Base Sepolia  
ChainId (decimal): 84532  
Explorer: [sepolia.basescan.org](https://sepolia.basescan.org)

**Contract control_structure.sol address**:  
0x2005DCa0518EB4caD06F5B2f5bDCDA12E60202B9

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0x2005DCa0518EB4caD06F5B2f5bDCDA12E60202B9)
- [Code verification](https://sepolia.basescan.org/0x2005DCa0518EB4caD06F5B2f5bDCDA12E60202B9/0#code)

**Contract structs.sol address**:  
0x717594892F800bd61B63Da20483DADFb1ab8dc22

Deployment and verification:
- [Deployment link](https://sepolia.basescan.org/address/0x717594892F800bd61B63Da20483DADFb1ab8dc22)
- [Code verification](https://sepolia.basescan.org/0x717594892F800bd61B63Da20483DADFb1ab8dc22/0#code)

These deployments validate Base tooling compatibility before final production deployment on Mainnet.
