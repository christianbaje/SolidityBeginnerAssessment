# SolidityBeginnerAssessment

A simple Solidity program which shows an idea on how to create tokens!

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract will have public variables that store the details about the coin (Token Name, Token Abbrv., Total Supply). This contract will have mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount. This contract will also have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address. This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```
pragma solidity 0.8.18;

contract MyToken {
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
    mapping(address => uint) public balances;

    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;

    }

    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to 0.8.4 or above, the auto compile is selected, and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it in the Deployed Contract Portion. You can mint, burn, and check the total supply, token name, token abbreviation, and balance

You can add value into an address by copying the address found in the top part of the "Deploy & Run Transactions" tab. Paste this address to the mint, burn, or balance account to interact with it.


## Author

Christian Baje


## License

This project is licensed under the MIT License License - see the LICENSE.md file for details
