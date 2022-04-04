---
layout: post
title: What does the Blockchain Developer really do?
categories: [Research]
excerpt: Let's decrypt the mystery behind this title. I have described the activities that a Blockchain Developer can do. These are also grouped into categories and compared to available jobs in the market. It turns out, that they are the various perspectives and types of responsibilities.
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

## Use-cases

Each activity described below in the next paragraph can be useful in one or several use-cases.
The real-world examples are among others:

- Cryptocurrency Wallet (custodial, non-custodial, multi-wallet)
- Centralized cryptocurrency exchange
- Decentralized cryptocurrency exchange
- Authorization through NFT ownership
- Authorization through Blockchain Wallet
- NFT Marketplaces
- API libraries for interaction with Blockchain
- Data storage
- Existence on many blockchains, bridges between them (interoperability)
- Supply chain
- Using data outside blockchain
- P2E (Play-to-earn) genre of computer games, which allows you to earn cryptocurrency by playing a game
- Paying for watching videos, listening in music, educational stuff (even for watched seconds of video, thanks to micro-transactions like BSV blockchain has instead of monthly subscription)

## Technical activities

List of activities you can do on technical side:

- Write and deploy Smart Contracts.
- Develop libs or apps, which interacts with Smart Contracts.
- Read and process data from Blockchain.
- Build a Bridge between Blockchains.
- Create an Oracle.
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
ownership of non-fungible tokens (NFT) and so on and so forth.

It's worth mentioning, that the code of Smart Contracts deployed on the Blockchain is (mainly) immutable,
so you have to shift your approach about maintenance and development of those. If there will be an error inside code,
there will probably not be a possibility to fix it. Before deploying it you have to be perfectly sure, 
that this logic is well tested and correct. Otherwise, you are allowed only to append new functions to the code
or deploy a completely new Smart Contract (as a separate thing).

Furthermore, each instruction may cost a different amount of Gas, so the performance is crucial, because it costs money.
The awareness of the consequences of decisions made inside a code (e.g. of choosing the proper type of variable of a collection)
should be definitely one of your skills.

### 2. Develop libs or apps, which interacts with Smart Contracts.

Smart Contracts with logic/data inside blockchain is one thing, but there should be at least one more layer (like UI) to allow people interact
with it. People should have some interface to use smart contracts without technical knowledge.

Therefore, you can use several libraries (like Web3j, web3.js and so on) or directly access Nodes APIs (e.g. via REST/gRPC protocols) in your application.
It doesn't matter, that frontend or backend (or both) is communicating with the Blockchain. Your application may depend on ledger completely or only partially
(like one element is stored in a decentralized way).

### 3. Read and process data from Blockchain.

Sometimes you will develop tools/applications, whose only uses data stored on blockchain (like analytics applications) without using Smart Contracts.
This activity may not be highly related with our topic, but it happens, that this is also a part of responsibilities of a Blockchain Developer position.

### 4. Build a Bridge between Blockchains.

A cross-chain Bridge is often a combination of 2 Smart Contracts: one per each (different) Blockchain.
Usually it allows people to transfer founds or other data (like NFTs) between two different ledger networks.

For instance, you have some ETH coins, that you want to move into another blockchain like Polygon. All you need to do is to trigger Smart Contract
on Ethereum network, give it an information how much Ether's you want to send and the recipient (destination) address on Polygon network.

Then the SC on Ethereum will freeze (hold) your desired amount of Ethers on their contract account and then emit an event (or use the Polygon Nodes API),
which triggers the second SC on Polygon. Then the Polygon SC will "unfreeze" part of its Ether equivalent founds and send them to destination account on Polygon network.
This works usually both-ways (if you want to transfer it back into Ethereum network).

However, there are variations of Bridges, whose use more centralised solutions (3rd party intermediary servers), 
especially when it's not possible to use only Smart Contracts (because of limitations). 

Of course, Bridges between Public and Private blockchains also exists (e.g. developers write them in Java using "Hyperledger Besu").

### 5. Create an Oracle.

An "Oracle" is on-chain API you can query to get data into your Smart Contracts. It connects the blockchain with outer (Web 2.0) world.
When you have some data outside ledger like weather data, you can access it through Oracle. 

Oracles can be also a bi-directional, so some events occurred in Smart Contracts may trigger outer-applications (or allow them to consume data) as well. 
Without them the SC may not have enough information to exploit their full potential, because the SC will have only information from blockchain.

On the other hand an Oracle isn't a primary source of data in SC. It acts rather like an additional query layer, 
which allows the SC to verify or authenticate external data source.

### 6. Develop blockchain nodes / systems from scratch.

