# Creating A Token

This Solidity program is a simple program that demonstrates the use of functions,different data types , mapping and use of conditional statements.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has public variables that store the details about the coin (Token Name, Token Abbrv., Total Supply), a mapping of addresses to balances (address => uint). It has a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount along with  a burn function, which works the opposite of the mint function, as it will destroy tokens. It takes an address and value just like the mint functions. It  then deducts the value from the total supply and from the balance of the address.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g.,token.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
    string public tokenName= "META";
    string public tokenAbbrev ="MTA";
    uint public totalSupply = 0;



    // mapping variable here
    mapping(address=> uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
     function burn(address _address, uint _value) public {
         if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
         }
    }

}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" , and then click on the "Compile token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. Just enter the values and finally, click on the "transact" button to execute the function and retrieve results.

## Authors

Akash
vermakash876@gmail.com

## License

This project is licensed under the MIT License.
