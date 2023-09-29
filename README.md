# Create a Token

This Solidity program is a simple token contract that demonstrates the functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

The program has two functions
### Mint
The mint function adds tokens to the balance of a specified address and the total supply.
### Burn
The burn function removes tokens from the balance of the specified address and total supply if the balance of the specified address is enough.

## Getting Started

### Installing

* Downlad the createToken.sol
* createToken.sol can be run using the online solidity IDE https://remix.ethereum.org/

### Executing program
```javascript
pragma solidity 0.8.18;

contract MyToken {
    string public token_Name = "PandaPunks";
    string public token_Abbreviation = "PPNKS";
    uint public total_Supply = 0;

    function mint(address recipient, uint256 amount) public {
        require(msg.sender == owner, "Only the owner can mint tokens.");

        total_Supply += amount;
        _mint(recipient, amount);
    }

    function burn(uint256 amount) public {
        require(balanceOf(msg.sender) >= amount, "Insufficient balance to burn.");

        total_Supply -= amount;
        _burn(msg.sender, amount);
    }

    function assert_func() public {
        assert(total_Supply >= 0);
    }

    function revert_func() public {
        if (total_Supply <= 0) {
            revert("Total supply must be greater than zero.");
        }
    }
}

```

* Go to https://remix.ethereum.org/
* Right click on a blank area in FILE EXPORER(Right Window) and click upload file
* Upload createToken.sol
* Open on createToken.sol in FILE EXPORER
* Open the Solidity compiler(third icon on the far right)
* Click "Compile and Run script"

## Authors

Gabrielle Rose P. Gacula

gbrllrpg@gmail.com

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
