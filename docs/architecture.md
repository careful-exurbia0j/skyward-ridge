# Skyward Ridge — Architecture Overview

## Overview

Skyward Ridge is designed with **Base's ecosystem** at its core, specifically focusing on **Base Mainnet** for live deployments and **Base Sepolia** for testing. This document outlines the design principles, architecture, and how the project aligns with Base’s network and read-only principles.

---

## Base Network Alignment

Skyward Ridge interacts exclusively with **Base** networks:
- **Base Mainnet** (chainId: `8453`) for live transactions.
- **Base Sepolia** (chainId: `84532`) for testing and validation purposes.

### RPC and Explorer Configuration

All network configurations, including **RPC URLs**, **chain IDs**, and **explorer URLs**, are centralized in the `config/base.networks.json` file. This centralized configuration ensures:
- **No hardcoding** of network values across the project.
- **Easy configuration management** for different environments (mainnet, testnet).

Network metadata is critical to ensuring that the project can scale and be easily maintained as Base networks evolve.

---

## Read-only Principles

The project adheres to **Base's read-only principles**, which limit the interactions to non-mutating operations. This approach helps minimize the attack surface and keeps the project simple and deterministic.

### Supported Operations:
- **Balance checks** for native assets and tokens.
- **Smart contract metadata reading**, such as verifying contract code.
- **Chain and block data queries**, including retrieving the latest block number and timestamp.
  
These operations ensure the project remains secure and compliant with **read-only** constraints, while also allowing for real-time data retrieval.

### Disallowed Operations:
- **Transaction sending** or **contract interactions** that modify on-chain data are outside the scope of this project.
- **Private key management** is avoided to reduce the risk of exposure.

---

## Architectural Rationale

### Centralized Configuration
The use of a centralized `config/base.networks.json` file ensures all network-related data is easily configurable and can be updated without needing to refactor the codebase.

This approach also allows for the easy addition of future Base networks with minimal disruption to existing functionality.

### Minimal Dependencies
Skyward Ridge is built with minimal dependencies to ensure a small attack surface and to make the project easier to maintain. Dependencies are carefully selected based on Base's ecosystem compatibility, and no unnecessary external libraries are included.

### Future-Proofing
The project’s architecture is designed to be easily extendable. Future support for new Base testnets or mainnets can be achieved by simply adding the corresponding configurations in the `config/base.networks.json` file.

---

## Design Tradeoffs

**Pros:**
- Simple and secure approach by limiting interactions to read-only operations.
- Clear separation between configuration, logic, and validation.
- Easy to scale with minimal changes required when Base adds new networks.

**Cons:**
- Limited to non-mutating interactions, which may restrict some use cases.
- Does not provide support for write-side interactions at this stage.

These tradeoffs are intentional to maintain a focus on security, simplicity, and compliance with Base's network principles.

---

## Future Considerations

1. **Transaction Simulation**:  
   While the project is currently read-only, there may be a future need for simulating transactions on Base networks, particularly for testing contract interactions.

2. **Extended Network Support**:  
   As new Base networks emerge, the project will adapt by adding the necessary configurations and ensuring compatibility with future environments.

_Last updated: initial scaffold_
