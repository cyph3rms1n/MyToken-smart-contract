# CREATE A  TOKEM  IN SOLIDITY

This Solidity program is a simple program that demonstrates how we can crewate a token, mint it, and burn it. The purpose of this program is to make you familier with basic functionality of the solidty programming language.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract demonstrate how we can create a token in solidty. This program serves as a simple and straightforward purpose of learning solidity, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., My_Token.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
/// SPDX-License-Identifier: MIT
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
    string public tokenName = "Epix Unite";
    string public  tokenAbbrv = "EU";
    uint public  totalSupply;

    // mapping variable here
    mapping (address => uint) public  balances;

    // mint function
    function mint(address _address, uint _value) public  returns  (address,uint){
        totalSupply = totalSupply + _value;
        balances[_address] = balances[_address] + _value;
        return (_address, _value);
    }

    // burn function
    function burn(address _address, uint _value) public  returns (string memory){
        if(balances[_address] >= _value){
            balances[_address] = balances[_address] - _value;
            totalSupply = totalSupply - _value;
            return "Burn successful";
        }
        else{
            return "Burn unsuccessful, Insufficient supply of token";
        }
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile  My_Token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "My_Token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it. Click on the "My_Token" contract in the left-hand sidebar, and then click on call button to check the token name, token abbreviation and total supply after that you can use mint function to mint the token according to total supply, And after minting of token you can also burn the token form the token supply using burn function. You can only burn a limited amount of token that are present not more than that. After using mint function and burn function you can check your total supply for total amount of token left. Total supply of token changes every time you call the mint and burn function.

## Authors

Jyotish Yadav  
[@novamaster_msin](https://twitter.com/novamaster_msin)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
