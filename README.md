# GarvToken

GarvToken is an ERC20-like token implemented in Solidity. It includes basic functionalities such as transfer, approval, minting, and burning of tokens.

## Features

- **Token Details**: Name, symbol, decimals, and total supply.
- **Transfers**: Transfer tokens from one address to another.
- **Approval**: Approve an address to spend tokens on behalf of the owner.
- **Minting**: Only the owner can mint new tokens.
- **Burning**: Token holders can burn their own tokens.

## Contract Details

### State Variables

- `string public name`: Name of the token.
- `string public symbol`: Symbol of the token.
- `uint8 public decimals`: Number of decimal places the token uses.
- `uint public totalSupply`: Total supply of the token.
- `address public owner`: Address of the contract owner.
- `mapping(address => uint) public balanceOf`: Balance of each address.
- `mapping(address => mapping(address => uint)) public allowance`: Allowance amount each address can spend on behalf of another address.

### Events

- `event Transfer(address indexed from, address indexed to, uint value)`: Emitted when tokens are transferred.
- `event Approval(address indexed owner, address indexed spender, uint value)`: Emitted when an approval is made.
- `event Mint(address indexed to, uint value)`: Emitted when new tokens are minted.
- `event Burn(address indexed from, uint value)`: Emitted when tokens are burned.

### Modifiers

- `modifier onlyOwner()`: Ensures that only the owner can call the function.

### Constructor

- `constructor()`: Sets the contract deployer as the owner.

### Functions

- `function transfer(address _to, uint _value) public returns (bool success)`: Transfers `_value` tokens to address `_to`.
- `function approve(address _spender, uint _value) public returns (bool success)`: Approves `_spender` to spend `_value` tokens on behalf of the caller.
- `function transferFrom(address _from, address _to, uint _value) public returns (bool success)`: Transfers `_value` tokens from address `_from` to address `_to`.
- `function mint(address _to, uint _value) public onlyOwner returns (bool success)`: Mints `_value` new tokens to address `_to`.
- `function burn(uint _value) public returns (bool success)`: Burns `_value` tokens from the caller's account.

## Usage

### Deployment

Deploy the `GarvToken` contract using Remix or any other Solidity development environment. The deployer will become the owner of the contract or.
go to the Remix website at https://remix.ethereum.org/ to run the contract.

### Interacting with the Contract

1. **Transfer Tokens**:
   ```solidity
   GarvToken.transfer(address _to, uint _value);
    ```
2. **Approve Tokens**:
   ```solidity
   GarvToken.approve(address _spender, uint _value);
   ```
3. **Transfer Tokens on Behalf**:
   ```solidity
   GarvToken.transferFrom(address _from, address _to, uint _value);
   ```
4. **Mint Tokens**:
   ```solidity
   GarvToken.mint(address _to, uint _value);
   ```
5. **Burn Tokens**:
   ```solidity
   GarvToken.burn(uint _value);
   ```
   
## Authors

- Garv Kumar (garvkumar287@gmail.com)

## License
This contract is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
