+++
title = "Mining"
date = 2020-03-04T23:06:14-08:00
weight = 30
chapter = true
pre = "<b></b>"
+++

### Mining

# Proof of Work (POW)

Block Reward Structure  
https://github.com/carsenk/denarius/blob/eca0b705e748d62f93473be52893d07eec3be6b7/src/main.cpp#L1641
```
        if (pindexBest->nHeight == 1)
            nSubsidy = 1000000 * COIN;  // 10% Premine
        else if (pindexBest->nHeight <= FAIR_LAUNCH_BLOCK) // Block 210, Instamine prevention
            nSubsidy = 1 * COIN/2;
        else if (pindexBest->nHeight <= 1000000) // Block 1m ~ 3m D (33% will go to hybrid fortunastakes)
            nSubsidy = 3 * COIN;
        else if (pindexBest->nHeight <= 2000000) // Block 2m ~ 4m D
            nSubsidy = 4 * COIN;
        else if (pindexBest->nHeight <= 3000000) // Block 3m ~ 3m D
            nSubsidy = 3 * COIN;
        else if (pindexBest->nHeight > ZERO_POW_BLOCK) // Block 3m
            nSubsidy = 0; // PoW Reward 
        else if (pindexBest->nHeight > 4683333) // Block 4683333, Start PoW Rewards again as 0.0001 D per block, Less than ~100 D per year to prevent unspendable UTXOs
            nSubsidy = 10000; // PoW Reward 0.0001 D
```
Proof of Work pays 67% to the Miner and 33% to FortunaStakes of 0.0001 Block Rewards and transactions fees.

{{<mermaid align="left">}}
graph TD;
    A{POW Block}-->B(67% Miner);
    A-->C(33% FortunaStake);
    B-->D[100% of POW Block];
    C-->D;
{{< /mermaid >}}
