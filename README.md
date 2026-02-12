# DAO Governance & Timelock

This repository implements a complete on-chain governance framework based on the OpenZeppelin Governor standard. It is designed for decentralized protocols that require community voting to execute treasury movements or contract upgrades.

## Architecture
1. **Governance Token**: An ERC-20 token with checkpoints (ERC20Votes) to track historical voting power.
2. **Governor Contract**: Manages the proposal lifecycle (Propose, Vote, Succeeded, Queued, Executed).
3. **Timelock Controller**: Acts as the "owner" of the protocol. It adds a mandatory delay between a successful vote and execution to protect users from malicious proposals.



## Governance Parameters
- **Voting Delay**: Time between proposal submission and voting start (e.g., 1 day).
- **Voting Period**: Duration of the voting window (e.g., 1 week).
- **Quorum**: Minimum percentage of total supply required for a vote to be valid.
- **Proposal Threshold**: Minimum tokens required to create a proposal.

## Deployment Guide
1. Deploy the `GovToken`.
2. Deploy the `TimelockController`.
3. Deploy the `GovernorContract` with the token and timelock addresses.
4. Transfer ownership of your protocol contracts to the `TimelockController`.
