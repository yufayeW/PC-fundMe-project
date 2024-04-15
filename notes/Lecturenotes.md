## notes of Lecture 7 debugging
- examples of functions:
    - `aasertEq()`

# tiny things to remember
- when forge testing was called without using a URL, it will create a new block adress and delete it after the test is done. 

# Test Methods
1. Unit
2. Integration
3. Forked
4. Staging

# Cheatcode 
prank: only works in the test environment for forge
identify next call
    address USER = makeAddr("user");
    vm.prank(USER)
vm.deal(user, startingMoneyBalance)

# modifier
save codes 
`solidity`
    modifier funded() {
        vm.prank(USER);
        fundMe.fund{value: SEND_VALUE}();
        _;
    }

    function testOnlyOwnerWithdraw() public funded{}

# chisel is a terminal to test small pieces of solidity

## We'd better create a new one for gas saving

# storage variables
- `storage` variables are stored in the blockchain
- `memory` variables are stored in the memory and are erased after the function call
- `calldata` variables are only available during the function call and are erased after the function call
- `stack` variables are stored in the stack and are erased after the function call
- `memory` is cheaper than `storage` and `calldata` is cheaper than `memory`
- string is an array, if you want to change it, you should claim it as a memory variable
- 
- every contract has storage dataspace.
- constant variables are stored in the code and are not stored in the storage, so less gas

# saving methods:
- variable starts with s_ is a storage variable, to save gas, it should be changed to memory variable

## makekfile

# 
- `make` saves the source code