# **MyToken Contract**
This Solidity script exemplifies a basic "MyToken" smart contract, showcasing fundamental token operations such as minting and burning on the Ethereum blockchain. It is designed as an introductory guide for beginners to grasp the essentials of token contracts in Solidity.

**Overview**
This script is a Solidity-based smart contract for Ethereum, defining a token with a specific name, abbreviation, and total supply. It incorporates functions for minting new tokens and burning existing ones. This contract serves as a practical entry point to Solidity development and can be expanded into more sophisticated token projects.

**Requirements**
The contract includes:

Public variables to store the token's name, abbreviation, and total supply.
A mapping to track the balance of each address (address => uint).
A mint function that accepts an address and a value, increasing the total supply and the balance of the given address.
A burn function that also takes an address and a value, decreasing the total supply and the balance of the specified address, with checks to ensure sufficient balance.
Source Code
solidity
Copy code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

/*
    REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).
    2. Your contract will have a mapping of addresses to balances (address => uint).
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance of the “sender” address by that amount.
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint function. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // Public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

**Getting Started**
**Running the Program**
To execute this contract, you can use Remix, a web-based Solidity IDE. Follow these steps:

Open the Remix IDE at Remix Ethereum.
Create a new file by clicking on the "+" icon in the left-hand sidebar and save it with a .sol extension (e.g., MyToken.sol).
Paste the provided Solidity code into the new file.
Compiling the Code
Navigate to the "Solidity Compiler" tab in the left-hand sidebar.
Ensure the "Compiler" option is set to "0.8.18" (or a compatible version).
Click the "Compile MyToken.sol" button.
Deploying the Contract
Go to the "Deploy & Run Transactions" tab in the left-hand sidebar.
Select the "MyToken" contract from the dropdown menu.
Click on the "Deploy" button.
Interacting with the Contract
After deployment, you can interact with the contract by invoking the mint and burn functions. For minting tokens, input an address and a value in the mint function. Similarly, for burning tokens, provide an address and a value in the burn function. Ensure the address has sufficient balance before burning tokens.

**Author **
Amrit@crafter
**License**
This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to customize this README file further according to your preferences or additional details about your project.





