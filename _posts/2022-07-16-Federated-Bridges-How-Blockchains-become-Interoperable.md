---
title: "Federated Bridges: How Blockchains become Interoperable"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-16
tags: Ethereum Bitcoin Blockchain Interoperability Vatsal Kanakiya blog web3
---
Today, we have many L1 Blockchains like $BTC, $ETH, $SOL, $AVAX etc. Users might have multiple assets across multiple chains, but they will not be able to leverage them across all chains. Moving assets across chains is tough. Here's how bridges solve for interoperability👇🧵   

Why do we need interchain operability? One reason can be to reap the value of assets on one chain through a dApp on another e.g. using $BTC as collateral to take loans on $AAVE. Another is speed. Moving $ETH assets to $MATIC or $SOL allows you to transact them with speed.   

InterOp also makes the UX a lot simpler, and drives adoption. Non technical users who may not understand chains do not care as much about which one. Interoperability allows for a seamless asset management and application experience for them. Complexity can be abstracted away.   

Another benefit of InterOperabililty is Composability. It enables dApps in one chain to call and leverage a dApp in another chain. It's fairly clear that InterOp is critical to growing Crypto Adoption. But how can it be achieved? One solution is Federated Bridges. Read on 👇   

Let's take the example of a $BTC to $ETH bridge. You would like to move your BTC to ETH for use in some dApp. The federated bridge occupies a wallet address on the BTC chain. The only thing the user has to do is send the BTC they want to move to this wallet address.   

As soon as they send it to the BTC wallet, it is noticed by the validators. Validators are external agents that validate that transactions are happening as expected, with no malicious actions. The validators note the sender address upon the arrival of BTC to the bridge address.   

Validators instruct the bridge's smart contract on ETH to mint 1 pegged Bitcoin and send it to the user's wallet on ETH. This coin is called a "Wrapped Bitcoin" or wBTC. The wBTC is pegged in value to BTC since for every wBTC, there's an actual BTC locked in the bridge address.   

The User can then use this wBTC as they want on the ETH chain for as long as they want. Let's say after a while, they would like to get their BTC back on chain. All they have to do is send the wBTC back to the bridge's smart contract. The Smart contract will burn the wBTC.   

Burning the wBTC means it ceases to exist. Parallely, the validators note that the wBTC associated with a certain account was burned. They issue a signed transaction on behalf of all validators to the BTC network, instructing to send the BTC back to its original address.    

A federated bridge is as simple as that. You need these external validators because a trustless bridge without them is tough - especially in chains like BTC without strong smart contracts systems. It's better to have a group of validators, to avoid a single point of failure.   

If two chains have strong Smart Contract support, once can build a trustless bridge using a zk-SNARK proof in between. If you'd like to learn more about how zk-SNARKs work, [check out this blog]({% post_url 2022-07-05-Zk-SNARKs-A-Primer %})
