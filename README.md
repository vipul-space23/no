# Document Verification System Using Blockchain & IPFS 🔒📜

A robust hackathon project that leverages modern web technologies, blockchain smart contracts, and decentralized storage to securely store and verify academic documents such as marksheets. This solution ensures tamper-proof record keeping with role-based access control and optimized gas fee management.

---

## Table of Contents 📑

- [Overview](#overview)
- [Software Requirements](#software-requirements)
- [Smart Contract Deployment & Interaction](#smart-contract-deployment--interaction)
- [File Upload & Hash Storage](#file-upload--hash-storage)
- [Role-Based Access Control](#role-based-access-control)
- [Gas Fees Optimization & Batch Upload Mechanism](#gas-fees-optimization--batch-upload-mechanism)
- [Verifier Gas Fee Payment](#verifier-gas-fee-payment)
- [Setup & Execution](#setup--execution)
- [License](#license)

---

## Overview 📖

This project provides a secure and efficient way to verify academic documents using a hybrid approach:
- **Frontend:** Built with React.js for a dynamic and responsive user interface ⚛️.
- **Backend:** Developed with Node.js, Express.js, and MongoDB for secure API and data management 💻.
- **Blockchain:** Uses Ethereum for immutable storage of document hashes via smart contracts ⛓️.
- **Decentralized Storage:** Utilizes IPFS (via Pinata) to store files off-chain, reducing gas costs 📤.

---

## Software Requirements 🛠️

### Frontend Technologies
- **React.js:**  
  - Dynamic, responsive, and component-based web applications.
  - Enhanced performance via React’s Virtual DOM for efficient reusability.

### Backend Technologies
- **Node.js & Express.js:**  
  - Powerful server-side frameworks for building robust RESTful APIs.
- **MongoDB:**  
  - Database for managing user data and implementing role-based access control (RBAC).

### Blockchain Components
- **Ethereum Blockchain:**  
  - Securely stores document hashes, student names, and PRN.
- **Solidity:**  
  - Language for writing secure smart contracts.
- **Ethers.js:**  
  - Connects the React frontend with Ethereum for transaction signing and interaction.
- **Hardhat:**  
  - A development-friendly environment for compiling, deploying, and testing smart contracts.
- **Ganache:**  
  - Provides a local Ethereum blockchain for testing deployments.
- **MetaMask:**  
  - Manages blockchain accounts and signs transactions securely.

---

## Smart Contract Deployment & Interaction 🚀

- **Smart Contract Development:**  
  The smart contract is written in Solidity and is responsible for securely storing and verifying document hashes. Once recorded, a document’s hash is immutable.

- **Development Environment Setup:**  
  - **Node.js & npm:** For installing dependencies.
  - **Hardhat:** To compile and deploy Solidity contracts.
  - **Ganache:** For local blockchain testing.
  - **Ethers.js:** To bridge the smart contract with the frontend.

- **Deployment Steps:**  
  1. **Initialize the Hardhat project.**
  2. **Develop the smart contract.**
  3. **Compile the contract.**
  4. **Deploy the contract to Ganache.**
  5. **Connect the frontend via Ethers.js to interact with the deployed contract.**

---

## File Upload & Hash Storage 📂🔑

- **Uploading to IPFS:**  
  The PDF marksheet is uploaded to IPFS via Pinata, returning an IPFS hash that serves as the unique file identifier.

- **Document Hashing:**  
  A Keccak-256 hash is generated for the document, ensuring integrity by producing a unique output for any modification.

- **On-Chain Storage:**  
  The IPFS hash, Keccak-256 hash, and student details are stored on Ethereum via the smart contract, ensuring permanent and tamper-proof records.

- **Verification Process:**  
  1. The document is re-hashed using Keccak-256.
  2. The smart contract is queried to check if the hash exists.
  3. A matching hash validates the document; otherwise, it is flagged as tampered.

---

## Role-Based Access Control 🔐

Implemented using Node.js, Express.js, and MongoDB, this system ensures:
- **University Administrators:**  
  - Authorized to upload marksheets and manage document storage.
- **Verifiers:**  
  - Authorized to verify documents only.

Session-based authentication ensures only authorized users access the system, redirecting non-authenticated users to the login page.

---

## Gas Fees Optimization & Batch Upload Mechanism ⛽💡

- **Gas Fee Optimization:**  
  Only the Keccak-256 hash and the IPFS link are stored on-chain, significantly reducing storage costs.

- **Batch Upload Mechanism:**  
  Allows multiple marksheets to be uploaded in a single smart contract call, reducing redundant transactions and minimizing gas fees.

---

## Verifier Gas Fee Payment 💰

- **Cost Distribution:**  
  - **Upload Costs:** Paid by the university when marksheets are uploaded.
  - **Verification Costs:** Paid by the verifier when they verify a document through the `verifyMarksheet()` function.

This ensures a fair distribution of costs across all parties involved.

---

## Setup & Execution 🚀

1. **Clone the Repository:**
   ```bash
   git clone <repository_url>
   cd <project_directory>
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Start Ganache:**
   - Launch Ganache to create a local Ethereum blockchain environment.

4. **Deploy Smart Contracts:**
   ```bash
   npx hardhat run scripts/deploy.js --network ganache
   ```

5. **Run the Application:**
   ```bash
   npm start
   ```

6. **Connect MetaMask:**
   - Ensure MetaMask is configured to the correct network (local or live) for signing transactions.

---

## License 📄

Distributed under the MIT License. See `LICENSE` for more information.

---

Feel free to modify and extend this README as your project evolves. This file provides a professional and engaging overview that will help users and reviewers understand your project's architecture and setup.
