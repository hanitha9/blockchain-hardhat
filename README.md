# Hardhat Setup and Execution for Blockchain Simulation
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
Ensure that you have Node.js and npm installed. You can check your installation by running:
```sh
node -v
npm -v
```
## Step-by-Step Setup and Execution

### 1. Initialize the Project
Create a new Hardhat project:
```bash
mkdir blockchain-hardhat
cd blockchain-hardhat
```
Select "Create a JavaScript project" and accept defaults. This creates `package.json`, `hardhat.config.js`, `scripts/`, and `contracts/`.

## Initialize Hardhat
To create a new Hardhat project, run:
```sh
npx hardhat
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
Paste the  `SimpleBlockchain.sol` code
Save and close.

### 4. Create the Deployment Script
Create and edit `scripts/deploy.js`:
```bash
cd ..\scripts
notepad deploy.js
```
Paste the `deploy.js` code
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
### output:
  # output on terminal after node launch
   ![image](https://github.com/user-attachments/assets/10b16d80-92eb-4306-b2e8-a4be113420a0)
  # output on terminal 2
![image](https://github.com/user-attachments/assets/d6a6fccd-d20b-4107-a040-9bcadd1d0d44)

### 7.Final Output
```sh
C:\Users\HANITHA\blockchain-hardhat>npx hardhat run scripts/deploy.js --network hardhat
SimpleBlockchain deployed to: 0x5FbDB2315678afecb367f032d93F642f64180aa3
----------------------------------------
Genesis block created. Chain length: 1
Genesis Block:
  Index: 0
  Timestamp: 1742922397
  Hash: 0x0094132d8db0beb41d9a7f5fa2668b1e4fdc0476e7e088f63e5fca8fa8429e02
----------------------------------------
Block #1 added. Chain length: 2
Block #1:
  Index: 1
  Timestamp: 1742922398
  Hash: 0x007900810a8e7aa206c73ccd8cf3d104c03d9c1caf27adc591ddad5554257bf2
  PreviousHash: 0x0094132d8db0beb41d9a7f5fa2668b1e4fdc0476e7e088f63e5fca8fa8429e02
----------------------------------------
Block #2 added. Chain length: 3
Block #2:
  Index: 2
  Timestamp: 1742922399
  Hash: 0x00f4f324714014d17edf4ecdd04260854d0cc3defa5df96f3b708bcb2f3c3f0f
  PreviousHash: 0x007900810a8e7aa206c73ccd8cf3d104c03d9c1caf27adc591ddad5554257bf2
----------------------------------------
Chain validity before tampering: true
----------------------------------------
Block #1 tampered. Chain length: 3
Block #1 (Tampered):
  Index: 1
  Timestamp: 1742922398
  Hash: 0xfb313c176259dc62808662c2c607d8dbd9fcce06f694b70023963cfe33bdfade
----------------------------------------
Chain validity after tampering: false
----------------------------------------

C:\Users\HANITHA\blockchain-hardhat>
```
### 8. Push to GitHub
Ensure your local files match the versions above.
```bash
git init
git add .
git commit -m "Final SimpleBlockchain simulation with Hardhat"
git remote add origin <your-repo-url>
git push -u origin main
```
