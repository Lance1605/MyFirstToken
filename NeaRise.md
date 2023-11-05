# Create a Token

This Solidity code is a "Token Creation" program designed to showcase the fundamental syntax and capabilities of the Solidity programming language. The objective of this code is to provide a foundational example for individuals who are new to Solidity and wish to gain a basic understanding of its workings.

## Description

This code represents a basic Solidity contract, a programming language employed for creating smart contracts on the Ethereum blockchain. The contract contains functions related to token minting and burning. It functions as an uncomplicated and direct initiation to Solidity programming, providing a starting point for more intricate projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    string public name;
    string public symbol;
    uint public totalSupply;

    mapping(address => uint) public balances;

    constructor() {
        name = "NEARISE";
        symbol = "NRY";
        totalSupply = 1000000000; // 1 Billion tokens
        balances[msg.sender] = totalSupply;
    }

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_address] -= _value;
    }

}
```

To compile the code, access the "Solidity Compiler" tab located in the left-hand sidebar. Ensure that the "Compiler" option is configured to "0.8.18" (or another compatible version), and proceed by clicking the "Compile NRY-MY TOKEN.sol" button.

After the code has been successfully compiled, you can initiate the contract deployment by navigating to the "Deploy & Run Transactions" tab within the left-hand sidebar. Choose the "MYTOKEN" contract from the dropdown menu, and then execute the deployment process by clicking the "Deploy" button.

Upon the successful deployment of the contract, make sure to copy its address. You can then interact with it by invoking the mint, burn, and balance functions. Access the "MYTOKEN" contract in the left-hand sidebar, and proceed to input values to examine the functionality of these functions.

## Authors

Kristian Marc Lance Nery  


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
