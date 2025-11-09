🏥 Patient Records DApp

A decentralized application (DApp) built on Ethereum to manage and access patient medical records securely. This guide will help you set up, deploy, and run the project locally using Ganache, MetaMask, and Remix IDE.

🚀 Getting Started
1. Clone the Repository
git clone <your-repository-url>
cd <project-folder>

2. Install Dependencies

Install all required dependencies:

npm install

⚙️ Local Blockchain Setup (Ganache + MetaMask)
3. Install Ganache

Download and install Ganache (GUI version recommended) from https://trufflesuite.com/ganache
.

Launch Ganache and create a New Workspace / Quickstart Ethereum project.

Note the RPC Server (usually HTTP://127.0.0.1:7545) and the list of test accounts.

4. Configure MetaMask

Install the MetaMask browser extension if you don’t have it.
👉 https://metamask.io/download/

Create a new wallet (or import an existing one).

Add a new network for Ganache:

Network Name: Ganache Localhost
New RPC URL: http://127.0.0.1:7545
Chain ID: 1337 (or as shown in Ganache)
Currency Symbol: ETH


From Ganache, copy a private key from one of the accounts and import it into MetaMask using “Import Account”.

🧱 Smart Contract Deployment
5. Open Remix IDE

Go to Remix Ethereum IDE
.

6. Load and Compile the Contract

Upload the Patients.sol file (from your project’s contracts/ folder) into Remix.

Select the correct Solidity compiler version (as used in your project).

Click Compile Patients.sol.

7. Deploy the Contract

In the Deploy & Run Transactions tab:

Select Environment: Injected Web3 (to connect Remix with MetaMask).

Choose your MetaMask account (connected to Ganache).

Click Deploy and confirm the transaction in MetaMask.

Once deployed, copy the Contract Address and Network ID.

🧩 Connect Frontend with Deployed Contract
8. Update ABI and Contract Info

In Remix, go to the Compiled Contracts section → ABI → click Copy ABI.

In your project, open the src folder and create/update a file (e.g., PatientABI.json):

{
  "abi": [ /* paste ABI here */ ],
  "networks": {
    "5777": {  // Replace with your Ganache Network ID
      "address": "0xYourDeployedContractAddress"
    }
  }
}


Save the file.

💻 Run the Frontend
9. Start the Application

Run the following command:

npm run start


Your DApp will open at:
👉 http://localhost:3000

🧠 Troubleshooting

No balance in MetaMask: Make sure you imported the private key from Ganache, not just created a new wallet.

Contract not found: Verify the network ID in PatientABI.json matches the one from Ganache.

Remix connection failed: Ensure MetaMask is connected to the same Ganache RPC network.