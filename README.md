Deploying Smart Contract In Redbelly Devnet using REMIX 

Contract Address: 0xe0f9f42f6fe340632220730e724c2916cddf7832
Token Name : Meta Token
Token Symbol : Meta


Step 1:
Open your metamask add Redbelly Devnet :
Network Name: Devnet Redbelly

RPC URL: [https://rbn-gcp-us-east5-a-0-b.devnet.redbelly.network:8545/](https://rbn-gcp-australia-southeast1-a-0-b-v2.devnet.redbelly.network:8545)

ChainID: 152

Currency Symbol: RBNT

Block explorer URL: [https://explorer.devnet.redbelly.network](https://explorer.devnet.redbelly.network)

Step 2: 
Get faucet on Redbelly Discord:
Join Redbelly Discord: https://discord.com/invite/redbelly
Go to #devnet-faucet channel
Type /faucet and paste your wallet address 

Step 3:
Go to REMIX:
Create new contract name (MeteToken) 
Remix will create new file "MetaToken.sol"
code:
```solidity
// SPDX-License-Identifier: MIT
   pragma solidity 0.8.17;

   contract Bustaaal {
       string public name = "MetaToken";
       string public symbol = "META";
       uint8 public decimals = 18;
       uint256 public totalSupply = 1000000000;

       mapping (address => uint256) public balances;
       address public owner;

       constructor() {
           owner = msg.sender;
           balances[owner] = totalSupply;
       }

       function transfer(address recipient, uint256 amount) public {
           require(balances[msg.sender] >= amount, "Insufficient balance.");
           balances[msg.sender] -= amount;
           balances[recipient] += amount;
       }
   }
```

Step 4:
Go to Compiler tab:
Use compiler version 0.8.18
Click Compile "MetaToken.sol"
You will see green checkmark on the compiler tab

Step 5:
Go to Deploy & Run Transactions tab:
Change the Environment to Injected Provider
Connect your Metamask to Redbelly Devnet network
Click “ Deploy “ and “Confirm” on your metamask
If you see "gas estimation failed", just continue and click Send Transaction
After successful transaction copy your smart contract address. 
Go to Redbelly Devnet Block Explorer (https://explorer.devnet.redbelly.network/overview) paste your smart contract address

You have just deployed a Smart Contract on Redbelly!
