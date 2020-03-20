---
title: "Staking Workflow"
date: 2020-03-04T23:16:51-08:00
---
### Proof of Stake 6% APR
```
nCoinAge * 0.06 / 365;
```
#### Stake 100 D Over 365 Days (104.0603934 D vs. 104.02)
{{<mermaid align="left">}}
graph LR;
    A{Stake 100 D}
    A --> B(180 Days)
    B --> I[67% Staker 1.982465753 D -> Total=101.982465753 D]
    B --> N[33% FS 0.6542136986 D]
    I --> J(185 Days)
    J --> L[67% Staker 2.077927665 D]
    J --> O[33% FS 0.6857161295 D]
    L --> M[Total=104.0603934 D]
    A --> C(365 Days)
    C --> E[67% Staker 4.02 D]
    C --> D[33% FS 1.3266 D]
    E --> F[Total=104.02 D]

{{< /mermaid >}}

#### Stake 5000 D Over 365 Days (5203.019671 D vs 5201 D)
{{<mermaid align="left">}}
graph LR;
    A{Stake 5000 D}
    A --> B(180 Days)
    B --> I[67% Staker 99.12328767 D -> Total=5099.123288 D]
    B --> N[33% FS 32.71068493 D]
    I --> J(185 Days)
    J --> L[67% Staker 103.8963833 D]
    J --> O[33% FS 34.28580648 D]
    L --> M[Total=5203.019671 D]
    A --> C(365 Days)
    C --> E[67% Staker 201 D]
    C --> D[33% FS 66.33 D]
    E --> F[Total=5201 D]

{{< /mermaid >}}
