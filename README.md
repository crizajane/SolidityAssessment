# Solidity Project

## Overview

The Solidity program code that I made for the assessment in Metacrafters is a simple token contract that shows how to use the Solidity programming language. 


## Description

The program is all about creating a token contract that is made in the Solidity Program. It has functions that you can use like the Token Details, Total Supply, Balances. It also has an interactive part where you can manage your account by creating or destroying the tokens. It's called the mint to create  and burn for destroy.

## Getting Started

### Installing

For this code, I used the Remix IDE. First search it on the google chrome and click the first website that you see on the screen. This is the link so you don't have to search for it. Click this one as it will be the one you will use to run your code. https://remix.ethereum.org 

Once you click the website, Create an account or LogIn on Remix IDE to be able to use it. After that click start coding and you can now create a file. 

### Executing program

I created a file using MyToken.sol and after that I pasted my code. Now to run the code, click the Compile MyToken.sol button. After compiling the code, you can now successfully click the deploy 

After you deploy, copy the account or address above and click the dropdown menu button. 

Click the TotalSupply, Token Abbrv and Token Name. Then click the mint and paste the address, enter a value and call it. You can check the balance by clicking it and you can also burn the value by clicking the burn and typing the value that you want to burn. 

// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

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
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}


## Help

Make sure that your version is the latest version, I use 0.8.25 as it's the latest version when I run my code. 

## Authors

Criza Jane Guerzon
[422002513@ntc.edu.ph]
username in Metacrafters [@crizaaaaa]
