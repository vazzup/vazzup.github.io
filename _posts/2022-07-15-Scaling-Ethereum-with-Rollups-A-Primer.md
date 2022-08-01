---
title: "Scaling Ethereum with Rollups - a Primer"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-15
tags: Ethereum Blockchain Scaling Rollups Optimistic zk-Rollups Vatsal Kanakiya blog web3
---
Rollups are the talk of the town - they're one solution to scaling the $ETH blockchain to process more Transactions (Tx) per Second. Here's how Rollups work, and why they're important: 👇🧵   

Today, every miner in the ETH network has to verify each and every transaction that is made. They check if it's valid, i.e., it's properly signed, there are enough tokens, etc. This is obviously not a very scalable model   

That's where Rollups come in. The concept of rollups is fairly simple. Instead of sending all your transactions to everyone in the ETH network, you send them to a "Rollup Coordinator" (aka RC). The RC validates and verifies your transaction as well as others.   

It doesn't push them to the ETH blockchain yet. The RC takes a lot of these transactions from various people, "rolls" i.e. aggregates them up into a single transaction. It then writes just the one transaction consisting of the outcome of all the previous ones onto the ETH chain.   

This allows the ETH network validators and nodes to validate and add only 1 transaction instead of 1000s. That means upto a 1000x increase in performance! It's not like the hard work of transaction validation does not get done though. It just gets done by a powerful RC.   

You might ask: does having an RC defeat the purpose of decentralisation completely? No. The RC is an untrusted entity that doesn't keep any secrets. If the RC tries to cheat and fails, it's easy for users to find another RC. We'll talk more on this later.   

There are two kinds of Rollups: Optimistic Rollups and zkRollups. Let's talk about zkRollups first. An example of Optimistic Rollups is Polygon Hermes. How do they work though? Read on 👇   

Check this image out. These are the basic parts of a zkRollup System. You have the Users, transacting. They send their transactions to the RC. The RC manages a merkle tree - a tree made out of hashes of the User a/c data. And you have the ETH blockchain. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fcrypto-knowledge%2FSwDO5xIOJ5.png?alt=media&token=ce4a1cfd-67f8-4773-938a-71ebaf117ccc)   

Users first have to get connected and onboard themselves onto the RC. The RC keeps a track of their initial balances, and creates a merkle tree out of their hashes. A merkle tree runs mathematical functions to combine the hashes of each wallet into a single hash.   

The root node of the tree stores the single hash and represents the current state of the wallets and their balances. This root hash is added by the RC to the ETH chain, to put the initial "state" of wallets on chain.   

The Users then start transacting with each other through the Rollup Coordinator. As the transactions happen, the RC keeps a track of their balances. After a few say transactions, say 1000, the RC will rework the merkle tree with each transaction create a new root node.   

The RC then takes this new root node hash, and adds it to the ETH chain, thus adding all transactions and the final wallet balances to the ETH chain. But how do the ETH Validators know these transactions actually happened, and weren't faked? that's where zk-SNARKs playa role. 👇   

zk-SNARKs are Zero Knowledge Succinct Argument of Knowledge. Zero knowledge means they prove that the sender knows what they're claiming to , without actually revealing the secrets. You can learn more on ZK Proofs [in this blog I wrote earlier]({% post_url 2022-07-04-Zero-Knowledge-Proofs-A-Primer %}).   

A non interactive ZK proof is one that proves the fact to the knowledge with only one statement. And a succinct one is one that is short in size and quick and easy to verify as a correct proof. [Here's a blog]({% post_url 2022-07-05-Zk-SNARKs-A-Primer %}) you can read to learn more about zk-SNARKs.

So the RC performs complex mathematical functions to create a zk-SNARK proof that tells the validators that these transactions are indeed validated correctly by the RC. The RC cannot lie. Once verified, the validators add the hash to the chain with a summary of all TXs attached.    

That's how ZK-Rollups work. What is the benefit of the ZK proof? Well first, the computational load moves from ETH Validators to the RC. Second, verifying a short zk-SNARK is much faster than verifying all the transactions!   

Optimistic Rollups work pretty much the same. The RC verifies all transactions, updates the merkle tree, creates the hash, and adds it to the ETH chain with a summary of Transactions, just like earlier. the difference is that it doesn't send a ZK Proof alongside.   

That's why it's called optimistic. The chain optimistically assumes all RCs are legitimate and accepts the Tx. However, these RCs are asked to Stake a certain amount of tokens as a pledge they won't cheat. This can be slashed if they are found cheating.    

This is where external validators come in.  External validators go through all hashes added by the RCs and their Transaction summaries, and check if they match up. If they find a malicious RC and prove it, the Tx is immediately rejected, and the RC's stake is slashed.    

The Slashed funds are given to the external Validators as a reward. In this way Optimistic Rollups allow for less computation from RCs and quick Txs. The downside is users might have to wait upto 3 days for a Validator to validate their Transaction and get access to their funds.   

Now, if a malicious RC is found, how does the User transfer their transactions to another RC? This is the data availability problem. There are two solutions to this problem: zkSync & zkPorter. Both of them work concurrently, and complement each other to ensure data availability.   

Let's start with zkSync. In this case, the L1 accepts transactions from RCs only if they include Tx summary. So when the data is to be moved, another RC can just read the transaction summaries from Transactions written by the previous RC, and build on top of that.    

This works because all the data is already on the L1, which is immutable, verified, and a trusted source of truth. The downside of zkSync is the high transaction fees associated with working with the L1 (ETH). It is generally recommended to use zkSync for high value assets.   

In the case of zkPorter, a whole new blockchain altogether is created and maintained by staked RCs. All transactions are done internally, and then written to L1 in batches. This allows for cheap on chain storage, and more security. However, there's lower guarantee than zkSync.   

The guarantee that the Transaction data will be available when needed is not as strong. Hence, zkPorter is generally preferred for lower value assets. Customers can choose how the RC can store its account when participating in a rollup - through zkSync or zkPorter.    

So that's all about Rollups - Optimistic and Zero Knowledge. They're a critical part of Web3 Infra. Infact, today we are also seeing zkEVMs - zkRollups that can process not only transactions, but entire Smart Contracts and dApps.   
