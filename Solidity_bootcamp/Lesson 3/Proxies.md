![](../Images/proxy_diagram.png)
```solidity
contract AdminUpgradeableProxy { 
	address implementation; 
	address admin;
	
	fallback() external payable { 
		// delegate here 
	} 
	function upgrade(address newImplementation) external { 
		require(msg.sender == admin);
		implementation = newImplementation; 
	}
}
```
[Transparent proxies](./Transparent%20proxies.md)
```solidity
contract TransparentAdminUpgradeableProxy { 
	address implementation; 
	address admin;
	
	fallback() external payable {
		require(msg.sender != admin);
		// delegate here 
	} 
	function upgrade(address newImplementation) external { 
		if (msg.sender != admin) fallback();
		implementation = newImplementation; 
	}
}
```

Universal upgradable proxies ([UUPS](./UUPS.md)):
```solidity
contract UUPSProxy { 
	address implementation;
	fallback() external payable {
		// delegate here
	}
}

abstract contract UUPSProxiable {
	address implementation;
	address admin;
	
	function upgrade(address newImplementation) external {
		require(msg.sender == admin);
		implementation = newImplementation;
	}
}
```

#### Cost Comparison
![](../Images/cost_comparission.png)

### Overwriting data
There is a possibility of overwriting data in our proxy contract unintentionally. 
- [Layout of variables in storage](https://docs.soliditylang.org/en/v0.8.7/internals/layout_in_storage.html#layout-of-state-variables-in-storage)

Wrong upgrade pattern:

| Implementation_v0 | Implementation_v1       |
| ----------------- | ----------------------- |
| address owner     | address lastContributor |
| mapping balances  | address owner           |
| uint256 supply    | mapping balances        |
| ...               | uint256 supply          |
|                   | ...                     |

The correct approach is only to **append** to the storage when we upgrade

| Implementation_v0 | Implementation_v1       |
| ----------------- | ----------------------- |
| address owner     | address owner           |
| mapping balances  | mapping balances        |
| uint256 supply    | uint256 supply          |
| ...               | address lastContributor |
|                   | ...                     |
