// SPDX-License-Identifier: Unlicense

pragma solidity ^0.8.15;

// Uncomment this line to use console.log
import "hardhat/console.sol";
import "./Ownable.sol";

contract SimplePaymentContract{

    address payable public AddressOwner;

    event Pay_Method(address indexed payer, uint256 amount)

    constructor (address payable _AddressOwner) {
    //AddressOwner= payable(msg.sender);
    AddressOwner = _AddressOwner;
    }

   function method_pay (uint256 _value) public payable {
        require(_value > 0);
        require(msg.value == _value);
        AddressOwner.transfer(_value);
        emit Pay_Method(msg.sender, _value);
    }


    function ContractBalance ()external view returns(uint) {
    return address(this).balance;
    }
    function withdraw() public onlyOwner() {
        address payable _owner = address(uint160(owner()));
        address myAddress = address(this);
        _owner.transfer(address(this).balance);

    }
}
