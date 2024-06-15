# ETH Proof Beginner Assessment 

This Solidity program includes a simple contract which provides a basic implementation of a token contract with minting and burning functionalities.

## Description

This Solidity contract implements basic functionalities for minting and burning tokens on the Ethereum blockchain. It features a minting function to increase the total token supply and allocate tokens to specific addresses. This contract serves as foundational component for creating custom tokens and can be used as a learning resource for understanding Solidity programming and smart contract development.

### Prerequisites

- Access to a web browser
- Internet connection
  
## Getting Started

### Executing program

1. To run this program, we can use Remix at https://remix.ethereum.org/.
2. Create a new file by clicking on the "+" icon in the left-hand sidebar.
3. Save the file with a .sol extension 

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken { 

    // public variables here 
    string public tokenName = "Vaishnavi Singh";
    string public tokenAbbrev = "VS";
    uint256 public totalSupply = 0;

    // mapping variable here
    mapping(address => uint256) public tokenBalance;

    // mint function 
    function mintFunc(address _address, uint256 _value) public {
        totalSupply += _value;
        tokenBalance[_address] += _value;
    }

    // burn function
    function burnFunc(address _address, uint256 _value) public {
        if (tokenBalance[_address] >= _value) {
            totalSupply -= _value;
            tokenBalance[_address] -= _value;
        } else {
            revert("Insufficient Token Amount");
        }
    }
}
```

Compile the code. Once compiled,

1. Go to the 'Deploy & Run Transactions' tab on the left.
2. Click on Deploy.

After deploying, we can interact with the contract. 

## Authors

Vaishnavi Singh


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
