## Exercise 1:

Modify the code below by packing the state variables to reduce gas cost of deployment.
```solidity
// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.27;

contract Store {

    struct payments {
        bool valid;
        uint256 amount;
        address sender;
        uint8 paymentType;
        uint256 finalAmount;
        address receiver;
        uint256 initialAmount;
        bool checked;
    }
    uint8 index;
    uint256 public number;
    bool flag1;
    address admin;
    mapping (address=>uint256) balances;
    bool flag2;
    address admin2;
    bool flag3;
    payments[8] topPayments;


    constructor(){

    }


    function setNumber(uint256 newNumber) public {
        number = newNumber;
    }

    function increment() public {
        number++;
    }
}
```

## Exercise 2:
Clone this [repo](https://github.com/Adg0/GasOptimisationFoundry)
### Your task is to edit and optimize the Gas.sol contract.

- You cannot edit the tests
- All the tests must pass.
- You can change the functionality of the contract as long as the tests pass.
- Try to get the gas usage as low as possible.
## To run tests & gas report

Run: 

`forge test --gas-report`

## To run a specific test

RUN:

`forge test --match-test {TESTNAME} -vvvv` 

EG: 

`forge test --match-test test_onlyOwner -vvvv`