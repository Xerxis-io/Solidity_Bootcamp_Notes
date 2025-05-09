## Foundry Support

There is a useful [article](https://www.rareskills.io/post/openzeppelin-foundry-upgrades) from Rare Skills See [repo](https://github.com/OpenZeppelin/openzeppelin-foundry-upgrades) The plugin can use UUPS, Transparent and Beacon proxy patterns as well as the diamond pattern.

The plugin can be imported with
```solidity
import { Upgrades } from "openzeppelin-foundry-upgrades/Upgrades.sol";
```

You need the OZ upgradable libraries
```bash
forge install OpenZeppelin/openzeppelin-contracts-upgradeable --no-commit
forge install OpenZeppelin/openzeppelin-foundry-upgrades --no-commit
```
The workflow is:
### Deploy a UUPS proxy

```solidity
address proxy = Upgrades.deployUUPSProxy(
    "MyContract.sol",
    abi.encodeCall(MyContract.initialize, ("arguments for the initialize function"))
);
```

Once deployed the contract's functions can be called as normal

```solidity
MyContract instance = MyContract(proxy);
instance.myFunction();
```
### Upgrade the contract

```solidity
Upgrades.upgradeProxy(
    transparentProxy,
    "MyContractV2.sol",
    abi.encodeCall(MyContractV2.foo, ("arguments for foo"))
);
```