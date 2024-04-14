pragma solidity ^0.8.0;

contract BasicOperations {
    // Define variables of different data types
    uint public num1 = 10;
    uint public num2 = 5;
    string public greeting = "Hello, ";
    string public name = "Alice";
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    // Perform arithmetic operations
    function add(uint _a, uint _b) public pure returns (uint) {
        return _a + _b;
    }

    function subtract(uint _a, uint _b) public pure returns (uint) {
        require(_a >= _b, "Subtraction result would be negative");
        return _a - _b;
    }

    // Concatenate strings
    function greetWithName() public view returns (string memory) {
        return string(abi.encodePacked(greeting, name));
    }

    // Check contract owner
    function isOwner() public view returns (bool) {
        return msg.sender == owner;
    }
}