The most complex area is to develop Blockchain core elements from scratch. You can for instance implement a blockchain Node according 
to Yellow-Paper (mostly mathematical) specification like Ethereum has, you can reuse many consensus mechanisms, hashing algorithms,
libraries, mix them up and create something new and so on. 

Despite the Smart Contracts area of development there are also many positions on the market (mostly in companies behind or around public blockchains), whose refers to 
core Blockchain system design. Most popular (modern) programming languages there are Rust or Golang, because of their efficiency in parallel/concurrent programming
and high performance in server use-cases. 

The range of required skills may be a quite large there:
- You should have theoretical and practical knowledge in cryptography (especially in different asymmetric algorithms)
such us internals of SHA-256, GPG, Elliptic Curve Digital Signature (ECDSA), RSA, AES and so on.
- knowledge of blockchain interoperability
- consensus/quorum algorithms (Proof-of-Work, Proof-of-Stake, Proof-of-Authority, etc.)
- distributed system design patters (CQRS, Saga, Two-Phase Commit, Sharding)
- ability to write highly-performant and reliable distributed systems
- fundamentals of peer-to-peer networks, TCP, UDP, RPC protocols
- solid understanding of concepts like HA/failover, ingress, load balancing, idempotence, eventual consistency
- optimization of non-relational databases
- ...and of course proficiency with low-level programming language paradigms, constructs and idioms

In addition, there are "Layer 2" solutions on the market, whose are trying to lower transaction costs, scale or speed up the blockchains in a various manners.
However, the L2 may be placed "off-chain" (in most cases), what force intermediary between people and the blockchain,
so these solutions are quite controversial and rather contradict what blockchain was supposed to be.

Some companies are also doing development in this area, so then you probably should explore things like:
"zero-knowledge", "zk-SNARK", "zk-STARK", "optimistic rollup" and so on. Because currently my knowledge about it is quite small,
I will not describe it in detail, but I left that here to let you be aware, that the "Layer 2" ecosystems exists.

## Two main paths of specialization for Blockchain Developer

After wider analysis of the Blockchain job offers, two career/specialization paths have emerged:
- Blockchain Developer, which build apps on (and around) blockchain using mainly SmartContracts (usability)
- Blockchain Engineer, which build and expand core blockchain elements, Nodes from scratch (foundations)

### 1. Building apps on blockchain (usability, shallow layer, business-oriented)

![](/images/posts/2/blockchain-developer-borders.png)

This kind of specialization will build applications for companies, whose want to use blockchain, but not build it from scratch.
Writing Smart-Contracts fits pretty well here. There would be nice, that you will have a deeper knowledge about ledger internals,
because then you will be more confident about the consequences of using, for example, one data structure instead of another.

Your daily responsibilities might also cross the area of building casual Web 2.0. frontend or backend side (or both), which communicates
with SmartContract and basically everything around it. 

This path may be easier for you to start with blockchain development, because you will not leave the Web 2.0. area completely in your career 
(which you probably are comfortable with). Another advantage might be a growing number (over time) of companies, whose want to build apps on blockchain
and will look for Blockchain Developers.

### 2. Building blockchain internally (core, foundations, science/tech-oriented)

![](/images/posts/2/blockchain-engineer-borders.png)

Blockchain Engineer touches more deep and technical aspect of distributed ledger. He will focus on low-level server programming,
building libraries, tools, platforms, whose will interpret the smart contracts code and allow to run it, expand it, and so on.

Gaining experience in this specialization will be harder to reach, but it will possibly give you much more satisfaction than just 
writing a Smart Contracts. If you're really interested in cryptography and blockchain internals, the difficult and complex problems
fascinates you, you want to beat them to create a completely new possibilities, where probably nobody has been before -> this path is for you.

### "Fullstack" Blockchain? All-in-one?

I saw also variations of those two paths in small amount of job offers, whose have wider spectrum of responsibilities, 
where someone creates some tools for internal blockchain and write Smart Contracts for applications as well. 
It would rather depend on the company size I think, in smaller ones (start-ups) there will be wider scope. In the opposite 
there will be much concise scope for larger companies. Sometimes these categories can overlap.

## Summary

We came across the most popular list of activities and responsibilities behind them. The Blockchain ecosystem is still quite young,
but we can see, that it emerges into two areas of development, business-oriented apps and tech-oriented fundamentals.
Probably soon or later it may become more complex in case of job positions on the market and their borders.

I hope this article has given you an idea of what this particular specialization is like in terms of the labour market.

As for me, I decided to explore both directions, both from the application side and from the Blockchain internals underneath.
How it will go for me, time will tell. The-two areas interest me a lot (extremely :)), so I don't want to limit myself.