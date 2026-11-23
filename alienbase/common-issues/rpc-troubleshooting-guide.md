---
description: A detailed guide on how to identify and troubleshoot common RPC issues
---

# RPC Troubleshooting Guide

#### Introduction

When using the AlienBase platform, you may occasionally encounter issues related to the RPC (Remote Procedure Call) connections. RPC issues can affect transactions, balance updates, and general interaction with the Base Chain. This guide provides steps to help you identify, troubleshoot, and resolve RPC issues.

#### **Step 1: Understand RPC and Its Importance**

RPC serves as the bridge between your wallet and the Base Chain. If the RPC server has issues, it can prevent your wallet from performing operations successfully.

#### **Step 2: Check the Base Chain Status**

First, ensure there are no ongoing issues with the Base Chain itself:

* **Official Status Page**: Visit the [Base Chain Status Page](https://status.base.org/) to check for any service disruptions, maintenance, or updates.

#### **Step 3: Identify and Verify Your RPC Server**

Knowing which RPC server your wallet uses is crucial for diagnosing issues:

* **Find the RPC URL in Your Wallet**: Typically located in the network or settings section of your wallet app.
* **Verify RPC Server**: Compare your RPC URL with the official list on [Chainlist for Base Chain](https://chainlist.org/chain/8453).

#### **Step 4: Change Your RPC Server If Needed**

If you suspect your current RPC server is problematic, you can switch to another:

* **Through Chainlist**: Visit Chainlist, locate Base Chain, and select another RPC server to automatically add to your wallet.
* **Manually Changing RPC in MetaMask**:
  1. Go to MetaMask, select Settings.
  2. Navigate to Networks, select Base Chain.
  3. Input a new RPC URL from the approved list on Chainlist.

#### **Step 5: Inspect Element and Check Console for Errors**

Understanding the specific RPC errors can help in diagnosing the issue:

* **Access Developer Tools**: Right-click on the AlienBase webpage, select "Inspect" (Chrome) or "Inspect Element" (Firefox), then click on the "Console" tab.
* **Look for Errors**: Identify any JSON RPC error messages, such as:
  * `Error: Failed to fetch`
  * `Internal JSON-RPC error.`
  * `net::ERR_CONNECTION_REFUSED`

#### **Step 6: Document and Report the Issue**

If issues persist after switching RPC servers:

* **Take Screenshots**: Capture any error messages or issues.
* **Contact Support**: Send a detailed report to AlienBase support by opening a ticket in the [dedicated Discord channel](https://discord.com/channels/1151515107587792896/1151602990860484618). Include screenshots, the RPC URL used, and a description of the issue for helping the team to identify the problem quickly
