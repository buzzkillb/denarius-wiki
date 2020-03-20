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
https://github.com/carsenk/denarius/blob/5c830a27670972486f7a032690520bbb0c2a3df1/src/main.cpp#L1557
```
if (pindexBest->nHeight == 1)
    nSubsidy = 1000000 * COIN;  // 10% Premine
else if (pindexBest->nHeight <= FAIR_LAUNCH_BLOCK) // Block 210, Instamine prevention
    nSubsidy = 1 * COIN/2;
else if (pindexBest->nHeight <= 1000000) // Block 1m ~ 3m D
    nSubsidy = 3 * COIN;  
else if (pindexBest->nHeight <= 2000000) // Block 2m ~ 4m D
    nSubsidy = 4 * COIN;
else if (pindexBest->nHeight <= 3000000) // Block 3m ~ 3m D
    nSubsidy = 3 * COIN;      
else if (pindexBest->nHeight > LAST_POW_BLOCK) // Block 3m
    nSubsidy = 0; // PoW Ends
```
Proof of Work pays 67% to the Miner and 33% to FortunaStakes of 0 Block Rewards and transactions fees.

{{<mermaid align="left">}}
graph TD;
    A{POW Block}-->B(67% Miner);
    A-->C(33% FortunaStake);
    B-->D[100% of POW Block];
    C-->D;
{{< /mermaid >}}
