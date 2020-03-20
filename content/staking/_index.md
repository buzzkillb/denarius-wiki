+++
title = "Staking"
date = 2020-03-04T22:46:57-08:00
weight = 20
chapter = true
pre = "<b></b>"
+++

### Staking

# Proof of Stake (PoS)

6% APR

Proof of Stake Reward Structure
```
nCoinAge * 0.06 / 365;
```
Proof of Stake pays 67% to Staker and 33% to FortunaStakes.

{{<mermaid align="left">}}
graph TD;
    A{PoS Block}-->B(67% Staker);
    A-->C(33% FortunaStake);
    B-->D[100% of PoS Block];
    C-->D;
{{< /mermaid >}}
