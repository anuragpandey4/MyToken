# MyToken

ASSIGNMENT --- This is it! You made it to your final challenge. Congratulations! As mentioned at the start of our journey, you will now create your very own token! Well, not really, but kinda! Either way, it’s going to be a lot of fun, so let’s get to the deetz!

## Description

For your assessment, we will create a contract together to fulfill the following requirements:

1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).
2. Your contract will have a mapping of addresses to balances (address => uint).
3. You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address.
5. Lastly, your burn function should have conditionals to make sure the balance of the account is greater than or equal to the amount that is supposed to be burned.

Whew! That sounds like a lot, but you’ve actually seen all of this throughout your lessons. You can 100% do this! For reference, I will list the pertinent course sections here, matching them with the requirements above.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix](https://remix.ethereum.org/).

1. Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyToken.sol`).
2. Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    string public tokenName = "ANURAG";
    string public tokenAbbrv = "ARG";
    uint public totalSupply = 0;
    mapping(address => uint) public balances;

    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
3. To compile the code, click on the “Solidity Compiler” tab in the left-hand sidebar. Make sure the “Compiler” option is set to “0.8.18” (or another compatible version), and then click on the “Compile MyToken.sol” button.
4. Once the code is compiled, you can deploy the contract by clicking on the “Deploy & Run Transactions” tab in the left-hand sidebar. Select the “MyToken” contract from the dropdown menu, and then click on the “Deploy” button.
5. Once the contract is deployed, you can interact with it by calling the mint and burn functions.

## Authors
@anuragpandey4

License
This project is licensed under the MIT License
