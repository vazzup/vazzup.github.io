---
title: "Zero Knowledge Proofs - A Primer"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-04
tags: zk-proofs Zero Knowledge Cryptocurrencies Blockchain Scaling Vatsal Kanakiya blog web3 
---
 You might have heard of ZK-Rollups, ZK transactions in the crypto space. The ZK there stands for Zero Knowledge Proofs. Here's what it means - a thread 👇🧵   

 Let's say you pick a card from a pack of 52 playing cards. The deck - a standard one - has 26 red cards and 26 black ones. You've picked up a Red Card, and want to prove to the person opposite you that you have a Red Card. You want to do this without revealing the actual card.   

 How do you do that? Well you show them the 26 black cards in the deck. By this they know you can not have a black card in hand. But they still don't know what card you actually have in hand. This is a zero knowledge (ZK) proof.   

 A ZK proof is a proof that over knows the secret without actually revealing the secret itself. Let's take an example of a compliance use case - Taxes. One can prove they've paid the right amount of taxes in Crypto without revealing details of the actual earnings, transactions etc   

 There are two kinds of ZK proofs: Interactive and Non Interactive. An interactive proof allows the prover and the verifier to exchange multiple messages. Let's take an example. Say someone's color blind, and you want to prove to them that two identical pens have different colors.   

 You have to do this without them having the actual knowledge of which pen has which color (say red and blue). All you have to do is to ask them to swap the pens in secret and put them in front of you. You will point out the pen to them which they had asked you to find   

 So, you find the pen they'd asked you to find. But you could just as likely have cheated or been lucky. Hence, they run the experiment over and over again. With each iteration where you pick the right pen, Their confidence increases in knowing you're correct.   

 By the end, the verifier knows that the colors of the pens are different, without actually knowing the colors of the pen. This is an interactive ZK proof - where the Prover and the verifier exchange multiple messages, and increase the confidence in the proof over time   

 Non interactive ZK proofs are like the Playing cards example taken above. The Prover gives their proof in one shot, one message to the verifier, which they can use to accept or reject. 
