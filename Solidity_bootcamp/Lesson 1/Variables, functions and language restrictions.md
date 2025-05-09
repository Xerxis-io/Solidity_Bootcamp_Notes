- [Elementary types](https://docs.soliditylang.org/en/latest/types.html)
    - Booleans
    - Integers
    - Fixed
    - Address
    - Bytes
    - Strings
- [State Variables](https://docs.soliditylang.org/en/latest/structure-of-a-contract.html#state-variables)
- State mutability![](../Images/mutability.png)
- [Visibility](https://docs.soliditylang.org/en/latest/contracts.html#visibility-and-getters)![](../Images/visibility.png)
- [Functions](https://docs.soliditylang.org/en/latest/contracts.html#functions)
- [Events](https://docs.soliditylang.org/en/latest/contracts.html#events)
### References
[https://docs.soliditylang.org/en/latest/cheatsheet.html#mathematical-and-cryptographic-functions](https://docs.soliditylang.org/en/latest/cheatsheet.html#mathematical-and-cryptographic-functions)

[https://docs.soliditylang.org/en/latest/grammar.html#a4.SolidityParser.eventDefinition](https://docs.soliditylang.org/en/latest/grammar.html#a4.SolidityParser.eventDefinition)

### Exercise
```solidity
contract Score { 
	uint score = 5;
	function getScore() public returns (uint) { 
		return score; 
	} 
	function setScore(uint new_score) public { 
		score = new_score; 
	}
}
```

```
// Outside a function
event Score_set(uint);

// Inside a function
emit Score_set(new_score);
```
