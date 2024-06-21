ETH PROOF: BEGINNER EVM COURSE ASSESSMENT

The ETH PROOF: Beginner EVM Course by Metacrafters is a comprehensive introduction to the world of Web3.0 and Solidity, the programming language used for writing smart contracts on the Ethereum blockchain. The course covers essential concepts of decentralized applications, blockchain technology, and the Ethereum Virtual Machine (EVM). Through hands-on exercises and projects, participants learn how to develop, deploy, and interact with smart contracts. The course aims to equip beginners with the foundational skills necessary to navigate and contribute to the rapidly evolving Web3 ecosystem.

DESCRIPTION:

The final assessment of the ETH PROOF: Beginner EVM Course involves creating a Solidity smart contract that simulates the basic functionality of a cryptocurrency token. The assessment tests the understanding and application of core Solidity concepts learned throughout the course. The following requirements outline the tasks to be accomplished in the assessment:

Requirements:
Public Variables:
Create public variables to store the token details: Token Name, Token Abbreviation, and Total Supply.
Address Balances Mapping:
Implement a mapping to track the balances of addresses (address => uint).
Mint Function:
Develop a mint function that accepts an address and a value. This function increases the total supply by the given value and credits the specified address with the same amount.
Burn Function:
Create a burn function that takes an address and a value. This function decreases the total supply by the specified value and deducts the same amount from the address's balance.
Conditional Checks in Burn Function:
Ensure the burn function includes conditionals to check that the sender's balance is sufficient to burn the requested amount of tokens.

Getting Started

Installing:

We used Remix IDE to compile and run our code.

Executing program:

In order to Execute our program you need to copy the code and paste it into Remix.
After pasting it you need to hit the Compile Button and Compile the code.
Next we will Deploy and Run Transcations.

How to run the program:

In order to Execute our program you need to copy the code and paste it into Remix.
After pasting it you need to hit the Compile Button and Compile the code.
Next we will Deploy and Run Transcations.

Author:
Raunak Raj

Contributors names and contact info:
Raunak Raj
raunakraj3002@gmail.com

License
This project is licensed under the Metacrafters.

CODE:-

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

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

    string public Name = "Twiter";
    string public Symbol = "X";
    uint public TotalSupply = 0;

    // mapping variable here

    mapping (address => uint) public balances;


    // mint function

    function mint (address _address, uint _value) public{
        TotalSupply += _value;
        balances [_address] += _value;

    }

    // burn function

    function burn (address _address , uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance");
            TotalSupply -= _value;
            balances[_address] -= _value;

        }

    }




