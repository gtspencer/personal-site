+++
author = "Spencer Obsitnik"
date = "2021-08-28"
title = "The Function of Supply: An ERC-20 Experiment in Minimum Transactable Value"
description = "The function of supply: an experiment in the supply of ERC-20 tokens"
tags = [
    "erc20",
    "ethereum",
    "bitcoin",
    "dev",
    "function of supply"
]
categories = [
    "dev",
    "project"
]
+++
## An Experiment in the Supply of ERC-20 Tokens

**This is still a work in progress**

### Abstract
This "greypaper" serves to identify a little discussed issue.  Popular tokens like Ethereum and Bitcoin, as they gain popularity, inch closer to a divisibility bomb in what I've dubbed "the Satoshi problem."  High market cap coins with limited supply and fixed divisibility will eventually experience a slowdown in the network when users are unable to micro-transact.

In order to be a useful currency, a monetary system should exhibit certain [characteristics][1]:
1. Durability
2. Portability
3. Divisibility
4. Uniformity
5. **Limited supply**
6. Acceptability

Most cryptocurrencies exhibit many if not all of these characteristics.

Popular cryptocurrency native networks like Bitcoin and Ethereum pose a little understood problem.  The underlying code in the Ethereum Virtual Machine (EVM) and the Bitcoin network physically doesn't compute decimals.  Instead, they hard-code the decimal point.  Consider the following in regards to Bitcoin:
>Bitcoin has a hard cap of 21 million coins.
>Bitcoin is divisible up to 8 decimals per the Bitcoin [source code](https://github.com/bitcoin/bitcoin/blob/master/src/amount.h).  This smallest divisible unit is called a Satoshi.
>This means, one Satoshi is equal to 1 / 100,000,000 of a Bitcoin.
>If one were to send 1 Bitcoin, they are actually sending 100,000,000 Satoshis.  The wallet software sees that amount of Satoshi, reads the Bitcoin source code to find out where to place the decimal, and places the decimal 8 points in.  In essence, it is valid to think about this transaction as sending 100,000,000 Satoshis as opposed to sending 1 Bitcoin.

A token with a "smallest divisible asset" (a Satoshi in Bitcoin terms) poses an interesting set of problems for a token with high liquidity.

The smallest divisible asset sets limitations on the network:
1. The minimum transactable value of the network is the smallest divisible asset.
2. The minimum transaction fee of the network is the smallest divisible asset.

Imagine Bitcoin is trading at $1 million a token.  This means a 2 things: the minimum transactable value of the network is 1 cent, and the minimum transaction fee is 1 cent.

### Minimum Transactable Value
The minimum transactable value of a network should serve the needs of everyone in the network.  At a minimum transactable value of even 1 cent, many financial services are left unusable.  Compounded interest is frequently calculated in divisions less than 1 cent.  Even automotive gas is priced in increments less than 1 cent.  For a network to be sustainable, its minimum transactable value must scale down with the network, relative to the dollar.

### Minimum Network Fee
Microtransactions, those less than 10 cents, are impossible, as network fees eat in to 10% of the trade.

### Velocity of Money
https://vitalik.ca/general/2017/10/17/moe.html

### Move the Decimals!
The obvious solution is to move the decimals.  Since the network imposes this arbitrarily, it would be trivial to divide Bitcoin further, say to 18 decimals like Ethereum.

This creates more tradeable entities.  While not necessarily increasing supply, increasing the decimals does increase the amount users are able to trade.  This by definition increases the velocity.

### One Token vs. Many Token
To better understand this problem, I present two tokens: One Token and Many Token.  Each is implemented identically with one key difference: their supply.  Each token has identical amounts of tradeable entities (1x10^77), with strikingly opposite supplies.

[1]: <https://www.stlouisfed.org/education/economic-lowdown-podcast-series/episode-9-functions-of-money#:~:text=The%20characteristics%20of%20money%20are,%2C%20limited%20supply%2C%20and%20acceptability.> "St. Louis Fed Function of Money"
