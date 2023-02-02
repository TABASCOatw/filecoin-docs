---
title: "Storage proving"
description: ""
lead: ""
date: 2022-01-25T14:41:39+01:00
lastmod: 2022-01-25T14:41:39+01:00
draft: false
images: []
type: docs
menu:
  storage-provider:
    parent: "lorem"
    identifier: "storage-proving-fb90120cfc77a129895e55e7687075aa"
weight: 10
toc: true
---

Storage proving known as “Proof of SpaceTime” (“PoSt”) is the procedure that the Filecoin blockchain uses to require storage providers to prove that they have the storage they pledged to store. In return you can earn block rewards as an incentive to store data on the Filecoin network.

As a Storage Provider you must preserve data (deals) for the duration of the deal. Currently, deals must have a minimum duration of 180 days, and maximum duration of 540 days. Storage Providers must continuously prove the availability and integrity of the data they are storing. Every storage sector of 32GiB or 64GiB gets verified once in each 24 hour period. This period is called a “proving period”. Every proving period of 24 hours is broken down into a series of 30 minute, non-overlapping “deadlines”. This means there are 48 deadlines per day. Storage sectors are grouped in a “partition” and assigned to a proving deadline. All storage sectors in a  given partition will always be verified during the same deadline.

The cryptographic challenge for storage proving is called WindowPoSt (Window Proof-of-SpaceTime). Storage Providers have a deadline of 30 minutes to respond to this WindowPoSt challenge (via a message on the blockchain containing a [zk-SNARK](https://en.wikipedia.org/wiki/Zero-knowledge_proof) proof of the verified sector). Failure to submit this proof within the 30 minute deadline, or failure to submit it at all, results in “slashing”. Slashing means a portion of the [collateral]({{< relref "fil-collateral" >}}) will be forfeited and the “storage power” of the Storage Provider gets reduced. Slashing is a way to penalize Storage Providers who fail to meet the agreed standards of storage. 

Another technique used by the Filecoin blockchain is WinningPoSt. WinningPoSt is the cryptographic challenge through which Storage Providers are rewarded for their contributions to the network. At the beginning of each epoch (1 epoch = 30 seconds), a small number of Storage Providers are elected to mine new blocks. Each elected Storage Provider who successfully created a block is granted Filecoin tokens by means of a “block reward”. The amount of FIL per block reward varies and is listed on various blockchain explorers like [Filfox](https://filfox.info/en).

The election mechanism of the Filecoin network is based on the “storage power” of the Storage Providers. A minimum of 10TiB in storage power is required to be eligible for WinningPoSt, and hence to earn block rewards. The more storage power one has the more likely he will be elected to mine a block. This concept becomes incredibly advantageous in the context of Filecoin Plus verified deals.