# Metacrafters-Getting-Started-with-Solidity
Getting Started with Solidity

Problem Statement : 


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


**Steps / Working :**

1. Deployment :
![deploy it](https://github.com/anurag7706/Metacrafters-Getting-Started-with-Solidity/assets/75776424/98fccae7-b5b3-4a98-b724-57878ae60f24)

2. Added Value : 
![added value](https://github.com/anurag7706/Metacrafters-Getting-Started-with-Solidity/assets/75776424/13e5327a-6503-4c14-b2f9-1c2cde4ee261)

3. Value Added :
![value added](https://github.com/anurag7706/Metacrafters-Getting-Started-with-Solidity/assets/75776424/cc978af0-3de7-4908-b4c7-92851416d75a)

4. Burning Token :
![burning token](https://github.com/anurag7706/Metacrafters-Getting-Started-with-Solidity/assets/75776424/dceed72d-994c-48b0-8765-4e1b0483d181)

5. Token Burned :
![burned token ](https://github.com/anurag7706/Metacrafters-Getting-Started-with-Solidity/assets/75776424/5b74c801-62e8-47d0-ba8d-732d07ec02e1)




**Code :** 


       SPDX-License-Identifier: MIT
       pragma solidity 0.8.18;
       contract MyToken {

    // public variables here
    string public tokenName = "TOKEN";
    string public tokenAbbrv = "TKN";
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
        if(balances[_address]>= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}
