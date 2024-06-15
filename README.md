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

Select the environment. For simplicity, you can use the "JavaScript VM" for testing.

Ensure the contract MyToken is selected in the dropdown.

Click the "Deploy" button.

Interact with the ContractAfter deployment, the contract instance will appear in the "Deployed Contracts" section.

Expand the deployed contract to see available functions.

Mint Tokens Only the owner (the address that deployed the contract) can mint tokens.

In the mint function input, enter the recipient address and the amount to mint.

Click the "transact" button to mint tokens.

Transfer Tokens Use the standard ERC-20 transfer function.

Enter the recipient address and the amount to transfer.

Click the "transact" button to transfer tokens.

Burn Tokens Any user can call the burn function.

Enter the amount of tokens to burn.

Click the "transact" button to burn tokens from the caller's balance.
