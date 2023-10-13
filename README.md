# MyToken: A Custom Ethereum Token

## Description

**MyToken** is a custom cryptocurrency token deployed on the Ethereum blockchain. Utilizing Solidity as the programming language, the token embodies essential cryptocurrency attributes and functionalities, allowing for seamless minting, burning, and balance management operations.

**Disclaimer**: This project is for demonstration purposes only

## Key Functionalities

- **Token Details Management**: Encompasses aspects such as Token Name, Token Abbreviation, and Total Supply.
- **Balances Mapping**: Tracks the token balance of each address involved in the token's transaction history.
- **Mint Functionality**: Permits the creation (minting) of new tokens, augmenting the total supply and crediting the designated address.
- **Burn Functionality**: Allows token removal (burning) from the total supply, decremented from a designated address, while ensuring balance adequacy.

## Smart Contract Structure

Below is a basic outline of the smart contract's structure:

```solidity
contract MyToken {

    // public variables here
    string public tokenName = "CANNY";
    string public tokenAbbrv = "CNNY";
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
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

### Functions

- **mint(address _to, uint256 _value)**
  - Parameters:
    - `_address`: The address to receive the minted tokens.
    - `_value`: The amount of tokens to be minted.
    
- **burn(address _from, uint256 _value)**
  - Parameters:
    - `_address`: The address from which tokens will be burned.
    - `_value`: The amount of tokens to be burned.
    
### Modifiers

No modifiers are used in the initial contract, but additional functionality, like access controls, can be implemented in future versions.

## Installation and Setup

### Prerequisites

- [Node.js and npm](https://nodejs.org/en/download/)
- [Truffle](https://www.trufflesuite.com/truffle)
- [MetaMask](https://metamask.io/download.html) or another web3 provider configured for use with Ethereum.

### Setup

1. **Clone the Repository:**
   ```shell
   git clone [repository-link]
   cd path-to-MyToken
   ```
   
2. **Install Dependencies:**
   ```shell
   npm install
   ```
   
3. **Compile & Deploy Contract:**
   ```shell
   truffle compile
   truffle migrate --reset
   ```
   
### Testing

For testing the contract functionalities:
```shell
truffle test
```
   
## Usage

After deployment, interact with the smart contract by using a decentralized application or through another smart contract. Ensure to handle mint and burn functions judiciously to maintain a balanced and functional token economy.

## Contributing

Contributions, issues, and feature requests are welcome!

## License

This project is [MIT](https://opensource.org/licenses/MIT) licensed.

## Contact

- GitHub: @CannibalPride(https://github.com/CannibalPride)

*Feel free to contact me for any queries or support needed to set up and deploy the token!*

---
