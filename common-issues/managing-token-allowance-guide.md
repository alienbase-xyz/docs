---
description: >-
  A detailed guide on how to identify and troubleshoot common issues related to
  token allowance
---

# Managing Token Allowance Guide

#### Introduction

In decentralized finance (DeFi), "allowance" refers to the permission that token holders give to smart contracts to spend tokens on their behalf. Managing allowances properly is crucial for engaging with various features on DeFi platforms, including farming, staking, and swapping tokens.

#### **Step 1: Understanding Allowance**

Before adjusting allowances, it's important to understand why they are necessary:

* **Security Measure**: Allowances limit how much a contract can handle without requiring further authorization, protecting your funds.
* **Functionality**: For certain features like farming or trading on decentralized exchanges, setting the correct allowance ensures these functions work without interruption.

#### **Step 2: Identifying Insufficient Allowance Issues**

If you encounter transaction failures, it might be due to insufficient allowances:

* **Error Messages**: Look for error messages that indicate a failure due to allowance issues, such as "allowance not sufficient".
* **Checking Allowances**: Use blockchain explorers or tools like Basescan to check the current allowance settings for a particular contract.

#### **Step 3: Adjusting Allowance**

Here’s how you can adjust the allowances to ensure proper functionality of your interactions:

**Setting Allowance**:

* **Navigate to the Smart Contract**: Visit [Basescan's Contract Interaction Page](https://basescan.org/token/0x365c6d588e8611125De3bEA5B9280C304FA54113#writeContract).
* **Connect Your Wallet**: Click 'Connect to Web3' to interact with the blockchain.
* **Approve or Modify Allowance**:
  * **Approve New Allowance**:
    * Function: `approveUsage`
    * Parameters:
      * UsageAddress: Address of the contract requiring the allowance (e.g., `0xd3968A4a07d64C6E16982d45191b9A09a261Ec88` for EsMaster).
      * Amount: Desired amount in the smallest token unit (e.g., `1 billion ALB` expressed as `1000000000000000000000000000`).
  * **To Revoke Allowance**:
    * Set the `Amount` parameter to `0` to fully revoke permissions.
* **Confirm Transaction**: Click on 'Write', then confirm the transaction in your wallet.

#### **Step 4: Troubleshooting and Support**

If problems persist after adjusting allowances:

* **Documentation**: Keep records of attempted transactions and error messages.
* **Support**: Contact AlienBase support in the [dedicated Discord channel](https://discord.com/channels/1151515107587792896/1151602990860484618) with detailed information for further assistance.
