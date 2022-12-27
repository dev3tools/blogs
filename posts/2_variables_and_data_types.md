---
title: 2. Variables and Data Types
date: 2022-12-25
permalink: basics/variables_and_data_types/
---

In this blog we will discuss about variables in solidity. Variables are the names you give to data locations which are used to store values in a smart contract.


## Types of variable
1. State variable
2. Local variable
3. Global variable


#### 1. State variable
Store permanent data in the smart contract (referred to as persistent state) by recording the values on the blockchain. These are not defined in any function it's outside a function. 

#### 2. Local variable
These variables are generally defined inside a function and cannot be accessed from outside that function’s scope. These are “transient” pieces of data that hold information for short periods of time while running computations. These values are not stored permanently on the blockchain.

#### 3. Global variables
These variables and functions are “injected” into your code by Solidity, and made available without the need to specifically create or import them from anywhere. These provide information about the blockchain environment the code is running on and also include utility functions for general use in the program. Global variables aren’t declared by you - they are “magically” available for you to use.

#### Varibale example
```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Variable {
    uint public stateV;    // <--------- State variable

    function setStateVariable(uint _count) public {
       stateV = _count; 
    }

    function localVariable() public pure returns(uint) {
        uint localV = 23; // <--------- Local variable
        return localV;
    }

    function globalVariable() public view returns(address) {
        return msg.sender; // <--------- Global variable
    }
}
```

