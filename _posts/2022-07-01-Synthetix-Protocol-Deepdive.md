---
title: "Synthetix Protocol - a DeepDive"
layout: post_edited
author: Vatsal Kanakiya
date:   2022-07-01
tags: Synthetix Cryptocurrencies Derivatives Trading Vatsal Kanakiya blog web3
---
I read through the Synthetix Protocol (synthetix.io). It's a protocol enabling the creation of synthetic derivatives based off real-world assets on the blockchain today. It's purpose is only speculative trading. Thought it was cool. Here's what they do 👇🧵   

@synthetix_io is built on $ETH. The protocol issues Synth tokens, whose prices are pegged to an underlying price feed and are backed by collateral. The main tracked assets are cryptocurrencies, fiat currencies, and gold.  e.g. sUSD - a synth pegged to the USD price.
The important thing to understand is the Synth is not backed by the actual asset. No trust is holding BTC just because you've bought sBTC. sBTC is pegged to the price of BTC, without holding any BTC. How do they do this? Read on 👇   

The protocol uses "decentralized oracles" from Chainlink. Oracles are  smart contracts on the blockchain which track the prices of real world assets and provide the data to other protocols. Synths can theoretically track any asset, long or short, and even levered positions.   

There are two broad types of tokens you can get: A long Synth is called an sToken, for example, a sUSD or a sBTC. When you're long, that means you're expecting the price of the asset to go up.
A short Synth is called an iToken, for example, an iETH or an iMKR. The values of these tokens rise when the asset's value fall. When you're short and buying iTokens, you're betting that the price of the asset will go down.   

Synthetix also has a platform token called SNX. SNX is a utility token, which means it enables the use of Synthetix functionality as its only feature. SNX serves as the unique collateral asset for the entire system. To create any Synths, you have to use SNX. 
To mint an sBTC for example, one has to buy SNX from an exchange, and then put it down as collateral on the smart contract. All Synths cumulatively create a "debt pool". Say $100K worth of SNX has been pledged for a set of Synths, then the total debt in the system is $100K   

When a user mints a synth, they become owners of a percent of the debt in proportion to their contribution e.g. if you mint at sBTC at $20K, and there's another $80K worth of synths minted, the total debt pool becomes worth $100K, and you become responsible for 20% of the debt.
The user become responsible for this percentage of the debt in the sense that to unlock their SNX collateral they need to return the total USD value of their debt. 
The global debt of all Synths is thus shared collectively by the Synth holders based on the USD-denominated percentage of the debt they owned when they opened their positions. So if the total debt goes up faster than the debt your holding is worth, you'll be down losing money.   

Let's say you buy into sBTC at $20K in a pool of $100K total and the price of BTC doubles to $40K. Parallely the rest of the market rises too, and the debt pool becomes $500K. You own 20% of the $500K pool, i.e. $100K, but your sBTC is worth only $40K. You're down $60K.   

Users can also stake their SNX tokens. Stakers are eligible to receive two types of rewards if your collateralization ratio remains at 600%: staking rewards, denominated in SNX, and exchange fees from all Synth trades, denominated in sUSD. 
A variable fee between 0.3% and 1% is also levied on each trade and sent to a pool where it can be claimed by SNX stakers.   

The stakers act as a “pooled counterparty” to trades in Synthetix. This means that exchanging Synths does not need another party to exchange with. Instead, you may convert them directly through a smart contract. This mitigates slippage, and ensures sufficient liquidity to trade.
Linking rewards to the collateralization ratio ensures that Synths are always sufficiently backed by collateral. If you want to un-stake your SNX tokens, you must burn sUSD. And because the debt pool fluctuates, you may need to burn more or less sUSD than you initially minted.   

The last piece of the Synthetix puzzle is Kwenta. Kwenta is a decentralized exchange on which you can trade Synths. Unlike other DEXs, the exchange does not have an order book and instead utilizes peer-to-contract trading, meaning all trades are executed against a smart contract   

What's the point of Synths though? Keep Reading 👇
Geography makes a lot of difference if you have access to certain assets. It's tough to buy Commodities being traded in New York while sitting in Senegal. Synthetix allows users to trade on any and every asset class possible through the blockchain. Physical and digital.
Synthetics and derivatives are also very important for building mature financial markets — i.e., markets that have reached equilibrium — by facilitating price discovery and helping to hedge against volatility   

Since Synths are issued on $ETH, you can use them on other protocols such as Curve, Uniswap, and Compound to provide liquidity and earn interest.
What's are the downsides? You don't get access to the actual asset, or any dividends / yields from it. You can only track the price. The other issue, is that creating a Synth requires massive collateralization to mint or stake - almost 600%.   

The protocol is also largely only meant for speculative trading on assets. It's not recommended for newbies.
