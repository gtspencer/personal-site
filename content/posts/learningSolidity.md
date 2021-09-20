+++
author = "Spencer Obsitnik"
title = "Takeaways From Learning Ethereum"
date = "2021-08-29"
description = "A brief description of my first post"
tags = [
    "solidity",
    "ethereum",
    "dev",
]
+++
Over the past few months, I have done a deep dive in to Solidity and Ethereum development.  This has included some Web3, but the main focus has been on Solidity and ERC standards.  Below is a short list of resources I used, as well as some brief takeaways.

## Resources I Used
[Nader Dabit](https://twitter.com/dabit3?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor).  I cannot stress enough how phenomenal that guy is at teaching.

### Tutorials
* https://cryptozombies.io/
* https://dev.to/dabit3/the-complete-guide-to-full-stack-ethereum-development-3j13
* https://questb.uk/quest/building-a-bank-with-solidity-that-isnt-a-toy-for-beginners-3e6e

## Tools I Used
* [Hardhat] (https://hardhat.org/)
* [Ethers.js] (https://docs.ethers.io/v5/)

## Things I Liked
**Implicit function variables**

Some variables are exposed to functions implicitly.  Things like `msg.sender` and `txn.origin` that expose the address of the sender and the caller of the transaction respectively.

**Modifiers**
Modifiers are used to restrict access to code.  They can perform a quick boolean check, or can be used for more complex purposes.  Below is a simple example:
```
// modifier
modifier isDivisible(uint a, uint b) {
  require(a % b == 0);
  _;
}

// function that uses modifier
function divide(uint a, uint b) public isDivisible(a, b)
 {
   // divide
 }
```
Once the modifier reaches the underscore, the function that calls the modifier can be executed.

## Things I Didn't Like
**Verbose function declarations**

Solidity has extremely verbose function declarations.  For example:
```
function testDeclaration(string storage _name) public view returns (bool) {
  // some code here
}
```

**Seemingly Inefficient Programming Logic**
Due to how storage, memory, and gas work in the EVM, it can often be more efficient to reconstruct complex variables (like arrays) in memory during runtime instead of storing it in a global variable.

## Things That Confused Me
**Storage vs. Memory (vs. Calldata)**

This is a seemingly complex one that I spent a lot of time on.  What it really boils down to, however, is that storage is persistent and memory is not.  After a function call, the memory is "wiped," like RAM on a computer.  Storage sticks around.  Calldata is a bit more complex and deals with external calls to the function.  There are more complex nuances, of course, and I encourage every one to explore them.
