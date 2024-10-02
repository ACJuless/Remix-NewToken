# Remix-NewToken

This Solidity program simulates how a token's value is minted and burnt which demonstrates the basic functions and syntax of Solidity Programming. 
This program serves as a stepping stone for us to know more about Solidity Programming. 

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum. 
The contract has six functions and those are the functions tokenName, tokenAbbrv, mint, burn, balances, and totalSupply.  
This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started
### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. 
Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

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
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. 
Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. 
Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can now interact with it by calling the functions provided. 
Click on the "myToken" contract in the left-hand sidebar and it will show all the functions available. 
Before proceeding please copy the account address and paste it in the address sections ("_address") of the functions "burn", "mint", and "balances". 
That section could be found by clicking on the drop-down button beside the mint and burn functions. For the "balances" function just paste it beside the button. 
While the drop-down menu is open, input a number on the value section (_value) of the "mint" function and click transact. This will add a value to the token in the program.
Same goes for the burn function but instead of adding a value to the token it subtracts from the token. Take note that you cannot subtract a bigger value than the current value of the token. 
Lastly, the "balances" function shows the value of the current token.

The remaining functions, which are tokenAbbrv, tokenName, and totalSupply, only serve to output the abbreviation name of the token, the name of the token, and the current value of the token respectively. 

## Author(s)

Paolo Jules Acuña
