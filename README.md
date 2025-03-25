# Hardhat Setup and Execution for Blockchain Simulation

## Prerequisites
Ensure that you have Node.js and npm installed. You can check your installation by running:
```sh
node -v
npm -v
```

## Install Hardhat
To set up Hardhat in your project directory, run:
```sh
mkdir blockchain-hardhat
cd blockchain-hardhat
npm init -y
npm install --save-dev hardhat
```

## Initialize Hardhat
To create a new Hardhat project, run:
```sh
npx hardhat
```
Choose "Create a basic sample project" and follow the prompts.

## Install Dependencies
For blockchain development, install the necessary dependencies:
```sh
npm install --save-dev @nomicfoundation/hardhat-toolbox
```

## Create a Smart Contract
Navigate to the `contracts/` directory and create `SimpleBlockchain.sol`. Define your Solidity smart contract inside it.

## Compile the Smart Contract
To compile the contract, use:
```sh
npx hardhat compile
```

## Deploy the Smart Contract
Create a deployment script inside the `scripts/` directory, such as `deploy.js`. Then, deploy using:
```sh
npx hardhat run scripts/deploy.js --network hardhat
```

## Running the Simulation
After deployment, execute the blockchain simulation by modifying `deploy.js` to include block creation and validation. Then, run:
```sh
npx hardhat run scripts/deploy.js --network hardhat
```

## Final Output
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

