### 1. [Migrate the data manually](./Migrate%20the%20data%20manually.md)
- Deploy your V2 contract, and migrate manually any existing data
### 2. [Use a Registry contract](./Use%20a%20Registry%20contract.md)
- A registry (similar to ENS) holds the address of the latest version of the contract. DApps should read this registry to get the correct address
### 3. [Eternal storage](./Eternal%20storage.md)
- Separate code into function and data contracts
- DeFi projects: GMX V2 Synthetix
### 4. [Proxies](./Proxies.md)
- [Transparent proxies](./Transparent%20proxies.md)
- Universal upgradable proxies (UUPS)
- Beacon proxy
- DeFi projects: Aave, Compound...
### 5. [Diamond pattern](./Diamond%20pattern.md)([ERC-2535](./ERC-2535.md)):
- great for large solidity projects which have multiple contracts that needs to be exposed by a single contract address. for example if you wanted all the functionality of an ERC20 and all the functionality of some other arbitrary contract without using inheritance

