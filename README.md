# ERC20-token
# Project Title:
 A Smart contract to create your own ERC20 token.
# Description:
The Token project uses Solidity to produce a personalised ERC-20 token on the Ethereum network. The ERC-20 token standard establishes a set of guidelines and conduct that all ERC-20 tokens have to adhere to, and ERC-20 tokens are fungible tokens that meet these requirements. The goal of Creating Token is to offer a basic ERC-20 token that exhibits necessary features like minting, transferring, burning, and mechanisms for allowing ownership control. Token ecosystems, token-based economies, and decentralised apps (dApps) can all be integrated with or built upon this token as a foundation for future experimentation.
# Getting Started: 
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. (e.g., Tokensol).Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyToken is ERC20, Ownable {
    constructor() ERC20("MyToken", "MTK") Ownable(msg.sender) {}

    // Only the owner can mint new tokens
    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    // Any user can burn their own tokens
    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}
```

Compile the Contract In the left sidebar, click on the "Solidity Compiler" tab.

Ensure the compiler version is set to 0.8.0 or later (matching the pragma statement in the contract).

Click the "Compile Token.sol" button.

Deploy the Contract In the left sidebar, click on the "Deploy & Run Transactions" tab.




Interact with the ContractAfter deployment, the contract instance will appear in the "Deployed Contracts" section.



Fill in the required constructor parameters:

name: The name of your token (e.g., "MyToken").

symbol: The symbol of your token (e.g., "MTK").

initialSupply: The initial supply of tokens (e.g., 1000000 for 1 million tokens).

Click on the "Transact" button to deploy the contract.

Interact with the Deployed Contract:

Once deployed, you will see your contract listed under "Deployed Contracts".

You can now interact with your contract by expanding its section and using the available functions (e.g., totalSupply, balanceOf, etc.).
