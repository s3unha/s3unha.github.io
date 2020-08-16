---
layout: post
title: "Rollbacks in Decentralized Games"
date: 2020-08-16
---

>Chain reorganization (reorg) is a wonderful property unique to blockchains which allows disparate clients to trustlessly reach consensus with probablistic finality; however, chain reorgs in decentralized games is a bug, not a feature.

Recently when I have some free time, I've been helping [Nine Chronicles](https://nine-chronicles.com/) (NC)  by participating in their CBT.

For the uninitiated, Nine Chronicles is a game developed by the [Planetarium](https://planetariumhq.com/) team that showcases their [Libplanet](https://github.com/planetarium/libplanet) library, a "blockchain core in C#/.NET for persistent peer-to-peer online games."

They imagine a world where:

1. Game runs on clients running the same software; no servers required to play. 
2. Don't like a game or see improvements which can be made? Fork the code base without permission for maximum moddability.
3. Development costs for games are secured through new revenue models.

In line with this vision, there are 0 servers running NC and the whole game runs on clients that reach consensus through PoW. PoW provides [probablistic finality](https://medium.com/mechanism-labs/finality-in-blockchain-consensus-d1f83c120a9a) which means that a deeper a block sinks into the chain, the harder to revoke a transaction in that block.

I've been following the game from day one, participated in its alpha, and found regular reorgs happen. Understanding Nakamoto consensus and being that we're in beta, I've given up fretting and accepted reorgs as an annoyance all decentralized games will have for the time being, until this week.

This week, a 700 block deep reorg took place following a client update. I've wondered how it would be to update crypto games. However, I haven't realized how tricky it really can get depending on the blockchain snapshot that's used, reorg, and its effects. Long story short, I felt cheated and frustrated.

Numerous players have complained of having lost time and energy, levels, and in-game items till now. However, 700 blocks of work gone for all the testers struck a nerve. Throw in the added "benefit" of permanent loss with absolutely no way of getting anything back. Because it's decentralized, there's no admin to run and cry/complain to nor can they do anything about it such as a rollback.

Additionally, whereas I believe this reorg problem can eventually be solved through clever engineering, there's no escaping the fact that as a crypto game gains traction, a malicious 51% attack on a valuable chain is a clear and present danger. For games using general purpose blockchains such as Ethereum this isn't much of an issue. On the other hand, games built on blockchains using probablistic or economic finality is vulnerable at all times.

A game developer friend of mine told me of several server rollbacks during the early days of [Maplestory](https://maplestory.nexon.net/landing). Apparently the hardest part post-rollback was not angry users leaving the game but rather recompensing users for their lost time and energy. Nexon had to navigate through financial laws regarding digital items across varying jurisdictions.

It's clear crypto solves complexities of financial laws across jurisdictions. However, it doesn't abate angry users and may leave them unattended.

Consider for a moment a case where a dissatisfied user sues a game company over a reorg and permanent loss of in-game items. Although the company can sidestep legal ramifications because of blockchain and its censorship-resistance, the same censorship-resistance may be what turn players off from the gaming experience.

Another thing that surprised me after this deep reorg was that losing levels and items which I had farmed before the reorg did not upset me. What did upset me was lost Nine Chronicles Gold ($NCG), a in-game currency in NC rewarded either for mining or for selling items in their P2P marketplace.

NC CBT does not offer any ways of earning $NCG other than upgrading items and selling them on the market. As there are no NPCs I was always strapped for cash. Before switching mining on a week ago, NC was an idle MMORPG. After I started mining this week, it suddenly morphed into a trade simulation game.

The reorg presented an immutable, choose-your-own-adventure, deja vu experience where I started from a certain point in the past without levels, items, and $NCG. Funny enough I instinctively knew the computing power and the token rewards from mining were never coming back while the levels and items could be farmed again. I never had been fully immersed in the economic aspect of a game until this week. This was somethig new.

During the bull market of 2017, in order to explain the barrage of layer 1 blockchains which were coming out there was a sentiment that depending on the nature of the dapp, dapp companies would need to select the appropriate blockchain architecture to build on. This reorg enlightened me that teams will need to select an appropriate blockchain depending on the type of game they wish to create.

The $NFT madness happening on [NBA Top Shot](https://www.nbatopshot.com/) makes sense to be on [Flow](https://www.onflow.org/)—their competitive edge is their partnership with the NBA and monopoly over NBA-related IP and content.

I can't wait to see what other video gaming creativity is unleashed on what blockchain—forks, reorgs, and all.