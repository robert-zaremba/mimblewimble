# Mimblewimble scheme

Go implementation of a mimblewimble transaction scheme.

This project is a library which provides functionality to process (create and verify) Mimblewimble transactions. It abstracts from the underlying blockchain and blockchain native transaction layer. Hence it depends on the underlying blockchain. The library allows to:

* Construct Pedersen commitments based on a field interface, with helper functions for on common elliptic curves (curve25519).
* Create and verify transactions.


**Status:** Work in progress.


## Introduction to Mimblewimble

Mimblewimble [1] was published by an anynomous author (or a group) with pseudonym for the French name of Voldemort from Harry Potter "Tom Elvis Jedusor". In it's original vision, Mimblewimble is a design of a Bitcoin based blockchain with no scripts, cross-block mergeable transactions, confidential account balances and confidential transactions. In Bitcoin transactions are linked by signed "spendable states" - UTXOs. In Mimblewimble, instead of open UTXOs, we have "unspend" Confidential Transactions (hiding token amount) using Pedersen commitments, range proofs (to prohibit overflows and negative amounts), CoinJoin (sender / receiver relation anonymity) and cut-through to compress the blockchain.

There are two notable blockchains which use Mimblewimble as their base transaction protocol: [Beam](https://www.beam.mw/) and [Grin](https://grin-tech.org/).

## Motivation

Presented protocol is way more efficient than anonymous transaction protocol using zkSNARKs family. We only need to provide a range proofs, which are much easier and faster than general constructions like zkSNARKs.

In a simple version, where each transaction has only one input and one output, we don't even need a range proofs, which makes the confidential transactions blazing fast.

## Resources

+ [1] [OriginalWhitePaper.txt](https://mimblewimble.cash/20160719-OriginalWhitePaper.txt) by Tom Elvis Jedusor (Lord Voldemort), 2016-07-19.
+ [Mimblewimble](https://mimblewimble.cash/20161006-WhitePaperUpdate-e9f45ec.pdf) mathematical whitepaper by Andrew Poelstra, 2016-10-06.
