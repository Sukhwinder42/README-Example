# Create our Token

We will create a token which will store some data and the data have to be updated whether by adding or emoving some of the variable's data and mapping the token with a respective address.

## Description

There is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. We will create a contract to fulfill the following requirements: 1.Our contract will have public variables that store the details about our coin (Token Name, Token Abbrv., Total Supply) 2.Our contract will have a mapping of addresses to balances (address => uint) 3.We will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount. 4.Our contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address. 5.Lastly, Our burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
*/
// SPDX-License-Identifier:MIT
pragma solidity >=0.8.7;

contract MyToken {

    // public variables here
    string public Token_Name="SUKHWINDER";
    string public Token_Abbrv="SIR";
    uint public total_supply=0;

    // mapping variable here
    mapping(address => uint) public Balances;

    // mint function
    function mint(address useraddress, uint variable) public {
     total_supply=total_supply + variable;
     Balances[useraddress]+= variable;
    }

    // burn function
    function burn(address useraddress, uint variable) public {

    if(Balances[useraddress]>= variable) {
        total_supply = total_supply - variable;
        Balances[useraddress] -= variable;
        }
    
    }

}



```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. After that go to the bottom at deployed contracts  and cilck on side arrow with MyToken contract. Here, we have to enter the address of the token which we can copy from the Account section and Enter the address in the Mint,Burn and Balances section to test these functions.
Then transact by entering the amount we want to add to or remove from the balance.

Mint will Add the amount
Burn will Remove the balances
Total supply will return the Balances at last.

## Authors

Sukhwinder Singh  
itsmaan127@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
