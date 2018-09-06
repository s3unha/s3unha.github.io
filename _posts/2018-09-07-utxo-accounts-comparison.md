---
layout: post
title: "UTXO v Accounts Comparison"
date: 2018-09-07
---

1. [Mike Hearn on UTXO](https://www.corda.net/2016/12/rationale-tradeoffs-adopting-utxo-style-model/)
2. [Vitalik Buterin on UTXO](https://www.corda.net/2016/12/rationale-tradeoffs-adopting-utxo-style-model/)
3. [Design Rationale: Accounts and not UTXOs](https://github.com/ethereum/wiki/wiki/Design-Rationale#accounts-and-not-utxos)

**UTXO Benefits**

1. Higher degree of privacy: IF a user uses a new address for each transaction that they receive then it will often be difficult to link accounts to each other. This applies greatly to currency, but less to arbitrary dapps.
2. Potential scalability paradigms: UTXOs are more theoretically compatible with certain kinds of scalability paradigms. UTXOs are very easy to apply transactions in parallel asssuming sufficiently granular entries. However, non-UTXO-dependent scalability paradigms do exist and there are tradeoffs. 
3. Minimal demands on consensus algorithms: All conflict resolutions boil down to the double spending problem.

**UTXO Cons**

1. Unfriendly: Representing numeric amounts using immutable entries is unnatural. The matter becomes even worse during implementation. You will need a layer on top of the underlying ledger to calculate a user's balance instead of just reading it out of the database. As a result, a lot of pressure is placed on wallet developers to be familar with the UTXO model so that they may create a friendly software.
2. Limitations in creating complex applications such as smart contracts.

**Account Benefits**

1. Large space savings: For example, if an account has 5 UTXO, then switching from a UTXO model to an account model would reduce the space requirements from (20 + 32 + 8) * 5 = 300 bytes (20 for the address, 32 for the txid and 8 for the value) to 20 + 8 + 2 = 30 bytes (20 for the address, 8 for the value, 2 for a nonce(see below)). In reality savings are not nearly this massive because accounts need to be stored in a Patricia tree but they are nevertheless large. Additionally, transactions can be smaller (eg. 100 bytes in Ethereum vs. 200-250 bytes in Bitcoin) because every transaction need only make one reference and one signature and produces one output.
2. Greater fungibility: Because there is no blockchain-level concept of the source of a specific set of coins, it becomes less practical, both technically and legally, to institute a redlist/blacklisting scheme and to draw a distinction between coins depending on where they come from. The responsibility for privacy falls less on the users in the account model.
3. Simplicity: Easier to code and understand, especially once more complex scripts become involved. It is not impossible to create complex programs using UTXO but it is best suited for dealing with finance.
4. Constant light client reference: Light clients can at any point access all data related to an account by scanning down the state tree in a specific direction. In a UTXO paradigm, the references change with each transaction, a particularly burdensome problem for long-running dapps that try to use the above mentioned state-root-in-UTXO propagation mechanism.

**Account Cons**

~~1. No SPV (light client): currently Ethereum still does not have a SPV wallet regardless of the benefits of the light client.~~
