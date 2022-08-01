---
title: "Scaling Bitcoin with Lightning Network - a Primer"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-08
tags: Bitcoin Cryptocurrencies Scaling Blockchain Lightning Netowrk Vatsal Kanakiya blog web3 
---
Here's the thing: L1s like Bitcoin and Ethereum are slow. Bitcoin currently processes about 5 Transactions (Tx) a second. On the other hand, Visa does 24000 Tx / sec. How can crypto ever outperform traditional money? Here's how Bitcoin scales with the Lightning Network👇🧵   

There are many ways blockchains can be scaled. Today we'll cover Payment Channels. Payment Channels basically take transactions off the Blockchain and make them Peer to Peer. The Lightning Network on Bitcoin is an example of this. Let's take an example:   

Say @tdryja wants to buy coffee from Vatsal daily. It's too slow and costly for him to make a transaction daily. Instead, Tadje keeps a 100 $1 coins at the shop. He creates two piles - one for self and one for Vatsal. When he makes a payment, he moves $1 from his pile to Vatsal's
Initially, Tadje's pile has a 100 coins, and Vatsal's 0. On day 1, Tadje spends $1 with Vatsal. So he moves 1 coin to Vatsal's pile. On day 2 he spends $4, day 3 $2 and so on. By Day 14 Tadje has spent $25 in total, and decides to settle things up. Vatsal agrees too.
So Tadje takes his pile of 75 $1 coins back, and Vatsal takes his pile of 25 $1 coins back. Voila, each receive their money in one transaction. This is how Payments Channels work.   

While this example was unidirectional, i.e. only Tadge could pay Vatsal, they could also do this in a bidirectional manner. Both Tadje and Vatsal lock $100 each for 30 days, and make the payments needed. Both settle once the lock period is over or they are satisfied.   

Let's go deeper into this with the Lightning Network and how it works in Bitcoin. First, it is important to understand that each bitcoin can be divided into 100 million parts. The lowest denomination is called a satoshi. 100,000,000 Satoshis = 1 $BTC   

In Bitcoin, Transactions are kept track of, by keeping track of who owns how many Sats from a particular Bitcoin. For example, I may own 50,000,000 sats from a Bitcoin 0x1A2B. That means, I own half a bitcoin. 
If I own 50Mn sats from Bitcoin 0x1A2B, and 50Mn sats from bitcoin 0x9F8E, I still own a total of 100Mn sats, that is 1 Bitcoin. However, I own it across two different coins.    

A transaction in bitcoin consists of a few parts - the key ones for us are the inputs, outputs, and the Lock Time. The inputs are the initial Coins that are involved in a particular transaction, including the number of sats you own in each.    

The Outputs are the number of Sats remaining to be given after the payment is made. For example, you have 100 sats from coin 1, and 100 sats from coin 2. That's your input. You have to pay someone 150 sats. So you send them 100 sats from coin 1 and 50 from coin 2.   

That leaves you with 50 Sats from coin 2. The receiving party now has 100 sats from coin 1 and 50 from coin 2. These are the outputs of the transaction - a definition of who owns how many parts of a parts of a coin. So there are 3 outputs in this transaction   

Each of these outputs is called an UTXO, or an Unspent Transaction Output. A UTXO defined how many sats of a particular coin are owned by a particular user post a transaction involving the coin. This is the tool used to create Payment Channels in Bitcoin.    

It relies heavily on the last part of the transaction - the Lock Time. The Lock Time specifies whether a transaction can be included in the blockchain right away or after some specified time. If the Lock time for a Tx is 30 days, it is written in the chain after 30 days only.   

If Vatsal and Tadge want to open a Payments Channel between themselves, they only need to start a transaction with an upper limit of amount, and the lock time. For e.g. 2 BTC and 30 days. Let's say Vatsal has 4 UTXOs (i.e. coins) with 50Mn Sats in each.   

Every day Vatsal pays a little to Tadge. All of this is accounted for by the UTXO without being written into the chain. So when Vatsal wants to pay 50K sats to Tadge, he just sends a signed transaction over and the UTXO changes accordingly without actually writing on chain.   

Let's say at the end of the Lock Time (30 days), Vatsal has made payments of 75Mn Sats to Tadge. Tadge would get 50Mn Sats from Coin 1 and 25Mn Sats from Coin 2. The remaining 25Mn Sats from Coin 2 along with the 50Mn each of Coins 3 and 4 would go back to Vatsal.   

And all these changes 👆would be written into the chain at the end of 30 days as one transaction. They can also be written if both agree and sign to close the Tx. This allows for Vatsal to make bulk payments frequently with minimal transaction fees too.   

While the above example is unidirectional, it can also be bidirectional, where both users open a UTXO towards the other and settle at the end.   

However, it's ridiculous to ask users to open Payment Channels with everyone they want to exchange money with. That's where the lightning network comes in. The lightning network has 20000 nodes connected by bidirectional payment channels.    

So all you need to do is open a bidirectional payment channel with any one lightning node. Let's say you want to pay someone else, they also need to be connected to any node of the network. Then it's a simple matter of finding the shortest and cheapest part to pay the user.   

Let's say Vatsal wants to pay Tadge. Vatsal is connected to Node A, whereas Tadge to node Z. Vatsal would send a payment through to node A, which will make a payment to node M, then to node P, node X, and node Z. Node Z then reimburses Tadge.   

This whole process is automated above is automated through Smart Contracts. This is the essence of the Lightning contract. It makes Bitcoin transactions multiple orders of magnitude faster. The nodes might take a small cut off each transaction to cover their costs.   
