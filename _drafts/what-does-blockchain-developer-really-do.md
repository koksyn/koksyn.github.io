---
layout: post
title: What does the Blockchain Developer really do?
categories: [Research]
excerpt: Let's decrypt the mystery behind this title. I have described the activities that a Blockchain Developer
can do. These are also grouped into categories and compared to available jobs in the market.
It turns out, that they are the various perspectives and types of responsibilities.
---

> Caution! This article is still in progress. To be completely transparent with you I am showing you this article at an early stage.
> So that you get a fresh knowledge as soon as possible. I will not leave it unfinished, don't worry :) It's just a matter of (my free) time!

## Initial assumptions for research

#### Background

Let's assume you are a Software Engineer, which have a strong theoretical and practical background of IT Science, 
common algorithms, architectures and a commercial software development.

You are also interested in blockchain technology, you had a chance to use various dApps, wallets,
transactions on many blockchains and so on. Maybe you have listened of Smart Contracts (or already tried to write some), 
read the Bitcoin WhitePaper and some books/articles about it. 

You've reached the point, where you are wondering what skills and knowledge area you need
to become a Blockchain Developer. Maybe you would like to make a choice according to your interests?
You also need to know what kinds of jobs and positions exist in the blockchain industry.
What is the difference between them?

#### Goals

I've started to wonder about that too. That's why I've checked out job listings at over the TOP 200
blockchain companies and read many publications on the subject. In this article I would like to share
with you my observations and conclusions. 

In my opinion it is worth consciously considering at the outset which path to take
before completely immersing yourself in the subject. My aim was to get a good idea
of the possible paths forward in this new field. It costs me a bit of effort, 
so I hope it will be useful to you as well :)

## Technical activities

List of activities you can do on technical side:

- Write and deploy Smart Contracts.
- Develop libs or apps, which interacts with Smart Contracts.
- Read and process data from Blockchain.
- Create an Oracle.
- Build a Bridge between Blockchains.
- Develop blockchain nodes / systems from scratch.

### 1. Write and deploy Smart Contracts.

#### Introduction

Firstly, you have to know what a Smart Contract is and how it works theoretically.
It's a program (set of bytecode instructions), which is stored inside Blockchain in a binary representation.

People can deploy a new code to be stored on ledger or run the existing code. It will be executed only, when someone triggers it.
Triggering means, that someone attached additional data to the Blockchain transaction, which consist of Smart Contract address 
and arguments passed to one of its functions.

I will describe it using Ethereum network as an example. Beside the code, Smart Contract may have its own memory as a state
(if it isn't a stateless 'library' contract type). When the transaction, which triggers some function is taken by Node to build a new block,
the Node will start an EVM (Ethereum Virtual Machine). Then it will take the current state of Smart Contract, its code and will run it
on EVM. When the calculations will be done (or 'Gas' limit will be reached), a Node will put this state transition into a block as well.

You can imagine, that every Node in the network will run the same code separately. Because the block consists of application state changes it should also
produce the same Hash on every Node, which is required for reaching a consensus. 

There are many programming languages (dedicated or general-purpose), whose can be used to write Smart Contracts such as Solidity, Vyper, Rust, etc.
The most popular and commonly used is the Solidity (used on Ethereum network). Before deploying it on the Blockchain you have to compile code into a bytecode.
A contract can also trigger other contracts during runtime.

Of course there are also limited kinds of smart contracts in some blockchains on the market (which won't allow you to do everything),
but I was focused on a Turing-complete ones in this article.

#### Activities

As a Blockchain Developer you can write programs, whose will replace the need of 3rd party intermediaries,
because the logic behind them will be immutable on the blockchain. In particular, these may be agreements
between parties, companies, persons, institutions. It opens up a completely new possibilities like peer-to-peer
financial instruments (so called DeFi), borrows, decentralized chats, authentication mechanisms,
ownership of non-fungible data (NFT) and so on and so forth.

It's worth mentioning, that the code of Smart Contracts deployed on the Blockchain is (mainly) immutable,
so you have to shift your approach about maintenance and development of those. If there will be an error inside code,
there will probably not be a possibility to fix it. Before deploying it you have to be perfectly sure, 
that this logic is well tested and correct. Otherwise, you are allowed only to append new functions to the code
or deploy a completely new Smart Contract (as a separate thing).

Furthermore, each instruction may cost a different amount of Gas, so the performance is crucial, because it costs money.
The awareness of the consequences of decisions made inside a code (e.g. of choosing the proper type of variable of a collection)
should be definitely one of your skills.

### 2. Develop libs or apps, which interacts with Smart Contracts.
### 3. Read and process data from Blockchain.
### 4. Create an Oracle.
### 5. Build a Bridge between Blockchains.
### 6. Develop blockchain nodes / systems from scratch.

## Use-cases

Each activity can be useful in one or several use-cases.
We will describe them further in the article as well.

- Cryptocurrency Wallet
- Centralized cryptocurrency exchange
- Decentralized cryptocurrency exchange
- Authorization through NFT ownership
- Authorization through Blockchain Wallet
- NFT Marketplaces
- API libraries for interaction with Blockchain
- Data storage
- Existence on many blockchains
- Supply chain
- Using data outside blockchain

## Two main paths of specialization for Blockchain Developer

### 1. Building apps on blockchain (usability, front-side)

> TODO: description. E.g. Help a companies to use blockchain, build apps, tools, startups,
> process data from, basically everything around it.

### 2. Building blockchain internally (core, fundaments, back-side)

> TODO: description. E.g. Nodes, libraries, APIs, cryptography, security, testnet's, system design,
> consensus/quorum algorithms, etc.

### Fullstack Blockchain? (combined both, my own idea)

> TODO: describe. For those, who want to involve in whole spectrum! :)
> Didn't found the jobs like that, but maybe it will be a good suite of experience for start-up companies
> or for CTO's / Architects.