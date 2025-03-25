
#  Blockchain Simulation using hardhat
 
A basic blockchain simulation implemented in Solidity and deployed using Hardhat. This project demonstrates core blockchain concepts including block structure, hashing, chain validation, and a simple Proof-of-Work mechanism.

## Objective
Demonstrate understanding of programming, problem-solving, and blockchain concepts by creating a simulation with linked blocks, hash generation, and tampering detection.

## Features
- **Block Structure**: Index, timestamp, transactions, previous hash, current hash, and nonce.
- **Hashing**: Uses `keccak256` to generate block hashes.
- **Blockchain Management**: Adds blocks and validates chain integrity.
- **Proof-of-Work**: Simple mechanism requiring the hash’s first byte to be `0`.
- **Output**: Prints block details and demonstrates tampering detection.

## Prerequisites
- **Node.js**: Version 16 or higher.
- **npm**: Comes with Node.js.
- **Windows**: Commands assume a Windows environment (adapt for other OS if needed).

## Step-by-Step Setup and Execution

### 1. Initialize the Project
Create a new Hardhat project:
```bash
mkdir blockchain-hardhat
cd blockchain-hardhat
npx hardhat init
```
Select "Create a JavaScript project" and accept defaults. This creates `package.json`, `hardhat.config.js`, `scripts/`, and `contracts/`.

### 2. Install Dependencies
Install Hardhat and required packages (updates `package.json` and generates `package-lock.json`):
```bash
npm install --save-dev hardhat @nomicfoundation/hardhat-toolbox
```

### 3. Create the Smart Contract
Create and edit `contracts/SimpleBlockchain.sol`:
```bash
cd contracts
notepad SimpleBlockchain.sol
```
Paste the latest `SimpleBlockchain.sol` code (see below).
Save and close.

### 4. Create the Deployment Script
Create and edit `scripts/deploy.js`:
```bash
cd ..\scripts
notepad deploy.js
```
Paste the latest `deploy.js` code (see below).
Save and close.

### 5. Compile the Contract
Compile the Solidity code:
```bash
cd ..
npx hardhat compile
```
Expected: "Compiled 1 Solidity file successfully" (may show a warning about unused `_unusedHash`, which is fine).

### 6. Debug and Test (Historical Commands)
During development, we used these commands to debug issues:

Check for running nodes (if `EADDRINUSE` occurred):
```bash
netstat -aon | findstr :8545
taskkill /PID <PID> /F
```
Re-run node after stopping:
```bash
npx hardhat node
```
Deploy to test fixes:
```bash
npx hardhat run scripts/deploy.js --network hardhat
```

### 7. Run the Final Simulation
Start the Hardhat node in one terminal:
```bash
npx hardhat node
```
Deploy the contract in a second terminal:
```bash
cd C:\Users\HANITHA\blockchain-hardhat
npx hardhat run scripts/deploy.js --network hardhat
```
Expected output: Contract deployment details, including addresses and transaction hashes.

### 8. Push to GitHub
Ensure your local files match the versions above.
```bash
git init
git add .
git commit -m "Final SimpleBlockchain simulation with Hardhat"
git remote add origin <your-repo-url>
git push -u origin main
```


