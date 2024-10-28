# Changing allowance

EsALB uses a different allowance system for allocating to farms, which is what happens when you click "Enable" on our Farms page.



In some cases, the allowance might be insufficient, or you may want to revoke it fully. Tools like revoke.cash wouldn't support this kind of allowance (but also, no one can take esALB from you).



To fix allowance issues, for now you need to manually approve usage on Basescan. To do so, head over to this link: [https://basescan.org/token/0x365c6d588e8611125De3bEA5B9280C304FA54113#writeContract](https://basescan.org/token/0x365c6d588e8611125De3bEA5B9280C304FA54113#writeContract)

**Click 'Connect to Web3' to connect your wallet.**

<figure><img src="../.gitbook/assets/Screenshot 2024-04-26 at 02.55.54.png" alt=""><figcaption></figcaption></figure>

Then, find the "approveUsage" function and fill the following parameters:

* UsageAddress: 0xd3968A4a07d64C6E16982d45191b9A09a261Ec88
* Amount: 1000000000000000000000000000

Usage Address is the address of our EsMaster, a contract for farming with esALB and other locked tokens. The amount is equivalent to 1 billion ALB, which is more than the total supply and should be more than enough for any approval.

To revoke approval, just set the amount to 0

Next, click on 'Write', confirm the transaction, and your allowance should be fixed!

<figure><img src="../.gitbook/assets/Screenshot 2024-04-26 at 02.56.57.png" alt=""><figcaption></figcaption></figure>



