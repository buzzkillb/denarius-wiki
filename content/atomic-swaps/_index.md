+++
title = "Atomic Swaps"
date = 2020-03-04T23:04:14-08:00
weight = 55
chapter = true
pre = "<b></b>"
+++

### Cross-Chain Atomic Swaps
Denarius also features atomic swaps on its blockchain! You can now use BlockDX (Decentralized Exchange) to buy or sell D atomically via an atomic swap without any 3rd parties! https://blockdx.com/

"An atomic swap is a direct trade between two different coins running on two separate blockchains; there are no centralized-exchange websites or other third-parties required for this trade. The technology enables common users to bypass the labyrinth of website-exchanges currently necessary to purchase cryptocurrencies. Once implemented, the atomic swap will allow common users to trade and purchase any desired coin directly within their own wallets." -- Komodo AtomicLabs BarterDEX/HyperDEX

The first step in performing an atomic swap is you and the other party needs to agree on an exchange rate and also have available UTXOs. For example, you can go from BTC -> LTC, LTC -> D, D -> BTC and any other combination of currencies. Atomic swaps can be performed with a wide range of cryptocurrencies with Denarius, which will one day open up the doors for more fully decentralized exchanges and less reliance on 3rd parties. Currently Denarius utilizes SPV technology with ElectrumX Indexing servers to relay transaction information and utilizes UTXO/MultiSig/CLTV technology to ensure the swaps happen.
