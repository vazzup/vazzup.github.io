---
title: "ZK-SNARKs - a Primer"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-05
tags: zk-SNARKs Zero Knowledge Proofs Primer Vatsal Kanakiya blog web3
---
Zero Knowledge Proofs have a real application in the crypto world. They can be used for Rollups, Private Transactions, and a lot more. ZK Proofs  that work on the blockchain are a special type called SNARKs. Let's do a deep dive into what ZK Snarks are and how they work: 👇🧵   

Firstly, if you aren't yet aware of Zero Knowledge (ZK) proofs, [here's a blog]({% post_url 2022-07-04-Zero-Knowledge-Proofs-A-Primer %}) that elucidates more on the same.   

Coming back - SNARK is an acronym for Succinct Non-Interactive Argument of Knowledge. What does that mean?   
a. It's succinct i.e. Short and sweet.    
b. It's Non interactive - i.e. it involves a single exchange of message from prover to verifier   

A SNARK is a short single message proving that you know what you claim to know. A zk-SNARK hence becomes a SNARK which does not give any knowledge of the secret you know. Why are zk-SNARKs so important to blockchains? Read on 👇   

Blockchains are decentralised Turing complete computers. But they're also resource constrained. Their compute power isn't too high. And compute is costly too, through gas. An interactive ZK Proof would not be ideal on the blockchain. SNARKs are short and fast enough to work.
Hence, by default, zk-SNARK algorithms have to be fast and generate the smallest possible proof. Every proof has 4 elements to it :   
a. 'C' - statement to be proved   
b. 'x' - knowledge that is public   
c. 'w' - secret that only Prover knows   
d. 'pi' - proof sent to Verifier by Prover   

So how do they work? First, there's the pre-processing. The actual statements that are to be proven i.e. 'C', tend to be too long. A pre-processor "S" is run on it to get two statements Sv & Sp
Sv is the statement sent to and used by the verifier. Sp is for the prover. These shorter statements are essentially summaries of the original statement in the context of the verifier or the prover.    

Then there's the algorithm P. This is used by the Prover using the data Sp, x, and w to generate the proof pi. This Algorithm is public along with Sp and x, but the secret w is known only to the Prover   

This proof pi is then sent to the Verifier. The Verifier uses the algorithm 'V' to verify if the proof is correct or not. Basis the response of V, the Verifier accepts or rejects the Prover's claim of knowledge.   

The preprocessing algorithm is one of the key parts in making the proof "Succinct". The proof should not take too much time to generate or to verify. Neither should the proof be too long to take up memory. The preprocessing algo generates the summaries so that this is solved for.   

Preprocessing algorithms can be classified on the basis of their security. There's trusted setup circuit: They have a random number that is generated for each statement internally as part of the algorithm.
This is not secure though, as if the number is discovered, the pattern is also discovered. This makes it easier for malicious actors to fake the proof or fake the verification.   

A slightly better way is the Trusted but Universal (updatable) setup. In this case, the preprocessing is split into two different algorithms. One only to generate random numbers, and the other to use the random number along with the statement C and x to generate Sp and Sv. 
This is better because if the random number is compromised, one can simply refresh the first algorithm that generates the random number.   

A Transparent Setup for a preprocessing algorithm is the best in terms of security. They do not use any secret random numbers or data. Hence, they tend to be a lot more secure.   

The first zk-SNARKs were design in 90s in papers by Kilian and Micali. However they were impractical because the time taken by provers were really high. After that, progress happened directly in 2016 with Groth's seminal work. Groth used a trusted setup, however
Since then, a lot of progress has been made with STARK '19 and DARK '19 which are transparent setup SNARKs. Here's a small comparison of all the recent SNARKs
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fcrypto-knowledge%2Fwxg-CbXrDp.png?alt=media&token=ed370ff6-caea-4618-b69c-2ea9b9c81995)
