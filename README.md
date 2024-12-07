# Missing Event Emission in Ownable Contract

This repository demonstrates a common bug in Solidity smart contracts: missing event emissions.  The `transferOwnership` function initially lacked the crucial `TransferOwnership` event emission. This omission can cause significant problems for applications that rely on these events to monitor ownership changes.

## Bug Description

The `transferOwnership` function, intended to transfer ownership of a contract, omits the event emission. This prevents applications monitoring the contract from recognizing the ownership change.

## Solution

The bug is resolved by ensuring that the `TransferOwnership` event is always emitted whenever ownership is transferred, providing complete and accurate record-keeping.

## How to Reproduce

1.  Compile `bug.sol`.
2.  Deploy the contract.
3.  Attempt to transfer ownership.
4.  Observe that no event is logged (demonstrating the bug).
5. Compile `bugSolution.sol`
6. Deploy the contract
7. Attempt to transfer ownership
8. Observe that event is logged (demonstrating the solution)